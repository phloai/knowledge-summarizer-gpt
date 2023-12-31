# Knowledge Summarizer GPT

A tool designed to efficiently summarize user-provided knowledge files into a structured Table of Contents (ToC). This ToC is formatted specifically to enhance your custom GPT's ability to navigate and utilize large volumes of data effectively. 

### Why do you need a Table of Contents?
Custom GPT's have difficulty navigating many and large knowledge files. This, I learned, is because it actively scrolls through these files using `myfiles_browser`. Which means it finds keywords and looks over only a small portion of the file. 

With a Table of Contents, you can adjust your GPT's instruction to process the entire ToC. Empowering your GPT to understand which knowledge files and which lines inside the knowledge files it should scroll to. Giving your GPT context of the important regions of your knowledge files, to more accurately respond to your queries.

## Link to the GPT
- ChatGPT access link: [Knowledge Summarizer GPT](https://chat.openai.com/g/g-McHIHioC4-knowledge-summarizer) 

## Features
- **Automated Summarization:** Processes uploaded knowledge files and generates a comprehensive Table of Contents.
- [**Customized Formatting:**](#output-format) Generates ToCs in a JSON format tailored to improve GPT navigation.
- **Chunk Processing:** Capable of handling large files by summarizing them in smaller, manageable sections.
- **Continuity Support:** Remembers the last processed position in a file, allowing for seamless continuation in large documents.
- **User-Friendly Interface:** Easy-to-use prompts and clear instructions for uploading and processing files.
- **Accuracy and Efficiency:** Ensures precise summarization with key information highlighted for quick GPT access.
- [**Recommended GPT Instructions:**](#recommended-gpt-instructions) A recommended format for GPT instructions, that can be copied and filled to properly look up and search through uploaded knowledge files outputted by this script and [BuilderIO/gpt-crawler](https://github.com/BuilderIO/gpt-crawler).
- **Sample GPT:** For a sample GPT that uses the recommended instructions and the ToC, look at our [Mojo Teacher GPT GitHub](https://github.com/phloai/mojo-teacher-gpt). It contains the link to the GPT instructions and knowledge files used to create it.

## Getting Started
### Prerequisites
- Ensure you have a JSON knowledge file formatted as per the Knowledge Summarizer's [**requirements**](##file-formatting-guidelines).
- Access to ChatGPT Plus

### Manual Installation (TODO)
1. In the future the instructions will be added to this repository so we can all improve upon them.

### Usage
1. **Prepare Your Knowledge File**: Format your knowledge file according to the specified guidelines. Each file should be a JSON containing a list of dictionaries with keys like "title", "url", "path", "content", and "html".
2. **Upload Your File**: Use the GPT interface to upload your formatted knowledge file.
3. **Summarization**: The GPT will process the file, starting from the top, and generate a ToC in the specified JSON format.
4. **Continuation and Completion**: For large files, the GPT will handle them in chunks and will prompt you to continue processing the next chunk until completion.

## File Formatting Guidelines
Your knowledge file should be a JSON with the following structure:
- A list of dictionaries, each containing keys: "title", "url", "path", "content", "html".
- The "content" and "html" keys must contain the main information for summarization.
- Ensure consistency and clarity in the content for accurate summarization.

## Command-Line Tools for File Formatting
To assist in properly formatting your knowledge files, you can use the following command-line tools:

- **GPT Crawler** ([GPT Crawler GitHub Repository](https://github.com/BuilderIO/gpt-crawler)): This tool crawls and processes web content into the required JSON format. It's particularly useful for converting web pages and online documents into the structure expected by the Knowledge Summarizer.

- **GPT GitHub Crawler** ([GPT GitHub Crawler Repository](https://github.com/phloai/gpt-github-crawler)): This tool is designed for extracting content from GitHub repositories. It formats code, READMEs, and other documentation into a JSON structure suitable for the Knowledge Summarizer.

These tools can automate the process of formatting and ensure that your files adhere to the required structure.

## Output Format
The output will be a JSON-formatted Table of Contents with the following fields for each entry (fields in brackets are filled in by the GPT):

``` json
[
	{
		"Knowledge Filename": "Filename of the knowledge file",
      		"Title": "Descriptive title",
		"Description": "Brief description of the contents",
		"Key Words": ["List", "of", "keywords"],
		"Index": "Index position in the knowledge file",
		"Lines": "Line positions in the knowledge file"
	},
	...
]
```

## Recommended GPT Instructions
After uploading all of your knowledge files, including your Table of Contents, it is recommended to copy the [instruction-template.md](https://github.com/phloai/knowledge-summarizer-gpt/blob/main/instructions-template.md) into your custom GPT instructions. You should fill in the areas in brackets, with the specified information unique to your assistant. I found this format for the GPT instructions to work best with the outputted knowledge files from this script and [BuilderIO/gpt-crawler](https://github.com/BuilderIO/gpt-crawler). If you find a better template, please contribute and submit a pull request so we can all benefit from your improved instructions!

## Contributing
Contributions are welcome! To contribute:

1. Fork the repository.
2. Create a feature branch (`git checkout -b feature/AmazingFeature`).
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`).
4. Push to the branch (`git push origin feature/AmazingFeature`).
5. Create a new Pull Request.

## License
Distributed under the MIT License. See `LICENSE` for more information.

## Acknowledgments
This project uses instructions inspired by concepts from the [spdustin/ChatGPT-AutoExpert](https://github.com/spdustin/ChatGPT-AutoExpert).
