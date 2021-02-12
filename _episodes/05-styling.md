---
title: "Styling Documents and Lists"
teaching: 15
exercises: 5
questions:
- "How do style the text in LaTeX documents?"
- "How can we create lists in LaTeX?"
objectives:
- "Understand how to apply styles to LaTeX documents"
keypoints:
- "we can style text with bold, underline, italic, superscript etc"
- "Some characters such as accented characters, £ signs, percent signs need special LaTeX commands to appear."
- "Extra spaces don't get shown by LaTeX, use the space command if you want extra spaces or newline to get a newline"
- "Some extra characters can be added by using some extra packages. The Siunitx is one such package, it provides SI units."
- "We can make numbered lists with the enumerate environment."
- "We can make un-numbered lists with the itemize environment."
---


# Styling Text

We already saw the `\textbf{}` command for bold text and `\textit{}` command for Italic text. But LaTeX offers a few other text styling commands including `\underline{}` command for underlined text, `\textsubscript{}` for subscript and `\textsuperscript{}` for superscript text.

## Setting Text Sizes

Text size can be adjusted by using the commands `\tiny`, `\small`, `\normalsize`, `\large` and `\huge`. These will set the size of the text until another size command is issued. They also don't create a new lines, so you can have multiple sizes of text on the same line.

~~~
\documentclass{article}
\begin{document}
	\section{Introduction}
	\tiny
	tiny text
	\small
	small text
	\normalsize
	normal text
	\large
	big text
	\huge
	huge text
\end{document}
~~~
{: .latex}

## Special Characters

Some characters which we can type on the keyboard won't actually appear if we type them into a LaTeX document. Perhaps the best example of this is the '%' character which means a comment in LaTeX. To insert this into a document we need to use the `\%` command. There are many other symbols which need LaTeX commands, including the £ symbol (\textsterling or \pounds), the less than and greater than symbols (\textless and \textgrater). See [this webpage from Wikibooks](https://en.wikibooks.org/wiki/LaTeX/Special_Characters#Escaped_codes) for a list of common symbols.


> ## Symbols exercise
> Write a letter in LaTeX saying the following:
> Dear Professor Schrödinger,
> Please find enclosed €200 for the cat you sold me.
> Yours Sincerely Émilie du Châtelet
> > ~~~
> > \documentclass{letter}
> > \usepackage{eurosym}
> > \begin{document}
> > Dear Professor Schr\"odinger,
> > Please find enclosed \euro{200} for the cat you sold me.
> > Yours Sincerely \'Emilie du Ch\^atelet
> > \end{document}
> > ~~~
> > {: .latex}
> {: .solution}
{: .challenge}

### LaTeX Packages

The `\usepackage{}` command is used to include extra packages, which is sometimes needed for extra symbols (and other extra commands and functionality to LaTeX). You will have needed to use this in the previous exercise to load the Euro symbol. This command is typically placed betwen the `\documentclass{}` and `\begin{document}` lines of a LaTeX file. One useful package is the `siunitx` package which includes SI units for many measurements. Sometimes you might also additional arguments to the package given between `[` and `]` symbols between the end of the package name and the `{` character.

~~~
\documentclass{article}
\usepackage{siunitx}
\begin{document}
The car was speeding at \SI{150}{\metre\per\second}.
\end{document}
~~~
{: .latex}

This will display the speed as km h to the power -1. We're probably more used to seeing km/h, we can set this by adding the command `\sisetup{per-mode=symbol}` after the `\usepackage` line.

## Whitespace Characters

Putting in multiple spaces or blank lines into our LaTeX source will still only result in one space or newline appearing in the output. Even if we end a line at what we think is a logical place and put in a newline, LaTeX won't create one there. If we really want extra spaces we have to use `\space` or for a newline its `\newline`.

## Lists

There are two types of lists which LaTeX can create, numbered lists and un-numbered lists. A numbered list is created with the `\begin{enumerate}` command, while un-numbered lists are created with the `\begin{itemize}` command.

~~~
\documentclass{article}
\begin{document}
\begin{itemize}
   \item First Item
   \item Second Item
\end{itemize}
\end{document}
~~~
{: .latex}

Its also possible to nest one list inside another, even if that list is of a different type.

~~~
\documentclass{article}
\begin{document}
\begin{itemize}
   \item First Item
   \begin{enumerate}
      \item first numbered item
    \end{enumerate}
\end{itemize}
\end{document}
~~~
{: .latex}


> ## Lists and packages exercises
> 1. Replace the _____ sections with the correct answers.
> 2. What does [binary-units=true] do on the second line?
> 3. What does \sisetup{group-separator = {,}} do on the third line?
> ~~~
> \documentclass{article}
> \usepackage[binary-units=true]{siunitx}
> \sisetup{group-separator = {,}}
> \begin{document}
> 	\begin{itemize}
> 		\item \SI{1}{\tera\byte} (terabyte) is equivalent to:
> 		\begin{_________}
> 			\item \SI{1024}{\___\byte} (gigabytes)
> 			\item \SI{1048576}{\mega\byte} (megabytes)
> 			\item \SI{1099511627776}{\kilo\byte} (kilobytes)
> 			\item \SI{1208925819614629174706176}{\byte} (bytes)
> 		\end{enumerate}
> 	\end{itemize}
> \end{document}
> ~~~
> {: .latex}
> > ## Solution
> > 1. enumerate and giga
> > 2. Allows us to use the \byte in siunitx, since bytes aren't actually an SI unit
> > 3. Makes the separator between each 3 digits a comma instead of the default space.
> {: .solution}
{: .challenge}

> ## Autorecognising Symbols
> The website "[Detexify](https://detexify.kirelabs.org/classify.html)" allows you to draw a symbol with your mouse (or finger/pen if you're using a phone or tablet) and will attempt to recognise it and tell you the LaTeX symbol for it.
{: .callout}



