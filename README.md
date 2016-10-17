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

## License
If not otherwise stated, all sub-projects are dual-licensed under a
2-clause BSD-style license and/or the LPPL version 1 or any later 
version. 
