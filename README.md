# Assignment Template — Quick Guide for TAs/Tutors

This LaTeX template provides a common format for course assignments and is intended to be used with **Overleaf**.

Before editing an assignment, make sure the project compiler is set to **XeLaTeX** in Overleaf:

**Menu → Settings → Compiler → XeLaTeX**

Overleaf handles the required compilation steps automatically.

## 1. Update the Assignment Title

For each assignment, update the title near the beginning of the `.tex` file:

```latex
\newcommand{\AssignmentTitle}{Homework N: Assignment Title}
```

The title is automatically used in the document title and page header.

## 2. TA/Tutor Notes

Information intended only for teaching staff should be enclosed in:

```latex
\begin{tutornote}
Explain the teaching point, expected answer, common misconception,
or other guidance for TAs/Tutors here.
\end{tutornote}
```

These notes appear in the teaching edition and are completely removed from the student edition. Student-facing instructions should therefore remain outside the `tutornote` environment.

The notes may contain ordinary LaTeX content, including paragraphs, lists, and mathematical expressions.

For example:

```latex
\begin{tutornote}
Students may confuse the asserted information with the inferred result.

Emphasize the following distinction:

\[
\text{asserted facts}
\longrightarrow
\text{reasoning}
\longrightarrow
\text{inferred facts}.
\]
\end{tutornote}
```

## 3. Mathematical Expressions

Use standard LaTeX math mode for mathematical or formal expressions.

For an inline expression:

```latex
The class expression \(A \sqcap B\) denotes an intersection.
```

For a displayed expression:

```latex
\[
\mathsf{DerivedEntity}
\equiv
\mathsf{BaseEntity}
\sqcap
\exists\,\mathsf{relevantRelation}.\mathsf{RelatedEntity}
\]
```

Use `\mathsf{...}` where appropriate for formal class, relation, or ontology names.

For more mathematical notation, see the [Overleaf guide to mathematical expressions](https://www.overleaf.com/learn/latex/Mathematical_expressions).

## 4. References and Bibliography

Bibliographic entries are stored in `refs.bib`.

Add a reference to `refs.bib` using a standard BibLaTeX entry, for example:

```bibtex
@article{smith2026example,
  author  = {John Smith and Jane Doe},
  title   = {An Example Article},
  journal = {Journal of Example Studies},
  year    = {2026},
  volume  = {10},
  number  = {2},
  pages   = {100--110}
}
```

The identifier `smith2026example` is the citation key. Cite the reference in the assignment with:

```latex
This approach has been discussed in previous work
\cite{smith2026example}.
```

Multiple references may be cited together:

```latex
\cite{smith2026example,doe2025example}
```

The bibliography is generated automatically from the cited entries in `refs.bib`. Overleaf handles Biber and the necessary recompilation automatically.

For additional information, see the [Overleaf guide to bibliography management with BibLaTeX](https://www.overleaf.com/learn/latex/Bibliography_management_with_biblatex).

## 5. Teaching and Student Editions

The same `.tex` source is used to generate both editions.

Near the beginning of the file, use:

```latex
\tutornotestrue
```

to generate the **TA/Tutor teaching edition**, including all `tutornote` content.

Change it to:

```latex
\tutornotesfalse
```

to generate the **student edition**.

When `\tutornotesfalse` is selected, all `tutornote` environments are completely omitted from the compiled PDF without leaving additional space.

Before releasing an assignment to students:

1. change the switch to `\tutornotesfalse`;
2. click **Recompile** in Overleaf;
3. inspect the resulting PDF to ensure that no teaching notes remain.

## 6. Other LaTeX Syntax

The existing template should normally be used as the primary reference: copy and modify existing examples of sections, lists, tables, equations, code listings, hyperlinks, and citations rather than redefining the document formatting.

For LaTeX syntax not demonstrated in the template, consult the Overleaf documentation:

- [Learn LaTeX in 30 minutes](https://www.overleaf.com/learn/latex/Learn_LaTeX_in_30_minutes)
- [Mathematical expressions](https://www.overleaf.com/learn/latex/Mathematical_expressions)
- [Lists](https://www.overleaf.com/learn/latex/Lists)
- [Tables](https://www.overleaf.com/learn/latex/Tables)
- [Code listing](https://www.overleaf.com/learn/latex/Code_listing)
- [Hyperlinks](https://www.overleaf.com/learn/latex/Hyperlinks)
- [Bibliography management with BibLaTeX](https://www.overleaf.com/learn/latex/Bibliography_management_with_biblatex)