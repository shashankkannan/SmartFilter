# SmartFilter

**Overview**

SmartFilter is an intelligent text analysis and filtering tool designed to enhance information retrieval and analysis from diverse sources, including web pages and text files. The project integrates various algorithms and data structures to provide powerful functionalities such as spell checking, autocomplete suggestions, and efficient text searching.

**Features**

**1. EditDistance (EditDistance.java)**
  - The EditDistance class implements the Levenshtein distance algorithm, which calculates the minimum number of single-character edits (insertions, deletions, or substitutions) required to transform one string into another. This algorithm is vital for the project's spell-checking functionality. The dynamic programming approach is employed to efficiently compute the edit distance and determine the similarity between two words.

**2. HTMLtoText (HTMLtoText.java)**
  - The HTMLtoText class is responsible for converting HTML files into plain text. It utilizes the Jsoup library, a Java library for working with real-world HTML, to parse HTML documents. The parsed text is then stored in a map (textContentMap), associating each file name with its corresponding plain text content. Additionally, the class creates text files from the extracted text, enabling further processing and analysis.

**3. IndexMain (indexMain.java)**
    
  - The IndexMain class serves as the central orchestrator of SmartFilter. It integrates various functionalities:

  - Web Crawling (runWebcrawl): Initiates the webCrawl class to crawl web pages, filter relevant links, and save their HTML content for subsequent analysis.

  - Text File Conversion (createTextFiles): Utilizes the HTMLtoText class to convert HTML files into plain text, creating a text file for each HTML file in the specified directory.

  - Keyword Search (KMPsearchfile): Initiates the KMPSearch class to perform keyword searches within text files using the Knuth-Morris-Pratt algorithm.

  - Spell Checking (spellCheck): Utilizes the EditDistance class to suggest corrections for misspelled words by comparing them to a pre-existing dictionary (dictionary.txt).

  - Autocomplete (autocomplete): Utilizes the Trie class to provide autocomplete suggestions based on user input.

**4. KMPSearch (Kmpsearch.java)**

  - The KMPSearch class implements the Knuth-Morris-Pratt (KMP) string searching algorithm. This algorithm efficiently searches for occurrences of a specific pattern (word) within a given text. The class provides methods to search for a word within a file and print the occurrences.

**5. Trie (Trie.java)**

  - The Trie class represents a trie data structure, which is used to store a dictionary of words extracted from text files. Key functionalities include:

  - Insertion (insert): Inserts words into the trie, updating the frequency table for each word based on the file number.

  - Search (search): Searches for a word in the trie and returns the frequency table associated with the last character of the word.

  - Autocomplete (autocomplete): Provides autocomplete suggestions based on the trie structure.

  - File Processing (create_whole_trie): Reads text files, processes them into words, and inserts them into the trie. Also creates a dictionary text file (dictionary.txt) containing all words.

  - Priority (priority): Determines the file with the highest frequency of a given word, aiding in providing relevant information during keyword searches.

**6. WebCrawl (webCrawl.java)**

  - The webCrawl class implements web crawling functionality. It uses depth-first search (DFS) to explore web pages, extract links, and filter out irrelevant URLs based on predefined regex patterns. The class saves the HTML content of filtered links for later analysis.




**Key Considerations and Improvements**

  - Efficiency: The use of advanced algorithms, such as KMP and Levenshtein distance, contributes to the efficiency of text searching and spell checking. However, further optimizations and parallelization could enhance performance, especially when dealing with large datasets.

  - Scalability: As the project processes web pages and text files, considering scalability is essential. Future improvements might involve distributed computing or cloud-based solutions to handle increased data volume.

  - User Interface: Integrating a user interface for SmartFilter could enhance user experience, allowing users to interact more seamlessly with the various functionalities.


**Getting Started**

 Make sure you have the following installed on your system:

- Java Development Kit (JDK) - [Download JDK](https://www.oracle.com/java/technologies/javase-downloads.html)
- Apache Maven - [Download Maven](https://maven.apache.org/download.cgi)
- Git - [Download Git](https://git-scm.com/downloads)

## Clone the Repository

Open your terminal or command prompt and run the following command to clone the SmartFilter repository:

```bash
git clone https://github.com/shashankkannan/SmartFilter.git
```

## Build the Project

Navigate to the project directory:

```bash
cd SmartFilter
```

Build the project using Maven:

```bash
mvn clean install
```

## Run SmartFilter

### 1. Web Crawling

To perform web crawling and save HTML content, run the following command:

```bash
java -cp target/SmartFilter-1.0-SNAPSHOT.jar project.webCrawl
```

This command initiates the web crawling process, filters links, and saves HTML content in the specified directory.

### 2. Text File Conversion

Convert HTML files to text using the following command:

```bash
java -cp target/SmartFilter-1.0-SNAPSHOT.jar project.HTMLtoText
```

This command converts HTML files to text, creating corresponding text files in the specified directory.

### 3. Keyword Search

Perform a keyword search within text files using the following command:

```bash
java -cp target/SmartFilter-1.0-SNAPSHOT.jar project.indexMain
```

Follow the on-screen instructions to enter the word you want to search for.

### 4. Spell Checking

Run spell checking on a given keyword using the following command:

```bash
java -cp target/SmartFilter-1.0-SNAPSHOT.jar project.indexMain
```

Follow the on-screen instructions to enter the keyword for spell checking.

### 5. Autocomplete

Get autocomplete suggestions based on user input:

```bash
java -cp target/SmartFilter-1.0-SNAPSHOT.jar project.indexMain
```

Follow the on-screen instructions to enter the prefix for autocomplete suggestions.

## Additional Notes

- Make sure to customize file paths and directories as needed in the Java files according to your system.
- The `dictionary.txt` file serves as the reference dictionary for spell checking.

Now you have successfully set up and run SmartFilter on your machine. Explore the various functionalities and enhance the project as needed for your specific use case.
