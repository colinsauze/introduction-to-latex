---
title: "LaTeX Commands"
teaching: 15
exercises: 10
questions:
- "What are the three different styles of LaTeX command?"
objectives:
- "Understand how LaTeX commands are structured"
- "See the difference between commands that take no arguments, one's which take an argument and one's which use a begin and end command."
keypoints:
- "LaTeX uses a series of commands all beginning with a \ character"
- "Some commands take additional arguments between a { and } character"
- "Some commands take lots of additional content between begin and end commands"
---


# LaTeX Commands

## Commands with no arguments

As you've seen from the simple Hello World example, LaTeX commands all start with a '\' character. We saw three types of examples on the previous page. The simplest was just a slash followed by a command, which was the `maketitle` command. This command takes some of the information that was already given and displays the title block.

~~~
\maketitle
~~~
{: .latex}

LaTeX has a number of other commands like this, one of the most useful is `\newpage` which will insert a new page into the document. Lets modify our old document to have an extra page using this command:

~~~
\documentclass{article}
\begin{document}
\title{Hello World}
\author{Jane Doe}
\maketitle
\newpage
\end{document}
~~~
{: .latex}

But when we build this document it still doesn't have a second page, because LaTeX has decided since there's no content after the `\newpage` command it won't include the page. Lets add some extra text after the `\newpage`. Now the text 'hello world' will appear on the second page (and if we remove the `\newpage` it will appear on the first page.

~~~
\documentclass{article}
\begin{document}
\title{Hello World}
\author{Jane Doe}
\maketitle
\newpage
Hello World
\end{document}
~~~
{: .latex}


## Commands with arguments

Some commands in LaTeX take an argument or some extra information. This is done by writing a `{` and `}` symbol after the command and entering the arguments between them. We already saw this in the documentclass, author and title commands. Another useful command that works in this style is the `\textbf` command. This makes the text that appears between the `{` and `}` symbols into bold text. Lets try making the Hello World text we just wrote in bold.

~~~
\documentclass{article}
\begin{document}
\title{Hello World}
\author{Jane Doe}
\maketitle
\newpage
\textbf{Hello World}
\end{document}
~~~
{: .latex}

## Begin and End Commands

Our third type of commands use a `\begin` and `\end` statement and span multiple lines. We saw this already with the `\begin{document}` and `\end{document}` commands, the content of our entire document should be between these. These state that everything between the begin and end commands are part of the document. Another command we can use in this way is the `\begin{abstract}` command, the text for our abstract is then placed between this command and the `\begin{abstract}` and the `\end{abstract}`. We can place this anywhere in the code that we like, but we probably want it to appear just after the title and on its own page, so lets take the code we just wrote and add the abstract after the newpage and before the bold hello world.

~~~
\documentclass{article}
\begin{document}
\title{Hello World}
\author{Jane Doe}
\maketitle
\newpage
\begin{abstract}
The text for my abstract..
\end{abstract}
\textbf{Hello World}
\end{document}
~~~
{: .latex}

This now puts the abstract and the bold Hello World on the same page, perhaps this isn't quite what we want so lets add another page between them:

~~~
\documentclass{article}
\begin{document}
\title{Hello World}
\author{Jane Doe}
\maketitle
\newpage
\begin{abstract}
The text for my abstract..
\end{abstract}
\newpage
\textbf{Hello World}
\end{document}
~~~
{: .latex}


> ## Using the \bigskip command
>
> The command \bigskip creates a big empty section between two bits of text. Add a \bigskip to this document, after the abstract ends but before the document text.
> ~~~
> \documentclass{article}
> \begin{document}
> \title{Hello World}
> \author{Jane Doe}
> \maketitle
> \newpage
> \begin{abstract}
> The text for my abstract..
> \end{abstract}
> The document text
> \end{document}
> ~~~
> {: .latex}
> > ## Solution
> > ~~~
> > \documentclass{article}
> > \begin{document}
> > \title{Hello World}
> > \author{Jane Doe}
> > \maketitle
> > \newpage
> > \begin{abstract}
> > The text for my abstract..
> > \end{abstract}
> > \bigskip
> > The document text
> > \end{document}
> > ~~~
> > {: .latex}
> {: .solution}
{: .challenge}


> ## Using the \textit command
>
> The \textit command makes the text contained between its { and } characters into italics. Try using this command to make some italic text in your document.
>
> > ## Solution
> > ~~~
> > \documentclass{article}
> > \begin{document}
> > \title{Hello World}
> > \author{Jane Doe}
> > \maketitle
> > \newpage
> > \begin{abstract}
> > The text for my abstract..
> > \end{abstract}
> > \textit{The document text}
> > \end{document}
> > ~~~
> > {: .latex}
> {: .solution}
{: .challenge}

> ## Centering Text
>
> The `\begin{center}` command will centre all text that follows it until a `\end{center}` command is issued. Try using this command to centre the text in your document.
>
> > ## Solution
> > ~~~
> > \documentclass{article}
> > \begin{document}
> > \title{Hello World}
> > \author{Jane Doe}
> > \maketitle
> > \newpage
> > \begin{abstract}
> > The text for my abstract..
> > \end{abstract}
> > \begin{center}
> > The document text
> > \end{center}
> > \end{document}
> > ~~~
> > {: .latex}
> {: .solution}
{: .challenge}
