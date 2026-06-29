# useful_tools

A small collection of standalone Python utilities. Each tool lives in its own folder and runs on its own.

## 🖼️ gif_generator

Stitches a sequence of images into an animated GIF.

```bash
cd gif_generator
pip install imageio
python gif.py          # combines 1.png, 2.png, ... into result.gif
```

Edit the `filenames` list and the `duration` (ms per frame) in `gif.py` to control which images are used and how fast the GIF plays.

## 📄 pdf_extractor

Pulls exam-style questions out of a PDF and answers them with an LLM. It parses the PDF text, splits it into sections (A/B) and numbered questions with regex, then sends them to the Groq API for answers (see `answers/example_answers.md` for sample output).

```bash
cd pdf_extractor
pip install -r requirements.txt        # pypdf, groq, python-dotenv
echo "GROQ_API_KEY=your_key_here" > .env   # get a key at console.groq.com
python pdf.py
```

Drop your PDF in `questions/` and point the script at it. The `GROQ_API_KEY` is read from `.env` and never committed.

## Stack

Python &middot; `imageio` (GIFs) &middot; `pypdf` + `groq` + `python-dotenv` (PDF extraction + LLM answers)
