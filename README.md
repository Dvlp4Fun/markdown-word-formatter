# Format Magic — Document Formatter

Convert plain **Markdown-style Word documents** into professionally styled Word files, matching the "Format Magic" look — clean titles, ruled headings, bullet/numbered lists, real tables, and shaded code/diagram boxes [1].

---

## 1. Overview — What This System Does

This tool automates document formatting. You write (or generate) content using simple **Markdown syntax**, save it as a `.docx` file, and the script transforms it into a polished, professionally styled Word document.

**The core idea:**
1. You prepare content in Markdown (headings, bullets, tables, etc.).
2. You drop the `.docx` into the `input/` folder.
3. You run the script and choose your file from a terminal menu.
4. A styled `.docx` appears in the `output/` folder.
5. You open it in Word and Save As → PDF for the final result [2].

This mirrors the "one-click automated formatting" concept — turning raw text into elegant documents while preserving your original content [1].

---

## 2. How It Works (Step by Step)

| Stage | Action | Result |
|---|---|---|
| **Generate** | Use the AI prompt (Section 7) to create Markdown content | Correctly-structured text |
| **Prepare** | Paste that text into a blank Word file, save into `input/` | An input `.docx` |
| **Run** | Execute `python format_magic.py`, pick a file | Script processes it |
| **Collect** | Grab the styled file from `output/` | Formatted `.docx` |
| **Export** | Open in Word → Save As → PDF | Final PDF document [2] |

---

## 3. Supported Input Syntax

The script recognizes these Markdown structures inside your `.docx`:

| Input Syntax | Becomes in Output |
|---|---|
| `# Heading` | Large title with bottom rule |
| `## Heading` | Section heading with underline |
| `### Heading` / `#### Heading` | Smaller sub-headings |
| `- item` or `* item` | Bullet list |
| `1. item` | Numbered list |
| `**text**` | Bold text |
| `\| col \| col \|` + `\|---\|---\|` row | Real Word table |
| ` ```text ... ``` ` | Shaded monospace box (diagrams/code) |
| `---` (on its own line) | Section separator (skipped visually) |

**Important:** The input must already use Markdown syntax. The tool does not reformat free-form prose or scanned/image PDFs.

---

## 4. Folder Structure

```
format_magic/
│
├── format_magic.py       # main script (the formatter)
├── requirements.txt      # dependencies
├── README.md             # this file
│
├── input/                # put your unformatted .docx files here
│   ├── sample_input.docx # reference example (see Section 6)
│   └── your_document.docx
│
└── output/               # formatted files appear here
    └── your_document_formatted.docx
```

The `input/` and `output/` folders are auto-created on first run if they don't exist.

---

## 5. Installation & Running

### Install dependencies

```bash
pip install -r requirements.txt
```

**requirements.txt** contains:

```
python-docx
```

### Run the script

```bash
python format_magic.py
```

The terminal lists all `.docx` files found in `input/`. Pick one by number (or `0` for all):

```
=== Format Magic - Document Formatter ===
Files found in 'input/':

  [1] VideoView_SRS_SDD.docx
  [2] sample_input.docx
  [0] Format ALL files

Enter the number of the file to format: 1
  ✔ VideoView_SRS_SDD.docx  ->  output/VideoView_SRS_SDD_formatted.docx

Done! Check the 'output/' folder.
```

Then open the formatted file from `output/` in Word and do **Save As → PDF** [2].

---

## 6. Sample Input File (Reference)

Create a `.docx` in Word with the content below and save it as `input/sample_input.docx`. This demonstrates every supported feature — use it to understand the target format:

