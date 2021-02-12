---
title: "Common Problems and useful tips"
teaching: 5
exercises: 0
questions:
- "How do I format URLs into my document?"
- "How do I insert some common symbols?"
- "How do I get images into the right place?"
- "Is LaTeX really worth all this hassle?"
- "Are there any easier to use alternatives?"
- "How do I convert LaTeX to MS Word for my colleague/journal who insists we use Word?"
objectives:
- "Understand some common problems encountered in LaTeX and solutions to them"
- "Know about some utilities to make LaTeX easier to use"
keypoints:
- "Use the hyperref package and url command to handle URLs. Some characters might need escaping"
- "LaTeX has lots of commands for common special characters you might type in on the keyboard"
- "Images often appear in the wrong place, use [ht!], resize the image or move the reference to the image to a different place in the LaTeX code"
- "LaTeX can be hassle especially on smaller documents but really comes into its own on big documents"
---

# URL Formatting
LaTeX often doesn't like URLs in the code. Use the hyperref package and the `\url{}` command to include them, this will also make them a clickable hyperlink in the PDF. Sometimes certain characters have to be escaped with `\` character in front of them. Alternatively you can change them to an ASCII code with the code `\%<code>`, using a code from [asciitable.com](https://www.asciitable.com). For example `http://www.mysite.com/somepage?a=1&b=2` would become either `\url{http://www.mysite.com/somepage\?a=1\&b=2}` or `\url{http://www.mysite.com/somepage\%3Fa=1\%26b=2`.

# Special Characters
* £ sign, use `\pounds` or `\textsterling`
* `<` or `>` symbols: `\textless` or `\textgreater`
* Exponents (e.g. 2 8 ): `2\textsuperscript{8}`
* Degrees symbol (e.g. 45 ◦ ), load the siunitx package and use `$\SI{45}{\degree}$`

# Images in the wrong place
* Use [ht!] on the begin figure line: `\begin{figure}[ht!]`
* Move the source location of the image, this can make reading the source annoying but can make it appear in a better place on the page.
* Resize the image slightly by adjusting the `[width=xcm]` or `[height=xcm]` to the `\includegraphics` command.

# Is it worth the hassle?

* LaTeX might be more effort for smaller documents but it really pays off with bigger documents.
* Many Journals offer a LaTeX template and an example file which takes away a lot of the hard work.

## Useful Utilities

* LyX is a "What you see is what you mean" editor, it shows things in a nice graphical format that represent's how you intend it to look but is nothing like how it will really look on paper. It can use LaTeX commands, import/export LaTeX files and produces documents by converting to LaTeX first.

![A screenshot of LyX]({{ page.root }}/fig/lyx.png)

* [latex2rtf](http://latex2rtf.sourceforge.net/) converts LaTeX output to RTF files which can be read by MS Word. Useful for when you need to give somebody who doesn't know LaTeX a document for them to edit or a Journal insists on Word file submissions.

* [jabref](https://www.jabref.org/) is a BibTeX database manager that lets you manage your BibTeX database. [Mendeley](https://blog.mendeley.com/tag/bibtex/) can also export to BibTeX.
