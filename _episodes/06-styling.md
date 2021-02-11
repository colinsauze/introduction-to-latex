--
title: "Styling Documents"
teaching: 15
exercises: 5
questions:
- "How do style the text in LaTeX documents?"
objectives:
- ""
keypoints:
- "we can style text with bold, underline, italic, superscript etc"
- "Some characters such as accented characters, £ signs, percent signs need special LaTeX commands to appear."
- "Extra spaces don't get shown by LaTeX, use the \space command if you want extra spaces"
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
>
