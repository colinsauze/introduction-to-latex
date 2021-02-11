---
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

LaTeX code has to be 'compiled' to convert it from the LaTeX language into a PDF file which can be easily viewed, distributed or printed. One method for doing this is to run the command `pdflatex` from the command line and tell it which LaTeX file we want to compile. Providing there are no errors this will convert the LaTeX into a PDF file.

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

It should also create a file called `helloworld.pdf` in the same directory which you can open in a PDF viewer such as Adobe Acrobat. It will also create some other temporary files called `helloworld.aux` and `helloworld.log`. These can be deleted afer you've compiled your document.

# Running LaTeX from TeXstudio

Now we'll paste the same code we used above into TeXstudio, then save the document and press the green button that looks like a play symbol with a tail on it or press the 'F5' key or click on the "Tools" menu and choose "Build and View".
![The icon to build and display in TeXStudio]({{ page.root }}/fig/texstudio-build-and-view.png)

![TeXStudio showing the preview]({{ page.root }}/fig/texstudio-example.png)

## Building a PDF with TeXstudio

Instead of previewing inside TeXstudio we can also build a PDF file by clicking on the green Play button, pressing 'F6' or choosing 'Compile' from the Tools menu.

# Running LaTeX from Overleaf

* Go to [www.overleaf.com](https://www.overleaf.com) in your web browser.
* Create a new account (if you don't already have one) and login.
* Click on "New Project" and choose "Blank Project", give the project a name.
* You'll be taken to a screen with some example LaTeX code already entered.
* Replace this with the code we entered above or upload the `helloworld.tex` file we downloaded.
* Click on the green "Recompile" button near the top middle of the screen.
* After a few seconds this should build your document and show it on the right side of the screen.
* Click on the download icon if you want a copy of the PDF.

![Overleaf Screenshot]({{ page.root }}/fig/overleaf.png)


> ## Compiling a document yourself
>
> Pick one of the methods shown above (a simple text editor, TeXStudio or Overleaf) and do the following:
>
> 1. Paste in the hello world document above.
> 2. Change the author to your own name.
> 3. Compile the code to make a PDF file and open it in a PDF viewer.
{: .challenge}
