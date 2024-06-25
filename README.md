# Unofficial LaTeX Template for Theses and Dissertations at the University of Texas

## DISCLAIMERS

1. This repository is **not** an official publication of the University of Texas at Austin. The template provided in this repository is not guaranteed to fulfill all of the official [Format Guidelines for Dissertations, Treatises, Theses, and Reports](https://utexas.box.com/shared/static/ffag6al7b0eaaqcheml6dcot9u3z6zit.pdf) as established by the Graduate School.
2. This template was used successfully with 2023 requirements, but may not be up to date with current rules. If you are using this template and the Graduate School requires formatting changes, please [create an Issue](https://github.com/shanemcq18/utexas-thesis-template/issues/new) to document shortcomings in the template.
3. This template is not a LaTeX tutorial. See [Overleaf](https://www.overleaf.com/learn/latex/Tutorials) for a thorough suite of tutorials.

## A Brief History

This LaTeX template was originally written by Young U. Ryu and later modified by Miguel A. Lerma and Craig McCluskey (thanks guys, we all owe you).
Craig's version is listed [here](https://gradschool.utexas.edu/academics/theses-and-dissertations/digital-submission-requirement/latex-document-preparation) and included in this repository as `template-2002.zip`.
Since then, the formatting requirements for theses and dissertations at UT-Austin have changed quite a bit, mostly becoming more relaxed over time.
In general, **consistency** throughout the report is what matters most; formatting choices (margin size, line spacing, etc.) are up to the writer as long as they are kept consistent throughout.
Some choices in this template may still be due to the stricter requirements of the past, so feel free to make changes and experiment as long as the result satisfies the current requirements set by the Graduate School.

This version of the template was updated in 2023 by Shane McQuarrie.
Summary of main changes from Craig's version:
- Page numbering is Arabic throughout and starts on the very first page (relatively new requirement).
- Changed margins to 1 inch on all sides.
- Changed default spacing to one-and-a-half (18pt).
- Left-aligned chapter headings.
- Severely stripped down the body of the template to essentials.
- Removed `zzclean` and `Makediss`, but added `Makefile` which relies on `latexmk` for the compilation recipe.
- Renamed `disstemplate.tex -> main.tex`
and cloistered imports / other user configuration to `config.tex`.
- General clean up / formatting of the template files, especially `utdiss.sty`.

## Usage

### Repository Organization

The `template/` folder contains the files for the actual template.
You can [download this repository as a `.zip` file](https://github.com/shanemcq18/utexas-thesis-template/archive/refs/heads/main.zip) or clone the repository to get at the files.
The `template/` folder includes the following:
- `utdiss.sty`: LaTeX style file that sets up most of the formatting.
- `config.tex`: LaTeX file for import commands (`\usepackage{}`) and the rest of the preamble.
- `main.tex`: LaTeX file that should be compiled to produce the actual document.
- `chapter-*.tex`: LaTeX source for a chapter of the report. Splitting the content into multiple files this way is [highly recommended](https://www.overleaf.com/learn/latex/Management_in_a_large_project). These files are imported in `main.tex` with the `\include{}` command.
- `abstract.tex`, `acknowledgments.tex`, `vita.tex`: LaTeX source for front / end matter in the report.
- `references.bib`: BibTeX file where references to be cited are stored.
- `Makefile`: Defines shortcuts for compiling the document and cleaning up auxiliary files.

### Report Compilation

To turn the source files into a PDF, we recommend using [`latexmk`](https://mg.readthedocs.io/latexmk.html) in the command line.
The resulting file is called `main.pdf`.

```bash
$ latexmk -pdf main.tex
```

The `Makefile` stores this command so you don't have to remember it.

```bash
$ make                  # Compile main.pdf.
$ make clean            # Delete auxiliary files if desired.
```

### Contributing

We welcome contributions in the form of a [new issue](https://github.com/shanemcq18/utexas-thesis-template/issues/new) or actual changes submitted through a pull request.
All pull requests must pass the automated GitHub action for building `main.tex` with `latexmk -pdf main.tex`.

## External Resources

- Graduate School webpage on theses and dissertations: https://gradschool.utexas.edu/academics/theses-and-dissertations/digital-submission-requirement
- Request a format check by the Graduate School Degree Evaluators by email at GradStudentSvcs@austin.utexas.edu.
- Non-latex dissertation templates: https://utexas.box.com/shared/static/xnr4okxrrcx3ptrklvmdopnbltfq52ez.zip