```
# PROJECT DOCUMENTATION TEMPLATE

**Version:** 1.0
**Prepared by:** Your Team
**Date:** 2026

---

# EXECUTIVE SUMMARY

This is a body paragraph explaining the document's purpose. Bold key terms like **main benefit** inline.

## 1. Introduction

### 1.1 Purpose

This sub-section describes the purpose in plain body text.

### 1.2 Scope

The system provides:

- **Feature One** — description of the first feature
- **Feature Two** — description of the second feature
- **Feature Three** — description of the third feature

## 2. How It Works

Follow these steps in order:

1. First step description
2. Second step description
3. Third step description

## 3. Comparison Table

| Feature | Basic | Premium |
|---|---|---|
| **Storage** | 10 GB | 100 GB |
| **Users** | 5 | Unlimited |
| **Support** | Email | 24/7 Phone |

## 4. System Diagram

```text
┌─────────────┐      ┌─────────────┐
│   Client    │─────▶│   Server    │
└─────────────┘      └──────┬──────┘
                            │
                     ┌──────▼──────┐
                     │  Database   │
                     └─────────────┘
```

## 5. Code Example

```python
def hello():
    print("Hello World")
```

---

# CONCLUSION

Final wrap-up paragraph.
```

---

## 7. AI Prompt to Generate Compatible Input

This is the **key to the whole system**. Give this prompt to any AI (ChatGPT, Claude, etc.) whenever you want it to produce content this script can format. Fill in your topic, then paste the AI's output into a blank Word file.

```
Generate a document about [YOUR TOPIC] using strict Markdown formatting 
so it can be processed by an automated Word formatter script.

Follow these formatting rules EXACTLY:

1. Use "# " for the main title and major section titles (e.g., # EXECUTIVE SUMMARY)
2. Use "## " for numbered sections (e.g., ## 1. Introduction)
3. Use "### " and "#### " for sub-sections (e.g., ### 1.1 Purpose)
4. Use "- " for bullet points
5. Use "1. " "2. " for numbered/ordered lists
6. Use "**text**" for bold emphasis on key terms
7. Use Markdown pipe tables with a separator row, like:
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

**Note:** The AI prompt and the sample file are two different things:
- The **sample file** (Section 6) *shows* what correct input looks like.
- The **AI prompt** (this section) *instructs an AI* to *generate* new content in that format.

---

## 8. Reference Example — VideoView SRS/SDD

The **VideoView SRS/SDD** document is an ideal real-world example — it uses every supported structure:

- `#` / `##` / `###` / `####` headings, such as `# PART 1: SOFTWARE REQUIREMENTS SPECIFICATION (SRS)` [2], `## 1. Introduction` [2], `### 1.1 Purpose` [2], and `#### FR-1: Browse Training Modules` [2]
- Pipe tables like `| Benefit | Impact |` [2] and the Technology Stack tables [2]
- ASCII architecture, ER, and screen-flow diagrams inside ` ```text ` code fences [2]
- Python/JavaScript code blocks inside ` ```python ` fences (e.g., the `create_app` factory) [2]
- `**bold**` inline terms such as `**Reduced training time**` [2]

Its stated goal was to keep "all content kept exactly as-is" in a "Word-ready formatted layout" for direct paste into Word and Save As → PDF [2] — exactly what this tool automates.

---

## 9. Full Workflow Summary

1. **Generate** — use the AI prompt (Section 7) to create Markdown content.
2. **Paste** — save it as `.docx` in `input/`.
3. **Run** — `python format_magic.py`, pick the file from the menu.
4. **Collect** — get the styled `.docx` from `output/`.
5. **Export** — open in Word → Save As → PDF [2].

---

## 10. Notes & Limitations

- **Tables** must use pipe syntax (`| col | col |`) with a separator row (`|---|---|`).
- **Diagrams/code** must be wrapped in triple-backtick fences to stay aligned; very wide ASCII diagrams (like the deployment topology or ER diagrams) may wrap depending on page width — use landscape orientation or reduce the font if needed [2].
- Output is **Word (.docx)** only; PDF is produced by Word's Save As, as recommended in the source workflow [2].
- The tool preserves your original content and does not rewrite text — it only applies styling [1].

---

## 11. Quick Reference Card

| I want to... | Do this |
|---|---|
| Understand the required format | Look at `sample_input.docx` (Section 6) |
| Create new content for the tool | Use the AI prompt (Section 7) |
| Format a document | Run `python format_magic.py`, pick the file |
| Get a PDF | Open output in Word → Save As → PDF [2] |

---

## License / Credits

Internal tool inspired by the one-click automated formatting concept [1].