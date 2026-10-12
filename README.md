# Notes Summariser

An AI-powered tool that automatically summarises PDF notes using Natural Language Processing (NLP). Built with Python and Jupyter Notebook, it offers two summarisation modes — extractive and abstractive — and exposes a clean web interface via Gradio.

---

## Problem Statement

Students and professionals accumulate large volumes of PDF notes that are time-consuming to review manually. This tool reduces that overhead by generating concise, meaningful summaries from uploaded PDFs in seconds.

---

## Key Features

- Upload any PDF file and receive an AI-generated summary
- **Extractive summarisation** — selects the most important sentences from the original text using TF-IDF and TextRank (PageRank)
- **Abstractive summarisation** — generates a new, fluent summary using the `sshleifer/distilbart-cnn-12-6` transformer model from Hugging Face
- Interactive web UI powered by Gradio (runs locally in the browser)
- Handles multi-page PDFs via PyPDF2 text extraction
- Stopword removal and text normalisation for cleaner results

---

## Technologies Used

| Technology | Purpose |
|---|---|
| Python 3.12 | Core language |
| Jupyter Notebook | Development environment |
| NLTK | Sentence tokenisation, stopword removal |
| scikit-learn (TF-IDF) | Sentence similarity computation |
| NetworkX (PageRank) | TextRank extractive summarisation |
| Hugging Face Transformers | Abstractive summarisation model |
| PyTorch | Model inference backend |
| Gradio | Web UI |
| PyPDF2 | PDF text extraction |
| NumPy | Numerical operations |

---

## Project Structure

```
AI Notes Summarizer/
├── Untitled.ipynb       # Main notebook — full project implementation
├── requirements.txt     # Python dependencies
├── .gitignore           # Git exclusion rules
└── README.md            # Project documentation
```

---

## Installation

### Prerequisites

- Python 3.9 or higher
- pip or conda package manager
- A working internet connection (for the first run — the Hugging Face model is downloaded automatically)

### Steps

1. Clone the repository:

```bash
git clone https://github.com/GaureshShinde25/Notes-Summariser.git
cd Notes-Summariser
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

3. Download required NLTK data (done automatically in the notebook, but can also be run manually):

```python
import nltk
nltk.download('punkt')
nltk.download('stopwords')
```

---

## How to Run

1. Launch Jupyter Notebook:

```bash
jupyter notebook
```

2. Open `Untitled.ipynb`.

3. Run all cells in order (Cell → Run All).

4. When the Gradio interface launches, a local URL will appear in the output, for example:

```
Running on local URL: http://127.0.0.1:7860
```

5. Open the URL in your browser.

---

## Usage

1. Click **Upload Your Notes (PDF only)** and select a PDF file.
2. Choose a summarisation method:
   - **Extractive** — faster, selects key sentences directly from the text
   - **Abstractive** — slower on first run (model download ~1.2 GB), generates a new natural-language summary
3. The summary appears in the output panel on the right.

> Note: The abstractive method uses the `sshleifer/distilbart-cnn-12-6` model, which is downloaded from Hugging Face Hub on first use and cached locally. Subsequent runs are faster.

---

## Example Input and Output

**Input:** A 5-page PDF of biology lecture notes covering cell division.

**Extractive output (example):**
> "Mitosis is the process by which a single cell divides into two identical daughter cells. The cell cycle consists of interphase and the mitotic phase. During prophase, chromosomes condense and become visible."

**Abstractive output (example):**
> "Cell division involves mitosis, producing two identical daughter cells through several stages including prophase, metaphase, anaphase, and telophase."

---

## Dependencies

See [`requirements.txt`](requirements.txt) for the full list with pinned versions.

Core packages:
- `transformers==4.54.1`
- `torch==2.7.1`
- `gradio==5.17.1`
- `scikit-learn==1.6.1`
- `nltk==3.9.1`
- `networkx==3.5`
- `PyPDF2==3.0.1`
- `numpy==2.0.2`

---

## Author

**Gauresh Shinde**  
[GitHub](https://github.com/GaureshShinde25)
