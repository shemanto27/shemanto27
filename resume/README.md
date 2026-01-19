# 🧩 LaTeX CV – Installation Guide (Ubuntu + VS Code)

## 1. Install TeX Live (Recommended – full setup)

```bash
sudo apt update
sudo apt install texlive-full
```

This is large (~6GB) but prevents missing-package errors.

### OR Minimal Alternative

If someone wants a lighter install:

```bash
sudo apt install \
  texlive-latex-recommended \
  texlive-latex-extra \
  texlive-fonts-recommended \
  texlive-fonts-extra \
  latexmk
```

## 2. Verify Required Tools

```bash
latexmk --version
pdflatex --version
kpsewhich fontawesome5.sty
```

**Expected result for the last command:**

```
/usr/share/texlive/.../fontawesome5.sty
```

If nothing appears, install:

```bash
sudo apt install texlive-fonts-extra
sudo mktexlsr
```

## 3. VS Code Setup

### Install VS Code Extension

1. Open VS Code
2. Extensions → Search for **LaTeX Workshop** (by James Yu)
3. Install the extension

### Recommended VS Code Settings (settings.json)

```json
{
  "latex-workshop.latex.autoBuild.run": "onSave",
  "latex-workshop.view.pdf.viewer": "tab",
  "latex-workshop.latex.clean.fileTypes": [
    "*.aux","*.log","*.out","*.toc","*.fls","*.fdb_latexmk"
  ]
}
```

## 4. Build Commands

### Inside VS Code

- **Build PDF:** `Ctrl + Alt + B`
- **View PDF:** `Ctrl + Alt + V`

### From Terminal

```bash
latexmk -pdf resume.tex
```

**Clean build files:**

```bash
latexmk -C
```

## 5. Common Issues & Fixes

### A. spawn latexmk ENOENT

```bash
sudo apt install latexmk
```

### B. fontawesome5.sty not found

```bash
sudo apt install texlive-fonts-extra
sudo mktexlsr
```

## 6. Tested Environment

- Ubuntu 20.04 / 22.04 / 24.04
- VS Code + LaTeX Workshop
- TeX Live 2023+

## 7. Optional: For Non-Ubuntu Users

### Windows

- Install MiKTeX or TeX Live
- Install LaTeX Workshop in VS Code
