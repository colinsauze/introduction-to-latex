---
title: "Mathematical Equations and Computer Code"
teaching: 15
exercises: 5
questions:
- "How do you add equations to your LaTeX document?"
- "How do you add computer code to your LaTeX document?"
objectives:
- "Understand how to insert equations and computer code into documents"
keypoints:
- "Equations can be entered inline by starting and ending with a $"
- "Equations can be placed on their own with the begin{equation} command"
- "There are lots of specialist symbols like greek letters available as their own commands"
- "Computer code can be included with the verbatim or listings environments"
---

## Inline Equations

Inline equations appear in the normal text and start with a `$` symbol and then writes out the equation text followed by another `$`, powers are specified with the `^` symbol, fractions using the `\frac` command and the sigma symbol can be brought in using `\sum`. For example writing $E=mc^2$ will display ![\E=mc^2](https://latex.codecogs.com/svg.latex?E=mc^2)

or a more complex ![\x = \sum \frac{e^\pi}{y^2-a}](https://latex.codecogs.com/svg.latex?x = \sum \frac{e^\pi}{y^2-a}) is `$x = \sum \frac{e^\pi}{y^2-a}$`.

~~~
\documentclass{article}
\begin{document}
	Einstein's famous formula $E=mc^2$....
\end{document}
~~~
{: .latex}

~~~
\documentclass{article}
\begin{document}
	$x = \sum \frac{e^\pi}{y^2-a}$ is `$x = \sum \frac{e^\pi}{y^2-a}$
\end{document}
~~~
{: .latex}

## Labelled Equations

Sometimes we want an equation to be displayed on its own, especially when its a key part of a paper. For this we can use the equation environment with the `\begin{equation}` and `\end{equation}` commands. Like with tables and figures, these can also be labelled and then referenced elsewhere in the text.

~~~
\documentclass{article}
\begin{document}
\begin{equation}
E=mc^2
\label{eq:einstein}
\end{equation}
Einstein's famous equation is shown in equation \ref{eq:einstein}.
\end{document}
~~~
{: .latex}

### Useful Mathematical Symbols

This isn't a complete list, see [The Comprehensive LaTeX Symbol List](https://anorien.csc.warwick.ac.uk/mirrors/CTAN/info/symbols/comprehensive/symbols-a4.pdf) for one.

* `\alpha`
* `\beta`
* `\delta`
* `\gamma`
* `\rho`
* `\sigma`
* `\epsilon`
* `\chi`
* `\tau`
* `\omega`
* `\lambda`
* `\theta`

## Computer Code

There are a few ways to include computer code in LaTex. The simplest in the `verbatim` environment which just shows the code inserted between the `\begin{verbatim}` and `\end{verbatim}` commands as it is, disabling any attempt to interpret it as LaTeX. It is usually shown in a courier font to differentiate it from other text, but otherwise has no styling.

~~~
\begin{verbatim}
#include<stdio.h>

int main(int argc,char **argv) {
  printf("Hello World\n");
  return 0;
}
\end{verbatim}
~~~
{: .latex}

Computer programmers often like to use colours or different text styles to highlight the syntax of their code, for this the more elaborate listings package can do this. The example below will do a simple black and white version with keywords put into bold. For a more elaborate version using colour see this example from [wikibooks](https://en.wikibooks.org/wiki/LaTeX/Source_Code_Listings).

~~~
\documentclass{article}
\usepackage{listings}
\begin{document}
\lstset{language=C}
\begin{lstlisting}
#include<stdio.h>

int main(int argc,char **argv) {
  printf("Hello World\n");
  return 0;
}
\end{lstlisting}
\end{document}
~~~
{: .latex}

### Captioning Code Listings
The listings package doesn't support the `\caption{}` command we've used on tables and images. Instead add a `caption` parameter in `[` and `]` to the `\begin{lstlisting}` command. For example:

~~~
\begin{lstlisting}[caption=Caption text here]
~~~
{: .latex}


### Loading computer code from a file

Computer code can be loaded from a source file instead of being pasted into LaTeX. This way the document can always reflect the latest version of your code. This is done using the `\lstinputlisting{}` command, where the filename is the argument. An optional extra argument can specify the language inside square brackets `[` and `]` symbols with the word `language=` followed by the language name, for example `[language=C]` or `[language=python]`. 

~~~
\documentclass{article}
\usepackage{listings}
\begin{document}
\lstinputlisting[language=C]{helloworld.c}
\end{document}
~~~
{: .latex}

> ## Including and Equations Code Exercise
> Create a LaTeX document with the following source code included. You can download this code as a file from [{{ page.root }}/files/sine_curve.py]({{ page.root }}/files/sine_curve.py). Write a caption stating that this is the code for generating the curve of ![\y=sin(x)](https://latex.codecogs.com/svg.latex?y=sin\(x\))
> ~~~
> import matplotlib as mpl
> import matplotlib.pyplot as plt
> import numpy as np
> x = np.arange(0, 10, 0.1);
> y = np.sin(x)
> plt.plot(x, y)
> plt.title('Sine Curve')
> plt.show()
> ~~~
> {: .python}
> > ## Solution
> > ~~~
> > \documentclass{article}
> > \usepackage{listings}
> > \begin{document}
> > \lstset{language=python}
> > \begin{lstlisting}[caption={Below the code to generate the curve of $y=sin(x)$}]
> > import matplotlib as mpl
> > import matplotlib.pyplot as plt
> > import numpy as np
> > x = np.arange(0, 10, 0.1);
> > y = np.sin(x)
> > plt.plot(x, y)
> > plt.title('Sine Curve')
> > plt.show()
> > \end{lstlisting}
> > \end{document}
> > ~~~
> > {: .latex}
> {: .solution}
{: .challenge}




