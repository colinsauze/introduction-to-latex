---
title: "Bibliographies"
teaching: 10
exercises: 5
questions:
- "How do you include bibliographic references?"
objectives:
- "Understand how to include bibliographic references in LaTeX"
keypoints:
- "LaTeX needs bibliography information to be stored in a separate BibTeX database."
- "Each bibtex entry needs a unique key"
- "We cite bibtex entries with the \\cite{} command"
- "We make LaTeX display the bibliography with the \\bibliography{} command, this also specifies the name of the bibtex database"
- "We can choose the style of the bibliography with the \\bibliographystyle{} command. Common ones are unsrt, plain or named"
- "Many journals will offer you the option to download the BibTeX for a paper"
---

LaTeX lets you cite references as you go in your document and then produces a bibliography of all the references that were used. References are placed in an external file called a BibTeX database, where each reference will have a key to uniquely identify it. These keys can be anything you like, but typically they are the author's name and the year or the title of the item. LaTeX then uses the `\cite{}` command to include a link to the reference.

Here is some example BibTex for a book about LaTeX and an article. `goossens93` and `greenwade93` are the keys which we'll use to cite them inside LaTeX.

~~~
@book{goossens93,
    author    = "Michel Goossens and Frank Mittelbach and Alexander Samarin",
    title     = "The LaTeX Companion",
    year      = "1993",
    publisher = "Addison-Wesley",
    address   = "Reading, Massachusetts"
}

@article{greenwade93,
    author  = "George D. Greenwade",
    title   = "The {C}omprehensive {T}ex {A}rchive {N}etwork ({CTAN})",
    year    = "1993",
    journal = "TUGBoat",
    volume  = "14",
    number  = "3",
    pages   = "342--351"
}
~~~
{: .bibtex}

The LaTeX code to reference these will be `\cite{goossens93}` or `\cite{greenwade93}`, the LaTeX compiler will replace these lines with a number or an author/date style reference inside the main text and then include them in bibliography. We also have to tell LaTeX what BibTex file to use with the `\bibliography{}` command, this takes the argument of the name of the bibliography without the `.bib` extension that is normally given to BibTeX files. We can also set the style of the bibliography with the `\bibliographystyle{}` command, common styles include the plain style which uses numbered references in the document and sorts the bibliography by author, the unsrt style does the same but sorts by the order of referencing and the named style uses the authors name and date instead of a number inside the text.

~~~
\documentclass{article}
\begin{document}
We can cite a text like \cite{goossens93}  or \cite{greenwade93} with the cite command.
\bibliography{library}
\bibliographystyle{unsrt}
\end{document}
~~~
{: .latex}


> ## Bibliographies exercise
> Change the citation style in the text above to unsrt
> Some publishers will export bibtex from their websites that you can include in your database. Find the BibTeX for the paper "Soft Hair on Black Holes" by Stephen Hawking and add it to your database.
> Cite Hawking's Paper in your text
> > ## Solutions
> > Hawking's paper's Bibtex can be found at [https://journals.aps.org/prl/export/10.1103/PhysRevLett.116.231301](https://journals.aps.org/prl/export/10.1103/PhysRevLett.116.231301)
> > The code to cite it will be \cite{PhysRevLett.116.231301} (assuming you didn't change the key's name)
> {: .solution}
{: .challenge}



