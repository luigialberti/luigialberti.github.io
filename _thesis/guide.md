---
permalink: /thesis/guide/
title: "First guidelines for writing your degree thesis"
modified: 2026-10-27
---

<!-- {% include base_path %} -->
<!-- {% include toc %} -->

This page collects some practical advice that is worth reading at the very beginning of
your thesis work. It does not replace the discussion with your supervisor, but it should
help you avoid the most common problems and save a good amount of time in the final weeks.

The rest of this document is organized as follows.

1. [Organizing the text, structure and content](#organizing-the-text-structure-and-content)
2. [Text editors](#text-editors)
3. [Figures and graphic formats](#figures-and-graphic-formats)
4. [Writing equations](#writing-equations)
5. [Referring to figures, tables and other floats](#referring-to-figures-tables-and-other-floats)
6. [Managing the bibliography](#managing-the-bibliography)
7. [Declaring the use of artificial intelligence](#declaring-the-use-of-artificial-intelligence)

---

## 1. Organizing the text, structure and content

Structure and content are two different things, and it is much easier to work on them at
different times.

Before writing any sentence, prepare the table of contents. List the chapters and the
sections, and add two or three lines to each of them describing what it will contain.
Then discuss this outline with your supervisor. Changing an outline takes a few minutes,
while rewriting a whole chapter can take weeks.

A technical thesis usually follows a fairly standard organization. It opens with a short
abstract that summarizes the problem, the method and the main results. The introduction
presents the context, the aim of the work and its original contribution, and it closes
with a description of how the following chapters are organized. A chapter on the state of
the art or on the theoretical background recalls only what is needed to understand the
rest of the thesis. The core of the work describes the models and the methods in enough
detail to allow a colleague to repeat what you did, and it is followed by the results of
simulations and experimental tests together with their discussion. The conclusions
summarize what has been achieved, the limits of the work and possible future developments.
The bibliography and, if needed, some appendices with data, code or long derivations
complete the document.

Once the structure is clear, you can focus on the content. A few habits make a big
difference in the quality of the final text.

- Each paragraph should develop a single idea, ideally announced in its first sentence.
- Every symbol must be defined the first time it appears, and the same symbol should always indicate the same quantity.
- Use the same term for the same concept throughout the thesis, instead of alternating synonyms.
- Every number needs its unit of measurement, and a precise value is always better than a vague adjective.
- Every figure and table must be mentioned and commented in the text.
- Read the text again after a few days and always run a spell check before sending it to your supervisor.

Finally, try to keep the content separate from its appearance. While writing, think about
what you want to say and let the editor take care of headings, numbering and layout. This
is what makes a long document easy to modify up to the last day, and it is the main reason
behind the suggestions of the next section.

---

## 2. Text editors

There are many possible ways to write a thesis, but the most suitable editors are LaTeX
and Microsoft Word (or an equivalent program such as LibreOffice Writer). Both give good
results, provided that they are used in the proper way.

### LaTeX

LaTeX is the recommended choice, especially if your thesis contains many equations. It
naturally separates the content, written in plain `.tex` files, from the formatting, which
is defined by the document class and by the packages you load. Numbering,
cross-references, equations and bibliography are handled automatically and very reliably.

You can use LaTeX online with [Overleaf](https://www.overleaf.com), without installing
anything, or on your own computer with a distribution such as TeX Live or MiKTeX and an
editor like TeXstudio. For a long document it is convenient to keep a main file and one
separate file for each chapter, as in the following minimal example.

```latex
\documentclass[a4paper,12pt]{report}
\usepackage{graphicx}   % figures
\usepackage{amsmath}    % equations
\usepackage{siunitx}    % numbers and units
\usepackage{cleveref}   % smart cross-references

\begin{document}
\include{ch1_introduction}
\include{ch2_model}
\include{ch3_results}
\bibliographystyle{IEEEtran}
\bibliography{biblio}
\end{document}
```

### Word

If you prefer Word, the most important rule is to always use styles (Heading 1, Heading 2,
Normal, Caption and so on) and never format the text by hand. Only in this way will the
table of contents and the numbering of chapters, figures and tables be generated
automatically. Captions are inserted with *References → Insert Caption* and the
references to them with *References → Cross-reference*. Save your work often and keep
dated copies, or use a cloud folder that keeps the version history.

A Word template for the thesis is available for download on the Moodle page of the
course. Using it from the beginning saves you from adjusting the title page and the
layout at the last minute.

---

## 3. Figures and graphic formats

Images can be saved in many different graphic formats, but the main distinction is
between raster and vector images, and choosing the right one makes a visible difference
in the quality of the thesis.

A raster image is a grid of pixels, each with its own color. This is the natural format
for photographs, screenshots and maps of a field computed with a finite element program.
Its main limit is that it has a fixed resolution, so it becomes blurred or pixelated when
it is enlarged, and the file size grows quickly with the resolution. The most common raster
formats are JPEG (`.jpg`), which is well suited to photographs, PNG (`.png`), which is
better for screenshots and images with uniform colors, and TIFF (`.tif`).

A vector image describes lines, curves and text through their geometry. It stays sharp at
any zoom level, it usually produces small files and it can be edited later, for example to
change a label or the thickness of a line. On the other hand it is not suitable for
photographs. The most common vector formats are PDF (`.pdf`), SVG (`.svg`) and EPS
(`.eps`).

When you have to use a raster image, export it with an adequate resolution, that is at
least 300 dpi at the size at which it will be printed. Whenever possible, however, prefer a
vector format. Plots, block diagrams, circuits and drawings should always be vector images,
and many simulation programs can export their plots directly as PDF or SVG files. A plot
pasted into the thesis as a screenshot is one of the most common and most visible defects
of a thesis.

To draw schemes and diagrams you can use [Inkscape](https://inkscape.org), a free and open
source vector graphics editor that runs on Windows, macOS and Linux. If you have never used
it, the [official tutorials](https://inkscape.org/learn/tutorials/) are a good entry point.
The first three, called Basic, Shapes and Advanced, are enough to start drawing in an
afternoon, and they are also available inside the program from the Help menu. A more
complete introduction is the
[Inkscape Beginners' Guide](https://inkscape-manuals.readthedocs.io/), while the
[Learn](https://inkscape.org/learn/) page of the Inkscape website collects further
material, including video tutorials. Inkscape can save a drawing as PDF, and the
*PDF+LaTeX* export option leaves the text of the figure to LaTeX, so that symbols and labels
use the same font as the rest of the thesis.

Expert LaTeX users can also draw figures directly in the document with TikZ. The
[Overleaf introduction to TikZ](https://www.overleaf.com/learn/latex/TikZ_package) is a
good place to start, and the
[CircuiTikZ](https://ctan.org/pkg/circuitikz) package is very convenient for electric
circuits.

Whatever tool you use, a few rules apply to all figures. The text inside a figure should
have a size similar to that of the thesis text. The axes of a plot always report the
quantity and its unit, for instance "Torque (Nm)". Colors should remain distinguishable
when printed in black and white or when seen by a color blind reader, so it is a good idea
to also vary the line style and the markers. Finally, keep the same style for fonts, colors
and line widths in all the figures of the thesis.

---

## 4. Writing equations

Equations are part of the text. They should be introduced by a sentence, numbered when
they are recalled later, and followed by the definition of every new symbol. In LaTeX an
equation is written as shown below.

```latex
The phase voltage is related to the current and to the flux linkage by
\begin{equation}
  v = R\, i + \frac{\mathrm{d}\lambda}{\mathrm{d}t}
  \label{eq:voltage}
\end{equation}
where $R$ is the phase resistance and $\lambda$ is the flux linkage.
As shown by \cref{eq:voltage}, ...
```

In Word an equation is inserted with *Insert → Equation*, or with the `Alt` + `=`
shortcut. To number equations on the right, the usual solution is a borderless table with
three columns, with the equation in the central cell and the number, inserted as a
caption, in the right one.

Some typographic conventions are worth following from the start. Variables are written in
italics, while units of measurement and functions such as sin and cos are written in
upright font. A space separates a number from its unit, so you should write 50 Hz and not
50Hz (in LaTeX `\qty{50}{\hertz}` takes care of this). Punctuation continues after an
equation, since the equation is part of the sentence. There is no need to number every
equation, it is enough to number those you refer to in the text.

---

## 5. Referring to figures, tables and other floats

Figures and tables are called floating elements, or floats, because LaTeX (and to some
extent Word) places them where there is enough space on the page, which is not
necessarily the exact point where you inserted them. For this reason you should never
write "the figure below" or "the following table". Use a numbered reference instead, such
as "as shown in Fig. 3.2".

Every figure and table needs a caption that allows the reader to understand it without
reading the text. By convention the caption goes below figures and above tables.

Every float also needs a label, the internal name you use to refer to it. The number is
assigned automatically and is updated by itself when you add or move a figure. In LaTeX
the label must be placed after the caption, as in this example.

```latex
\begin{figure}[htbp]
  \centering
  \includegraphics[width=0.8\linewidth]{figures/current.pdf}
  \caption{Phase current measured at 1500 rpm and rated torque.}
  \label{fig:current}
\end{figure}

\Cref{fig:current} shows that ...
```

It helps to use consistent prefixes for the labels, such as `fig:`, `tab:`, `eq:` and
`sec:`, and to mention every figure in the text before it appears. In Word you obtain the
same result with *Insert Caption* and *Cross-reference*. Before sending a draft, select
the whole document and press `F9` to update all the numbers.

---

## 6. Managing the bibliography

Every idea, result, figure or piece of data taken from someone else's work must be cited,
whether it comes from a paper, a book, a datasheet, a standard or a website. Managing
citations by hand quickly becomes impossible, so it is worth adopting a reference manager
from the very first day.

[Zotero](https://www.zotero.org) is free and collects references directly from the web
browser. It works with Word through a plugin and with LaTeX through BibTeX export, which is
even better with the Better BibTeX extension. In LaTeX the references are stored in a
`.bib` file and cited with `\cite{key}`. In our field the most common style is the IEEE
one, obtained with `\bibliographystyle{IEEEtran}`. A typical BibTeX entry looks like this.

```bibtex
@article{alberti2013multilayer,
  author  = {Alberti, Luigi and Bianchi, Nicola},
  title   = {Theory and Design of Fractional-Slot Multilayer Windings},
  journal = {IEEE Transactions on Industry Applications},
  volume  = {49},
  number  = {2},
  pages   = {841--849},
  year    = {2013},
  doi     = {10.1109/TIA.2013.2242031}
}
```

BibTeX entries can be downloaded from IEEE Xplore, Scopus or Google Scholar, but they
always need to be checked, in particular authors, year, pages and the capitalization of
the title. Prefer primary and verifiable sources, such as journal and conference papers,
books, standards and official datasheets. Wikipedia and popular science websites can help
you get oriented in a new topic, but they are not sources to be cited in a thesis. Never
cite a work you have not read, at least in the part you are using, and make sure that
every reference actually exists. This is especially important for references suggested by
artificial intelligence tools, which are known to invent them.

---

## 7. Declaring the use of artificial intelligence

The University of Padova has adopted
[guidelines on the use of generative AI tools in teaching and in the preparation of degree and doctoral theses](https://psicologia.unipd.it/sites/psicologia.unipd.it/files/LineeGuidaImpiegoAI_Unipd_ITA_rev20251128.pdf)
(in Italian), in force since September 2025, which implement the
[general policy of the University](https://www.unipd.it/node/121803) on this subject. The
document may be updated over time, so always check the most recent version. The points
that matter most when writing a thesis are summarized below.

- You remain fully responsible for everything you write, including the parts in which an AI tool was involved. An improper use, such as copying text without checking it or without declaring its origin, is considered academic misconduct.
- AI tools cannot be used to write substantial parts of the thesis. They may be used to obtain feedback on your own work and to improve the language of a text that you have already written.
- Everything produced by an AI tool has to be checked, because these tools can give wrong information and cite sources that do not exist.
- With tools other than those provided by the University, you must not enter personal data, confidential data, data covered by agreements with companies or unpublished research results. Entering an unpublished idea into an online AI service may amount to disclosing it.
- Any use of AI tools must be declared precisely, reporting the tool, its version, the date and preferably the prompts, following the APA or MLA recommendations, in a dedicated part of the thesis such as the methods section or the bibliography.

Before using AI tools for your thesis, agree with your supervisor on whether and how you
may use them. A declaration could read as follows.

> **Declaration on the use of artificial intelligence tools.**
> In the preparation of this thesis I used [name of the tool, version] between
> [month year] and [month year], only for [for example, the language revision of
> Chapters 2 and 3]. All the content has been checked and revised by me, and I take full
> responsibility for it. The prompts used are reported in Appendix [X].

If you did not use any AI tool, it is good practice to state it explicitly with a similar
sentence.
