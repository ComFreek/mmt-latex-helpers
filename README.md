# MMT LaTeX Helpers

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](http://makeapullrequest.com)

LaTeX utility macros for typesetting papers and theses involving the [MMT Language](https://uniformal.github.io/).

## Documentation

So far no shiny external documentation is available; you have to read the inline documentation in source, unfortunately 😀

## Partial Documentation Attempt

![Imgur](https://imgur.com/gpokLNm.png)

```
\makecn{Unital}

\begin{mmttheory}[\Unital]
    \mmtinclude{\SFOL}
    U      & \tp\\
    \circ  & \tm{U} \to \tm{U} \to \tm{U}\\
    e      & \tm{U}\\
    \neut  & \ded \fall{x}[\tm{U}] e \circ x \doteq x
\end{mmttheory}
```
