# authorarchive

A LaTeX style for producing author self-archiving copies of (academic) 
papers. 

## Installation 
Copy `authorarchive.sty` in a directory that is searched by LaTeX
(e.g,. either your `texmf` tree or the local directory with your main
LaTeX file.

## Usage
A simple use for LNCS-formatted papers is as follows:
```tex
\usepackage[LNCS,
   key=brucker-authorarchive-2016,
   year=2016,
   publication={Anonymous et al. (eds). Proceedings of the International
       Conference on LaTeX-Hacks, LNCS~42. Some Publisher, 2016.}
   startpage={42},
   doi={00/00_00},
   doiText={0/00\_00},
   nocopyright
 ]{authorarchive}
```

The following layout-styles are pre-defined:
* `ACM` for the two-column layout used by many ACM conferences
* `IEEE` for the two-column layout used by many IEEE conferences 
* `LNCS` for the LNCS layout (as used by Springer)
* `LNI` for the Lecture Notes in Informatics, published by the GI
* `ENTCS` for the Elsevier ENTCS layout

By re-defining the font command (`authorcrfont{}`) and the command that is
used for positioning the copyright text (`\authorat{}`), the package can 
be adapted easily to other layouts. For example,
```tex
\renewcommand{\authorcrfont}{\scriptsize}
\renewcommand{\authorat}[1]{\put(25,56.5){#1}}
```
works nicely for Acta Informatica.

## Embedding Bibliography Entries
Mostly, it is hard for scientists to find the correct bibtex entry for a paper.
One solution to this issue is to embed the respective `.bib`, `.enw`, `.ris`, or `.word.xml` file in the PDF directly.
This work allows for that.
In case any of these file exist in the current directory, it gets embedded in the PDF.

You can generate these files by using [JabRef's export functionalities](https://help.jabref.org/en/#importexport).

## License
If not otherwise stated, all sub-projects are dual-licensed under a
2-clause BSD-style license and/or the LPPL version 1 or any later 
version. 
