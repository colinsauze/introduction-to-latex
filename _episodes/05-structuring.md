--
title: "Structuring LaTeX Documents"
teaching: 10
exercises: 0
questions:
- "How do you break up the structure of a LaTeX document?"
objectives:
- "Explain about the different sections of a document"
keypoints:
- "LaTeX lets us split up documents into sections, subsections, subsubsections etc."
- "Some document classes allow extra commands like chapters, tables of contents etc."
- ""
---


# Structuring LaTeX Documents

We've already seen that documents can have abstracts as a part of the document, but they can also have many other types of section to split up the document. We can declare sections, subsections, subsubsections and paragraphs using the commands: `\section{title}`, `\subsection{title}`, `\subsubsection{title}` and `\paragraph{title}`.

~~~
\documentclass{article}
\begin{document}
\title{My first LaTeX paper}
\author{Jane Doe}
\maketitle
\newpage
\section{Introduction}
Write introduction here....
\section{Background}
Write background here...
\section{Methods}
Write methods here...
\section{Results}
Write results here...
\section{Conclusion}
Write conclusion here...
\end{document}
~~~
{: .latex}

After compiling this document you should see that each section now has a bold heading with larger text and is numbered from 1 to 5. This numbering is automatic, if we change the order, add or remove a section the numbers will automatically change. Now lets add a table of contents by using the command `\tableofcontents` under the `\maketitle` line. Now on the first page there should be a title and a table of contents and on page two we'll have the sections and their contents.

~~~
\documentclass{article}
\begin{document}
\title{My first LaTeX paper}
\author{Jane Doe}
\maketitle
\tableofcontents
\newpage
\section{Introduction}
Write introduction here....
\section{Background}
Write background here...
\section{Methods}
Write methods here...
\section{Results}
Write results here...
\section{Conclusion}
Write conclusion here...
\end{document}
~~~
{: .latex}


> ## Creating subsections and subsubsections.
>
> Take the document above and add a subsection on Future Work to the conclusion and a subsubsection on exciting things I didn't have time for under the future work subsection.
>
> > ## Solution
> > ~~~
> > \documentclass{article}
> > \begin{document}
> > \title{My first LaTeX paper}
> > \author{Jane Doe}
> > \maketitle
> > \tableofcontents
> > \newpage
> > \section{Introduction}
> > Write introduction here....
> > \section{Background}
> > Write background here...
> > \section{Methods}
> > Write methods here...
> > \section{Results}
> > Write results here...
> > \section{Conclusion}
> > Write conclusion here...
> > \subsection{Future Work}
> > Write about future work here.
> > \subsubsection{Really Exciting Thing I didn't have time for}
> > Write about the really exiciting thing here.
> > \end{document}
> > ~~~
> > {: .latex}
> {:. solution}
{: .challenge}

> ## Creating Chapters
>
> Try putting all your sections inside a chapter by using the `\chapter{title}` command before the first section. Does this work? If not what error does it produce and why? How might you fix this?
>
> > ## Solution
> > You will get an error message saying "Undefined control sequence \chapter". This is because chapter isn't supported by the article document class since articles don't usually have chapters. If you change the document class from article to report then it should allow chapters.
> {: .solution}
{: .challenge}

## Adding Appendicies

To add Appendicies on the end of a document we need to first use a class that supports them. The report class is one example of a document class which supports them. Each appendix is really just a chapter, but LaTeX will start calling them Appendix instead of Chapter after we issue the command `\appendix`. For example:

~~~
\documentclass{report}
\begin{document}
	\title{My first LaTeX paper}
	\author{Jane Doe}
	\maketitle
	\newpage
	\tableofcontents
	\newpage
	\chapter{My Chapter}
	\section{Introduction}
	Write introduction here....
	\section{Background}
	Write background here...
	\section{Methods}
	Write methods here...
	\section{Results}
	Write results here...
	\section{Conclusion}
	Write conclusion here...
	\subsection{Future work}
	Write about what you'll do in future.
	\subsubsection{Thing I'm really exited about}
	There's this thing I didn't have time for that might be really exciting.
	\paragraph{Why its so it exciting}
	Because its so good!
	\appendix
	\chapter{Stuff I couldn't fit}
		Write appendix here
\end{document}
~~~
{: .latex}



# Sometimes you have to recompile multiple times
~~~
Sometimes things such as table of contents don't update the first time we recompile a document after adding them. This is because some information about things further into the LaTeX document isn't known the first time we compile, but as it compiles its entered into the .aux file which is read by the LaTeX compiler on the second pass. As we'll see in a future section the same thing can happen with bibliographic references.
~~~
{: .callout}

