# Study_Notes_Generator
**AI-Powered Study Notes from PDF & PPTX**

Upload lecture slides (PDF/PPTX) → Get clean summaries, key points, beautiful flowchart + auto-generated flashcards (Q&A pairs) — all locally using modern NLP.

## ✨ Features

- Extract text from **PDF** and **PowerPoint (.pptx)** files
- High-quality abstractive summarization (BART-large-cnn)
- Smart key phrase extraction using spaCy
- Colorful, auto-generated **flowchart** visualization of key concepts
- Automatic question-answer pair generation (flashcard style)
- Clean, responsive Streamlit interface
- All processing happens **locally** — no cloud, no API keys

## 📋 Tech Stack

- **Frontend**: Streamlit
- **Text Extraction**: PyPDF2 + python-pptx
- **NLP**: spaCy (en_core_web_sm)
- **Summarization**: facebook/bart-large-cnn (Hugging Face)
- **Question Generation**: valhalla/t5-small-qg-hl
- **Visualization**: NetworkX + Matplotlib
- **Python**: 3.8+

## 🚀 Quick Start (Local Installation)

### 1. Prerequisites

```bash
# Recommended Python version
python --version   # Should be 3.8–3.11
```

### 2. Install dependencies

```bash
pip install streamlit spacy transformers torch PyPDF2 python-pptx networkx matplotlib
```

### 3. Download spaCy model

```bash
python -m spacy download en_core_web_sm
```

### 4. Run the app

```bash
streamlit run app.py
```

→ Open browser: http://localhost:8501

## 🎯 How to Use

1. Click **"Choose a PDF or PPTX file"**
2. Upload your lecture notes / slides
3. Wait ~10–60 seconds (depending on file size & hardware)
4. Get:
   - Concise bullet-point summary
   - Most important key phrases
   - Beautiful flowchart of concepts
   - Ready-to-study Q&A pairs

## 🖥️ Example Output

**Input**: 20-page PDF lecture on "Photosynthesis"

**Output you get**:
- Clean 8–12 bullet point summary
- 8–10 important key terms/phrases
- Colorful flowchart showing process flow
- 4–5 high-quality question-answer pairs

## ⚡ Performance Tips

| Situation                        | Recommendation                                 |
|----------------------------------|------------------------------------------------|
| Very long documents (>50 pages)  | Split file or increase chunk size in code      |
| Slow summarization               | Use smaller model: `sshleifer/distilbart-cnn-12-6` |
| Slow on laptop                   | Limit summary sentences / key points           |
| No GPU                           | Everything works on CPU (but slower)           |
| Question generation not working  | Check Hugging Face cache / internet first time |

## 🛠️ Troubleshooting

| Problem                                 | Solution                                                                 |
|-----------------------------------------|--------------------------------------------------------------------------|
| spaCy model not found                   | `python -m spacy download en_core_web_sm`                                |
| Hugging Face model download fails       | Check internet / run once with connection                                |
| "torch not compiled with cuda" warning  | Normal on CPU-only — ignore or install torch+cpu                         |
| Flowchart looks messy                   | Try different NetworkX layout (kamada_kawai_layout, circular_layout…)   |
| Memory error on large files             | Increase `max_chunk_size` or process smaller sections                    |

## 📈 Possible Future Improvements

- Support for DOCX & handwritten note images (OCR)
- Multiple language support
- Customizable summary length & style
- Export to Markdown / Anki / PDF
- Better question variety (multiple per sentence)
- Dark mode + better mobile experience

## 📄 License

MIT License

Feel free to fork, modify, and use for your own study needs!
