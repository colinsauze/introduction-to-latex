--
title: "Running LaTeX?"
teaching: 10
exercises: 0
questions:
- "how do we build a LaTex document?"
- "What are the common editors for LaTeX?"
objectives:
- "Explain that LaTeX is compiled"
- "Introduce TexStudio and Overleaf editors"
keypoints:
- "LaTeX is compiled by running the pdflatex command"
- "There are lots of editors which include a button to run pdflatex"
- "Some editors like Overleaf include a preview of your document"
---

# Setting up LaTeX

* Linux users install the package texlive using your package manager or [TeXStudio](https://www.texstudio.org/#download)
* Windows users install [TeXStudio](https://www.texstudio.org/#download)
Does windows need MiKTeX?????
* Mac users download [MacTeX](http://mirror.ctan.org/systems/mac/mactex/MacTeX.pkg) and [TeXStudio](https://github.com/texstudio-org/texstudio/releases/download/3.0.4/texstudio-3.0.4-osx.dmg)
* If you can't install anything you can use [Overleaf](https://www.overleaf.com/) in your web browser.


# Running LaTeX from the command line

(Note this won't work if you're using OverLeaf, if you are then paste in the contents of the document and press compile)

Download the example file `helloworld.tex` from (https://github.com/colinsauze/introduction-to-latex/raw/gh-pages/files/helloworld.tex)[https://github.com/colinsauze/introduction-to-latex/raw/gh-pages/files/helloworld.tex].

Or type out the code in your favourite text editor and save it as helloworld.tex

~~~
\documentclass{article}
\begin{document}
\title{Hello World}
\author{Jane Doe}
\maketitle
\end{document}
~~~
{: .latex}


~~~
pdflatex helloworld.tex
~~~
{: .bash}

This should produce some output like:

~~~
This is pdfTeX, Version 3.14159265-2.6-1.40.18 (TeX Live 2017/Debian) (preloaded format=pdflatex)
 restricted \write18 enabled.
entering extended mode
(./helloworld.tex
LaTeX2e <2017-04-15>
Babel <3.18> and hyphenation patterns for 7 language(s) loaded.
(/usr/share/texlive/texmf-dist/tex/latex/base/article.cls
Document Class: article 2014/09/29 v1.4h Standard LaTeX document class
(/usr/share/texlive/texmf-dist/tex/latex/base/size10.clo)) (./helloworld.aux)
[1{/var/lib/texmf/fonts/map/pdftex/updmap/pdftex.map}] (./helloworld.aux) )</us
r/share/texlive/texmf-dist/fonts/type1/public/amsfonts/cm/cmr10.pfb></usr/share
/texlive/texmf-dist/fonts/type1/public/amsfonts/cm/cmr12.pfb></usr/share/texliv
e/texmf-dist/fonts/type1/public/amsfonts/cm/cmr17.pfb>
Output written on helloworld.pdf (1 page, 26419 bytes).
Transcript written on helloworld.log.
~~~

It should also create a file called `helloworld.pdf` in the same directory which you can open in a PDF viewer such as Adobe Acrobat.

