# MMT LaTeX Helpers

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)

LaTeX utility macros for typesetting papers and theses involving the [MMT Language](https://uniformal.github.io/) including

- an `mmttheory` environment (see image below)
- macros for typesetting simply- and dependently-typed function types (arrows, Pis), functions (lambdas), and function applications in different variants all with nice spacing:
  - basics: `\to` (LaTeX built-in), `\tpi{x}[A] B` (for `\Pi x\colon A.\ B`), `\lam{x}[A]` (for `\lambda x\colon A.\ `)
  - variadic (with nice spacing and ldots): `\flexFun`, `\flexPi`, `\flexApp` (for application)
  - doubly, triply variadic (e.g. to ultimately typeset `\Pi a \Pi b \Pi c ... \Pi d \Pi e \Pi f`): `\flexDoublePi`, `\flexTriplePi`
  - each variant (Pis, lambdas) accepts types of the variables as optional arguments
  - each variant supports (Pis, lambdas) accepts multiple variables too (e.g. `\lam{a b}[T]` to typeset `\lambda a\,b\colon T`)
  - and more stuff
- macros for typesetting various FOL and SFOL stuff

## Installation

1. Get ahold of this repository's files, e.g. via [git subrepo](https://github.com/ingydotnet/git-subrepo):

   ```bash
   > git subrepo clone https://github.com/ComFreek/mmt-latex-helpers.git mmt-latex-helpers
   ```
2. Include the file `all.tex` in your LaTeX document:

   ```tex
   \RequirePackage{import}
   \subimport{mmt-latex-helpers/}{all}
   ```
   
   Here, we use the `subimport` command from the `import` package to allow `all.tex` to include files relatively to its containing directory.
   E.g. `all.tex` contains an `\input{terms}`, which would fail if we didn't use `subimport` above.

3. Test by writing `$\lam{x}[S] t$` somewhere in your document. This should render as `λx: S. t`.

## Minimal Working Example

Assuming you performed step 1 of the installation above, the following should compile fine with any TeX distribution:

```tex
\documentclass[]{article}

\RequirePackage{import}
\subimport{mmt-latex-helpers}{all}

\begin{document}

\begin{mmttheory}{T}
	S & \type\\
	T & \type\\
	t & T\\
	c & S \to T\\
	d & S \to T\mmtdef
	    \lam{s}[S] c\ s
\end{mmttheory}

\end{document}
```

## Documentation

So far no shiny external documentation is available; you have to read the inline documentation in source, unfortunately 😀

## Partial Documentation Attempt

![Imgur](https://imgur.com/gpokLNm.png)

```
\makecn{Unital}
\makecn{neut}

\begin{mmttheory}{\Unital}
    \mmtinclude{\SFOL}
    U      & \tp\\
    \circ  & \tm{U} \to \tm{U} \to \tm{U}\\
    e      & \tm{U}\\
    \neut  & \ded \fall{x}[\tm{U}] e \circ x \doteq x
\end{mmttheory}
```
