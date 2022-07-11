# authorarchive

> A LaTeX style for producing author self-archiving copies of
> (academic) papers.

<!-- toc -->

- [authorarchive](#authorarchive)
  - [Installation](#installation)
  - [Usage](#usage)
    - [Boolean Switches](#boolean-switches)
    - [Key/Value Options](#key-value-options)
  - [Embedding Bibliography Entries](#embedding-bibliography-entries)
  - [Notes on Self-Archiving](#notes-on-self-archiving)
  - [Usage at arXiv.org](#usage-at-arxivorg)
  - [Other publishers](#other-publishers)
  - [Alternative Packages](#alternative-packages)
  - [Authors](#authors)
    - [Contributors](#contributors)
  - [License](#license)
  - [Upstream Repository](#upstream-repository)

<!-- tocstop -->

## Installation

Copy `authorarchive.sty` and the directory `icons` in a directory that
is searched by LaTeX (e.g., either your `texmf` tree or the local
directory with your main LaTeX file).

## Usage

A simple use for LNCS-formatted papers is as follows:

```tex
\usepackage[LNCS,
   key=brucker-authorarchive-2016,
   year=2016,
   publication={Anonymous et al.\ (eds). Proceedings of the International
       Conference on LaTeX-Hacks, LNCS~42. Some Publisher}
   startpage={42},
   doi={00/00_00},
   doiText={0/00\_00},
   nocopyright
 ]{authorarchive}
```

The following layout-styles are pre-defined:

- `ACM` for the two-column layout used by many ACM conferences
- `ENTCS` for the Elsevier ENTCS layout
- `IEEE` for the two-column layout used by many IEEE conferences
- `LNCS` for the LNCS layout (as used by Springer)
- `LNI` for the Lecture Notes in Informatics, published by the GI

By re-defining the font command (`authorcrfont{}`) and the command that is
used for positioning the copyright text (`\authorat{}`), the package can
be adapted easily to other layouts. For example,

```tex
\renewcommand{\authorcrfont}{\scriptsize}
\renewcommand{\authorat}[1]{\put(25,56.5){#1}}
```

works nicely for Acta Informatica.

### Boolean Switches

| Switch        | Meaning                                                                                                           |
| --            | --                                                                                                                |
| `nocopyright` | If present, no publisher's copyright notice is printed. Usual case for LNCS.                                      |
| `nourl`       | If present, no link to the publication is inserted.                                                               |
| `nobib`       | If present, no embedding of bibliographic entries is made.                                                        |
| `orcidicon`   | For layouts displaying the author's ORCID identifiers as text, replace the ORCID identifier by the ORICD iD icon and a hyperlink (currently only supported for LNCS). |

### Key/Value Options

| Option | Default | Meaning |
| -- | -- | -- |
| `bibtexdir`| `.` | The directory where the bibliography entries are listed. |
| `baseurl` | <https://git.logicalhacking.com/adbrucker/authorarchive/src/main> | The URL used as prefix for building the links. |
| `suffix` | `.pdf` | The suffix to use at links. |
| `publisher` | `UNKOWN PUBLISHER` | The name of the publisher. Default values are set by the series (`LNCS`, ...). |
| `year` | `UNKOWN YEAR` | The year of the publication. |
| `key` | empty | The basename of the filename. Used also to generate links. |
| `doi` | empty | The DOI of the publication. Used to generate the DOI link. |
| `doiText` | The value of `doi` | In case a DOI contains underscores, the displayed text differs from the DOI. |
| `publisherurl` | empty | In case no DOI is provided, one can provide a link to the publisher. |
| `startpage` | 1 | The pagenumber of the first page of the paper. |
| `publication` | `UNKNOWN PUBLICATION` | Information on the publication. |

The package also defines a command `\authorsetup{}` which allows to
define key value options dynamically. Moreover, if a file
`authorarchive.config` exists in the LaTeX search path, it will be
loaded automatically. This allows for configuring defaults (e.g., the
baseurl) easily.

## Embedding Bibliography Entries

Mostly, it is hard for scientists to find the correct bibtex entry for
a paper.  One solution to this issue is to embed the respective `.bib`
(BibTeX, for LaTeX users), `.enw` (Endnote), `.ris`, or `.word.xml`
(Word 2007 or later) file in the PDF directly. In case any of these
file exist in `bibtexdir`, it gets embedded in the PDF.

You can use the
[bibutils](https://sourceforge.net/p/bibutils/home/Bibutils/) for
converting between these different formats for bibliographic
references easily.

## Notes on Self-Archiving

Before using this package, please check with your signed copyright form,
which rights you have. Especially whether you may self-archive the preprint
or the postprint. For more information on that, read on at
<https://blogs.scientificamerican.com/information-culture/understanding-your-rights-pre-prints-post-prints-and-publisher-versions/>.

None of the authors might be hold liable for copyright
violations by using this package.

## Usage at arXiv.org

arXiv.org deletes bib files when submitting a pre print. As workaround, this package
supports using the file suffix `.bibtex`. When no `.bib` is found, but a `.bibtex`
file, this file is used and embedded as `.bib` file into the PDF.

## Other publishers

In general, one does not need to specify a certain publisher (or LaTeX document class).
The default setting just prints the note centered at the bottom of the first page.

```latex
\usepackage[
   key=brucker-authorarchive-2017,
   year=2017,
   publication={Anonymous et al.\ (eds). Proceedings of the International
       Conference on LaTeX-Hacks, CEUR-WS Vol~42, 2017.}
   startpage={42},
   doi={10.1039/authorarchive},
   nocopyright
 ]{authorarchive}
```

Still, for some used document classes (e.g., `lncs` and `acmart`) there are specific
package options available hat produce an alternative layout.  

## Alternative Packages

The package [coverpage](https://ctan.org/pkg/coverpage) prepends a
separate PDF page before the first page of the paper.  That page
contains the bibliographic information as BibTeX entry.  One is forced
to have a `.bib` file ready and multiple institutions are not well
supported.  With `authorarchive`, the information is printed at the
bottom of the first page of the paper and required links to the
publisher are generated.

The package
[llncsconf](https://ctan.org/pkg/llncsconf) is a
light-weight alternative to this package.  It supports
[LNCS](http://www.springer.com/de/it-informatik/lncs) only.  In
comparison to `authorarchive`, it provides support for the additional
publication states "intended-to-submit" and "submitted", but no QR
code and links to the author's archive URL.

## Authors

Main author: [Achim D. Brucker](http://www.brucker.ch/)

### Contributors

- [Oliver Kopp](https://github.com/koppor/)

## License

If not otherwise stated, all sub-projects are dual-licensed under a
2-clause BSD-style license and/or the LPPL version 1.3c or (at your
opinion) any later version.

```yaml
SPDX-License-Identifier: LPPL-1.3c+ OR BSD-2-Clause
```

## Upstream Repository

The upstream git repository, i.e., the single source of truth, for this 
project is hosted by the 
[Software Assurance & Security Research Team](https://logicalhacking.com) at
<https://git.logicalhacking.com/adbrucker/authorarchive>.
