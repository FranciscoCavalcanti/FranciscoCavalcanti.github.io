# CV source

LaTeX source for the CV that is embedded on the site
(`/#cv`, via `files/cv/Curriculum_Vitae_English.pdf`).

## Files
- `Curriculum_Vitae_English.tex` — the CV source (edit this).
- `CV.sty` — vendored custom style (defines the small-caps `\section` rule and
  the `CV` list environment). Kept here so the build is self-contained.
- `Curriculum_Vitae_English.pdf` — build output; **this is the exact file the
  site serves** for download and `<embed>`. No copying anywhere.

## Build
Requires a TeX distribution (MiKTeX/TeX Live) with `pdflatex`:

```bash
cd files/cv
latexmk -pdf Curriculum_Vitae_English.tex      # or: pdflatex Curriculum_Vitae_English.tex
latexmk -c                                      # (optional) remove .aux/.log/.out
```

That's it. The home page (`_pages/about.md`) links and `<embed>`s
`../files/cv/Curriculum_Vitae_English.pdf` — the same file `latexmk` just
produced. Rebuild, commit the updated PDF, and the site is up to date.
