# Minimal BPE Tokenizer Implementation

This repository contains a minimal implementation of a Byte Pair Encoding (BPE) tokenizer, developed as part of a programming task to understand subword tokenization, algorithmic thinking, and clean code practices. This implementation focuses on the core mechanics of BPE and does not utilize any external tokenization libraries.

## Features

- **Training**: Trains a BPE model on an arbitrary UTF-8 text file.
- **Encoding**: Converts new text into a list of integer token IDs.
- **Decoding**: Reconstructs the original text from a list of integer token IDs (loss-less for the training set).
- **Minimalist Design**: Designed to be small and efficient, omitting handling of special tokens, complex regex pre-tokenization, or advanced Unicode corner cases for simplicity and adherence to project constraints.

## Project Structure

bpe_tokenizer/
│
├── src/
│ ├── tokenizer.py # Core BPE tokenizer logic
│ └── main.py # Client CLI for training, encoding, and decoding demonstration
│
├── alice.txt # Testing corpus used for demonstration (provided by task)
├── README.md # This file
└── output.txt # Example output for tokenization & detokenization demonstration

## How to Run

1.  **Clone the repository:**

    ```bash
    git clone <your-github-repo-link>
    cd bpe_tokenizer
    ```

2.  **Ensure Python 3 is installed.** (The project uses Python 3.11.5 based on your metadata.)

3.  **Run the main script for demonstration:**
    ```bash
    python src/main.py
    ```
    This script will:
    - Initialize the `BPETokenizer` with a `vocab_size` of 200.
    - Train the tokenizer using `alice.txt` as the corpus.
    - Encode a sample sentence: "Alice was beginning to get tired".
    - Decode the resulting token IDs back into text.
    - Print the original text, encoded IDs, and decoded text to the console.
    - Write these results to `output.txt`.

## Code Overview

### `tokenizer.py`

- **`BPETokenizer` class**: Encapsulates the BPE logic.
  - `__init__(self, vocab_size=200)`: Initializes the tokenizer with a specified vocabulary size.
  - `get_bigrams(self, word)`: Helper function to extract pairs of adjacent tokens within a word.
  - `train(self, corpus_path)`: Implements the core BPE training algorithm, iteratively merging the most frequent byte pairs until the `vocab_size` is reached.
  - `encode(self, text)`: Encodes an input string into a list of token IDs based on the learned merges.
  - `decode(self, token_ids)`: Decodes a list of token IDs back into a string.

### `main.py`

- This script serves as a client-side interface to demonstrate the tokenizer's capabilities. It handles file reading, tokenizer instantiation, training, encoding, decoding, and outputting the results.

## Usage of LLM in Tasks

The core logic and structure of this BPE tokenizer implementation were independently developed. A Large Language Model (LLM) agent (Google Gemini) was used to assist with generating the content for this `README.md` file and the script for the demo video. The code itself is independent work, built on fundamental BPE algorithm understanding.

## Author

Kanak Agrawal
