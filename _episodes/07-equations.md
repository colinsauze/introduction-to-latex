---
title: "Mathematical Equations and Computer Code"
teaching: 15
exercises: 5
questions:
- "How do you add equations to your LaTeX document?"
- "How do you add computer code to your LaTeX document?"
objectives:
- ""
keypoints:
- "Equations can be entered inline by starting and ending with a $"
- "Equations can be placed on their own with the \begin{equation} command"
- "There are lots of specialist symbols like greek letters available as their own commands"
- "Computer code can be included with the verbatim or listings environments"
---

## Inline Equations

Inline equations appear in the normal text and start with a `$` symbol and then writes out the equation text followed by another `$`, powers are specified with the `^` symbol, fractions using the `\frac` command and the sigma symbol can be brought in using `\sum`. For example writing $E=mc^2$ would be `$E=mc^2$` or a more complex $x = \sum \frac{e^\pi}{y^2-a}$ is `$x = \sum \frac{e^\pi}{y^2-a}$`.

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


