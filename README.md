# authorarchive

> A LaTeX style for producing author self-archiving copies of (academic) papers.

<!-- toc -->

- [Installation](#installation)
- [Usage](#usage)
  * [Boolean Switches](#boolean-switches)
  * [Key/Value Options](#keyvalue-options)
- [Embedding Bibliography Entries](#embedding-bibliography-entries)
- [Development](#development)
- [Alternative Packages](#alternative-packages)
- [License](#license)

<!-- tocstop -->

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

### Boolean Switches
| Switch | Meaning |
| -- | -- |
| `nocopyright` | If present, no publisher's copyright notice is printed. Usual case for LNCS. |
| `nourl` | If present, no link to the publication is inserted. |
| `nobib` | If present, no embedding of bibliographic entries is made. |

### Key/Value Options
| Option | Default | Meaning |
| -- | -- | -- |
| `bibtexdir`| `.` | The directory where the bibliography entries are listed. |
| `baseurl` | https://git.logicalhacking.com/adbrucker/authorarchive/src/master | The URL used as prefix for building the links. |
| `suffix` | `.pdf` | The suffix to use at links. |
| `publisher` | `UNKOWN PUBLISHER` | The name of the publisher. Default values are set by the series (`LNCS`, ...). |
| `year` | `UNKOWN YEAR` | The year of the publication. |
| `key` | empty | The basename of the filename. Used also to generate links. |
| `doi` | empty | The DOI of the publication. Used to generate the DOI link. |
| `doiText` | The value of `doi` | In case a DOI contains underscores, the displayed text differs from the DOI. |
| `publisherurl` | empty | In case no DOI is provided, one can provide a link to the publisher. |
| `startpage` | 1 | The pagenumber of the first page of the paper. |
| `publication` | `UNKNOWN PUBLICATION` | Information on the publication. |

## Embedding Bibliography Entries
Mostly, it is hard for scientists to find the correct bibtex entry for a paper.
One solution to this issue is to embed the respective `.bib`, `.enw`, `.ris`, or `.word.xml` file in the PDF directly.
This work allows for that.
In case any of these file exist in the current directory, it gets embedded in the PDF.

You can generate these files by using [JabRef's export functionalities](https://help.jabref.org/en/#importexport).

## Development
You can fix the indent of `authorarchive.sty` by using [latexindent](https://ctan.org/pkg/latexindent) as follows:

    latexindent -l -s -sl -w authorarchive.sty

## Alternative Packages
The package [coverpage](https://ctan.org/pkg/coverpage) prepends a separate PDF page before the first page of the paper.
That page contains the bibliographic information as BibTeX entry.
One is forced to have a `.bib` file ready and multiple institutions are not well supported.
With `authorarchive`, the information is printed at the bottom of the first page of the paper and required links to the publisher are generated.

The package [llncsconf](https://github.com/adbrucker/llncsconf) is a light-weight alternative to this package.
It supports [LNCS](http://www.springer.com/de/it-informatik/lncs) only.
In comparison to `authorarchive`, it provides support for the additional publication states "intended-to-submit" and "submitted", but no QR code and links to the author's archive URL.

## License
If not otherwise stated, all sub-projects are dual-licensed under a
2-clause BSD-style license and/or the LPPL version 1 or any later 
version.
