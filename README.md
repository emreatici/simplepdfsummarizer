# Simple PDF Summarizer
A simple jupyter notebook for summarizing online PDF documents with chat-gpt.

This Python script is designed to summarize a research paper provided in PDF format. The code leverages the OpenAI GPT-3.5-turbo model to generate summaries. It creates two summaries: One is the union of the summary of all pages and the second one is a general summary all page summaries. Here's a step-by-step explanation of the code:

- Import the necessary libraries: os, re, time, PyPDF2, and openai. If PyPDF2 or openai are not installed, the code will install them.

- Set the variables for the input PDF URL, minimum words for the summary, preferred language, and an optional name for the article.

- Download the paper from the given URL using curl.

- Initialize an empty string, pdf_summary_text, to store the final summary.

- Read the PDF file using PyPDF2 and create a function ask() that takes a demand parameter and calls the OpenAI API to generate a response.

- Loop through all the pages in the PDF, extracting the text and calling the ask() function with the text to generate a summary for each page. The code handles API rate limit errors by retrying up to 10 times with a 10-second wait between retries.

- Concatenate the page summaries and save them to a .ptp_summary.txt file.

- If there are more than 5 pages in the PDF, divide the page summaries into smaller lists and generate a summary for each list. Concatenate these summaries, and then generate a final summary from the concatenated text.

- If there are 5 or fewer pages in the PDF, generate a summary directly from the concatenated page summaries.

- Save the final summary to a .summary.txt file and print it.

While there are more complicated versions out there, I wanted to create a simple and easy-to-use tool that anyone can benefit from. 
