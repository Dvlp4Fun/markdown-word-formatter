#  Document Formatter

Professional document formatting

Transform plain Markdown-style Word documents into beautifully styled `.docx` files with one command.

![Status](https://img.shields.io/badge/status-active-brightgreen)
![Python](https://img.shields.io/badge/python-3.7%2B-blue)
![License](https://img.shields.io/badge/license-MIT-green)

---

## 📋 Table of Contents

- [Quick Start](#quick-start)
- [What This Tool Does](#what-this-tool-does)
- [Installation](#installation)
- [How to Use](#how-to-use)
- [Supported Markdown Syntax](#supported-markdown-syntax)
- [Folder Structure](#folder-structure)
- [Sample Input File](#sample-input-file)
- [AI Prompt for Content Generation](#ai-prompt-for-content-generation)
- [Complete Workflow](#complete-workflow)
- [Limitations & Notes](#limitations--notes)
- [About This Project](#about-this-project)
- [Acknowledgments](#acknowledgments)
- [Attribution & References](#attribution--references)

---

## 🚀 Quick Start

**In 3 steps:**

1. **Prepare** — Write or generate content using Markdown syntax
2. **Run** — Execute `python format_magic.py` and select your file
3. **Export** — Open the formatted `.docx` in Word and Save As → PDF

```bash
# Install dependencies
pip install -r requirements.txt

# Run the formatter
python format_magic.py
```

---

## ✨ What This Tool Does

Format Magic automates professional document styling. Instead of manually formatting headings, tables, lists, and code blocks in Word, you:

- ✅ Write content using simple **Markdown syntax**
- ✅ Save it as a `.docx` file in the `input/` folder
- ✅ Run the script to transform it into a polished, professionally styled document
- ✅ Collect your formatted file from the `output/` folder
- ✅ Export to PDF with one click in Word

**The result:** Beautiful, consistent, professional documents — without the formatting headache.

### Perfect For

- 📊 Business reports and proposals
- 📄 Resumes and cover letters
- 🎓 Academic papers and research documents
- 📋 Technical specifications and documentation
- 📢 Marketing materials and presentations
- 👨‍🏫 Teacher resources and lesson plans

---

## 📦 Installation

### Prerequisites

- Python 3.7 or higher
- Microsoft Word (for final PDF export) or compatible alternative

### Step 1: Clone the Repository

```bash
git clone https://github.com/yourusername/format-magic.git
cd format-magic
```

### Step 2: Install Dependencies

```bash
pip install -r requirements.txt
```

**requirements.txt** contains:
```
python-docx
```

### Step 3: Verify Setup

Run the script to confirm installation:

```bash
python format_magic.py
```

You should see a menu listing any `.docx` files in the `input/` folder.

---

## 📖 How to Use

### Workflow Overview

| Stage | Action | Output |
|---|---|---|
| **1. Generate** | Create Markdown content (use AI prompt) | Structured text |
| **2. Prepare** | Paste into blank Word file, save to `input/` | Input `.docx` |
| **3. Run** | Execute `python format_magic.py`, select file | Script processes |
| **4. Collect** | Retrieve styled file from `output/` | Formatted `.docx` |
| **5. Export** | Open in Word → Save As → PDF | Final PDF |

### Running the Script

```bash
python format_magic.py
```

**Terminal Output:**
```
=== Format Magic - Document Formatter ===
Files found in 'input/':
  [1] my_report.docx
  [2] sample_input.docx
  [0] Format ALL files

Enter the number of the file to format: 1
  ✔ my_report.docx  →  output/my_report_formatted.docx

Done! Check the 'output/' folder.
```

**Options:**
- Enter `1`, `2`, etc. to format a specific file
- Enter `0` to format all files at once
- Formatted files appear in `output/` with `_formatted` suffix

---

## 🎨 Supported Markdown Syntax

The script recognizes these Markdown structures inside your `.docx`:

| Input Syntax | Output Style | Example |
|---|---|---|
| `# Heading` | Large title with bottom rule | `# PROJECT DOCUMENTATION` |
| `## Heading` | Section heading with underline | `## 1. Introduction` |
| `### Heading` | Sub-heading (smaller) | `### 1.1 Purpose` |
| `#### Heading` | Sub-sub-heading (smaller still) | `#### FR-1: Core Feature` |
| `- item` or `* item` | Bullet list | `- First point` |
| `1. item` | Numbered list | `1. First step` |
| `**text**` | Bold emphasis | `**Important term**` |
| ` ```text ... ``` ` | Shaded code/diagram box | ASCII art, code snippets |
| ` ```python ... ``` ` | Python syntax-highlighted box | Code examples |
| ` ```javascript ... ``` ` | JavaScript syntax-highlighted box | Code examples |
| `\| col \| col \|` + `\|---\|---\|` | Professional Word table | Feature comparison table |
| `---` (alone on line) | Section break (visual separator) | Between major sections |

### Important Notes on Syntax

- **Input must use Markdown.** The tool does not reformat free-form prose or scanned PDFs.
- **Tables require pipe syntax** with a separator row:
  ```markdown
  | Column A | Column B |
  |---|---|
  | value 1 | value 2 |
  ```
- **Code/diagrams must be wrapped** in triple-backtick fences to preserve alignment:
  ````markdown
  ```text
  ┌─────────┐
  │ Diagram │
  └─────────┘
  ```
  ````
- **Inline formatting** (`**bold**`, `_italic_`) works within paragraphs.

---

## 📁 Folder Structure

```
format_magic/
│
├── format_magic.py              # Main script (the formatter)
├── requirements.txt             # Python dependencies
├── README.md                    # This file
│
├── input/                       # Place your unformatted .docx files here
│   ├── sample_input.docx        # Reference example
│   ├── my_report.docx           # Your document
│   └── another_document.docx
│
└── output/                      # Formatted files appear here
    ├── sample_input_formatted.docx
    ├── my_report_formatted.docx
    └── another_document_formatted.docx
```

**Note:** The `input/` and `output/` folders are created automatically on first run if they don't exist.

---

## 📝 Sample Input File

Create a `.docx` in Word with the content below and save it as `input/sample_input.docx`. This demonstrates every supported feature:

```markdown
# PROJECT DOCUMENTATION TEMPLATE
**Version:** 1.0  
**Prepared by:** Your Team  
**Date:** 2026

---

## 1. Executive Summary

This is a body paragraph explaining the document's purpose. Bold key terms like **main benefit** inline.

## 2. Introduction

### 2.1 Purpose

This sub-section describes the purpose in plain body text. You can include multiple paragraphs and use formatting as needed.

### 2.2 Scope

The system provides:

- **Feature One** — description of the first feature
- **Feature Two** — description of the second feature
- **Feature Three** — description of the third feature

## 3. How It Works

Follow these steps in order:

1. First step description
2. Second step description
3. Third step description

## 4. Comparison Table

| Feature | Basic | Premium |
|---|---|---|
| **Storage** | 10 GB | 100 GB |
| **Users** | 5 | Unlimited |
| **Support** | Email | 24/7 Phone |

## 5. System Architecture

```text
┌─────────────┐      ┌─────────────┐
│   Client    │─────▶│   Server    │
└─────────────┘      └──────┬──────┘
                            │
                     ┌──────▼──────┐
                     │  Database   │
                     └─────────────┘
```

---

## Conclusion

Final wrap-up paragraph summarizing the key points and next steps.
```

---

## 🤖 AI Prompt for Content Generation

Use this prompt with ChatGPT, Claude, or any AI to generate content that Format Magic can process. Fill in your topic, then paste the AI's output into a blank Word file and save to `input/`.

```
Generate a professional document about [YOUR TOPIC] using strict Markdown 
formatting so it can be processed by an automated Word formatter script.

Follow these formatting rules EXACTLY:

1. Use "# " for the main title and major section titles
   Example: # EXECUTIVE SUMMARY

2. Use "## " for numbered sections
   Example: ## 1. Introduction

3. Use "### " and "#### " for sub-sections
   Example: ### 1.1 Purpose

4. Use "- " for bullet points
   Example: - First point

5. Use "1. " "2. " for numbered/ordered lists
   Example: 1. First step

6. Use "**text**" for bold emphasis on key terms
   Example: **important concept**

7. Use Markdown pipe tables with a separator row:
   | Column A | Column B |
   |---|---|
   | value 1 | value 2 |

8. Wrap any diagrams, code, or ASCII art in triple-backtick fences:
   ```text
   (diagram here)
   ```

9. Use "---" on its own line to separate major sections

10. Write normal explanatory content as plain paragraphs (no markers)

Do NOT use any other formatting (no HTML, no images, no markdown links).
Keep all content in plain Markdown only.

Topic: [DESCRIBE WHAT YOU WANT]
```

**Example Usage:**
```
Generate a professional document about "Cloud Migration Strategy" using 
strict Markdown formatting...
```

---

## 🔄 Complete Workflow

### From Idea to PDF in 5 Steps

**Step 1: Generate Content**
- Use the AI prompt above to create Markdown content
- Or write your own using Markdown syntax

**Step 2: Prepare Input File**
- Create a blank Word document
- Paste your Markdown content
- Save as `.docx` in the `input/` folder
- Example: `input/my_document.docx`

**Step 3: Run the Formatter**
```bash
python format_magic.py
```
- Select your file from the menu
- Wait for the script to complete

**Step 4: Collect Output**
- Open `output/my_document_formatted.docx`
- Review the formatting
- Make any manual adjustments if needed

**Step 5: Export to PDF**
- In Word: **File → Save As**
- Choose **PDF** as file type
- Click **Save**
- Done! You have a professional PDF

---

## ⚠️ Limitations & Notes

### What Works Well

- ✅ All standard Markdown syntax (headings, lists, tables, code blocks)
- ✅ Bold and italic inline formatting
- ✅ ASCII diagrams and code snippets
- ✅ Professional table layouts
- ✅ Consistent styling across documents

### Limitations

- ❌ **Images** — Not supported; use ASCII diagrams instead
- ❌ **HTML/Links** — Not supported; keep content in plain Markdown
- ❌ **Free-form prose** — Must use Markdown syntax; won't auto-format unstructured text
- ❌ **Scanned PDFs** — Cannot process image-based documents
- ❌ **Wide ASCII diagrams** — May wrap on standard page width; use landscape orientation or reduce font size if needed
- ❌ **PDF output** — Must use Word's Save As feature; the script outputs `.docx` only

### Best Practices

1. **Use consistent heading levels** — Don't skip from `#` to `###`
2. **Keep tables simple** — Complex nested tables may not format perfectly
3. **Test with sample file first** — Use `sample_input.docx` to verify your setup
4. **Backup originals** — The script creates new files; your originals remain untouched
5. **Use landscape for wide diagrams** — Prevents wrapping of large ASCII art

---

## 📚 About This Project

This is an independent, open-source implementation of document formatting automation. The project aims to provide developers and users with a free, customizable tool for transforming Markdown-formatted content into professionally styled Word documents.

### Key Features

- ⏱️ **Save hours of formatting time** — Automate repetitive styling tasks
- 🎨 **Achieve consistent, professional look** — Every document matches your style
- 💼 **Impress clients, employers, and colleagues** — Professional appearance matters
- 😌 **Reduce stress and focus on your content** — Let the tool handle formatting
- 🎯 **Fully customizable** — Modify and extend the code to suit your needs

---

## 🙏 Acknowledgments

- Inspired by the document formatting automation concept from **Format Magic Pty Ltd**
- Built with [python-docx](https://python-docx.readthedocs.io/)
- Special thanks to all contributors and users

---

## 📚 Attribution & References

### Inspiration Source

This project was **inspired by concepts from the Format Magic platform**:

- **Format Magic Official Website:** https://formatmagic.ai/
- **Company:** Format Magic Pty Ltd, Perth, Western Australia
- **Founder:** Jeremy Beard, CEO
- **About:** Professional document formatting, powered by AI

### Key Concepts Referenced

1. **One-Click Automated Formatting** — The core idea of transforming plain text into professionally styled documents with minimal user effort
2. **AI-Powered Document Styling** — Context-aware formatting that intelligently applies headings, styles, and layouts
3. **Template-Based Approach** — Using predefined templates to ensure consistent, professional output
4. **Multi-Format Support** — Supporting various document types (reports, resumes, academic papers, etc.)
5. **Markdown to Document Conversion** — Converting structured text into formatted documents

### Important Note

**This is NOT an official Format Magic product.** This is an independent, open-source project created to provide similar functionality. For the official Format Magic platform with advanced features and support, please visit https://formatmagic.ai/

---

**Ready to transform your documents?** Start with the [Quick Start](#quick-start) section above! 🚀

---

© 2026 This Project  
Inspired by Format Magic Pty Ltd (https://formatmagic.ai/)  
Licensed under MIT License
