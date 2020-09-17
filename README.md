# LaTeX template for Sapientia Bachelor's Thesis ![Compile thesis](https://github.com/andraspatka/sapi-thesis-template/workflows/Compile%20thesis/badge.svg?branch=master)

Recommended Editor: Visual Studio Code with LaTeX Workshop plugin

Pro tip: use alt+z for text wrapping.

## Stuff to install

Dependencies:

```sh
sudo apt-get install texlive-latex-extra

sudo apt-get install texlive-lang-european

sudo apt-get install texlive-science
```

Spell checking: spell right

```sh
ln -s /usr/share/hunspell/* ~/.config/Code/Dictionaries

sudo apt install hunspell-hu
```

## Compiling

Compile with:

```
pdflatex main.tex
bibtex main
pdflatex main.tex
pdflatex main.tex
```

Or use VSC Latex Workshop Plugin:
- ctrl + shift + p
- type in: LaTeX Workshop: Build with recipe
- press enter
- choose the recipe with pdflatex -> bibtex -> pdflatex -> pdflatex

## Folder structure

Recommended folder structure:
- docs: LaTeX files and generated pdf
  - chapters: contains the LaTeX files for the chapters
  - figures: contains all kinds of figures
    - images: contains all kinds of images
      - literature: contains images that come from the literature
    - tables: contains tables
    - algorithms: contains pseudocode algorithms
  - pdfs: contains pdfs which can be included. Also contains the doc files (in case needed) from which pdfs can be generated.
- literature: scientific articles that were used for the thesis


## Github actions

The respository contains a very basic Github action, that compiles the latex document and pushes the generated PDF to the repo. In order to use this, you need to define two secrets:
- secrets.EMAIL: your email address (used for git)
- secrets.FULL_NAME: your full name (used for git)