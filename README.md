> **IMPORTANT NOTE**: this project has [moved to Codeberg](https://codeberg.org/harisont/lucid).

# lucid
A modern Beamer theme you can use without installing dozens of CTAN packages.

I really, really hate all PowerPoint-like programs but also dislike most Beamer templates, so back in my third year of university I invested one night in making my own.
I didn't understand anything about CTAN packages, `.sty` files and `tikz` (and to a large extent I still don't), but [Beamer-Theme-Execushares](https://github.com/hamaluik/Beamer-Theme-Execushares) provided an excellent starting point and the resulting theme served me well throughout the last 5 years - I only recently switched to my current institution's (Språkbanken Text, University of Gothenburg) colors and logo and fixed a few things that kept annoying me. 
There are still a few [issues](https://github.com/harisont/Beamer-mhthm/issues) I'd like to address, but because I find writing style files to be a nightmare PRs are more than ever welcome.  

## Usage
You can of course use lucid to write your presentations in LaTeX and compile them with `pdflatex`. 
A fairly standard `texlive` installation should provide everything you need, as the only package required is `tikz`.

### If you hate writing presentations in LaTeX
However, __I warmly recommend that you write your presentations in Markdown and generate beamer slides with [pandoc](https://github.com/jgm/pandoc)__.
This is a much easier way to obtain perfectly fine slides in 99% of the cases, and allows for LaTeX injections that fix the remaining 1% of things that you can't express in Markdown. 
For instance, you can add a `\pause` wherever you want.

I usually just write regular Markdown using `#` for each new section and `##` for each new slide, add a metadata section in the beginning of the file, for instance

```yaml
---
title: "The title"
subtitle: "a possibly very long subtitle" # OPTIONAL
author: "My Name" # OPTIONAL
theme: "lucid"
logo: "gu.png" # OPTIONAL - if present, it should as of now be the path to a 300x300 image
date: "the date" # OPTIONAL - will appear on the title page on the bottom right
institute: "Språkbanken Text, University of Gothenburg" # OPTIONAL
---
```

and then run 

```
pandoc slides.md -t beamer --slide-level 2 -o slides.pdf
```

to generate the PDF.

See [`slides.pdf`](slides.pdf) for some example pandoc-generated slides and [`slides.md`](slides.md) to take a look at the very simple source code.

For further information about the pandoc + beamer combo, I think [alexeygumirov](https://github.com/alexeygumirov/pandoc-beamer-how-to) is the most exhaustive source. A more compact tutorial is available [here](https://ashwinschronicles.github.io/beamer-slides-using-markdown-and-pandoc?utm_source=pocket_reader). 

## Namesake
In Italian, _lucidi_ is the word that indicates slides meant for old-fashioned overhead projectors.
Not to mention that having a quick and simple way to generate acceptable-looking slides greatly helps me _mantenere la luciditá_ (stay sane).
