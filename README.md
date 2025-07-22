# OCR PDF Renamer

A Python tool that uses Tesseract OCR to extract structured text (e.g., Document Number and FG ITEM #) from PDFs and automatically rename them. Designed for use on scanned documents with consistent layouts.

---

## 📂 Folder Structure

```
OCR_Renamer_Bundle/
├── ocr_rename.py           # Main script
├── PDFs/                  # Place your PDF files here
├── poppler/
│   └── bin/               # Poppler executables (e.g., pdftoppm.exe)
└── tesseract/
    ├── tesseract.exe      # Tesseract OCR engine
    └── tessdata/
        └── eng.traineddata
```

> ⚠️ All folders must be present for the script to work.

---

## ⚙️ Installation

### 1. Install Python

- Download from [https://www.python.org/downloads/](https://www.python.org/downloads/)
- During install, check ✅ **"Add Python to PATH"**

Verify:
```bash
python --version
```

---

### 2. Install Required Python Packages

Open a terminal and run:

```bash
pip install pytesseract pdf2image
```

---

### 3. Download Tesseract OCR (Portable)

- GitHub: [https://github.com/tesseract-ocr/tesseract](https://github.com/tesseract-ocr/tesseract)
- Copy `tesseract.exe` and `tessdata/` into `OCR_Renamer_Bundle/tesseract/`

---

### 4. Download Poppler for Windows

- GitHub: [https://github.com/oschwartz10612/poppler-windows](https://github.com/oschwartz10612/poppler-windows)
- Extract and copy the contents of the `bin/` folder into `OCR_Renamer_Bundle/poppler/bin/`

---

## ▶️ Running the Script

1. Place all your PDF files inside the `PDFs/` folder.
2. From the root of the `OCR_Renamer_Bundle` folder, run:

```bash
python ocr_rename.py
```

---

## 🧠 How It Works

- The script scans each PDF in the `PDFs/` folder.
- It extracts:
  - `DOCUMENT NO:` → e.g., `TSP001`
  - `FG ITEM #` → e.g., `130105`, `ABC-123`, `X_001`
- It renames the PDF to:  
  ```
  <DOCUMENT NO>_<FG ITEM #>.pdf
  ```

Example:
```
TSP001_130105.pdf
```

---

## 🛠 Troubleshooting

- If `pip` isn't recognized, try `py -m pip install ...`
- If `tesseract.exe` or `pdftoppm.exe` not found, check your folder paths
- For best accuracy, make sure the scanned forms are high quality (300 DPI+)

---

## 📄 License

MIT License — use freely, contribute if you'd like!
