This small repository contains a LaTeX Preamble with settings for Computer
Science handins together with a document with examples of use of all the
different packages in the preamble together with a template to get a new
document started quicker.

> THIS IS A MAJOR REWRITE OF THE PREAMBLE! This does include multiple breaking
> changes. Your old version most likely does not at all compile any more. You
> can find the old version at commit `782d91460e2ba6f9c1c6a1c83b255decc7fb6dcc`
> or on the branch `version/v1`.

# Preamble
The preamble is made in two parts, with the intent to divide the settings
between the general and the localisation specific settings. This is only of
value, should you write your .tex document in various languages.
- `base_p1`, `base_p2`: Packages and most settings (the second part is to be
  executed after localisation)
- dk/en: Settings specifically for localisation to danish (dk) or english (en).
  The underlying preamble

When importing the preamble you have to only import the localised .tex file,
since there's already a call to the base settings within both. How you import it
depends on where you have the preamble files located compared to your document.

## Same folder
```tex
\documentclass[a4, english]{article}
\input{preamble_en.tex}
```

## Absolute path
On Windows
```tex
\documentclass[a4, english]{article}
\usepackage{import}
\import{C:/GitHub/LaTeX_Preamble_and_Examples/preamble/}{preamble_en.tex}
```

On Unix
```tex
\documentclass[a4, english]{article}
\usepackage{import}
\import{/home/username/Documents/LaTeX_Preamble_and_Examples/preamble/}{preamble_en.tex}
```

## Relative path
```tex
\documentclass[a4, english]{article}
\usepackage{import}
\subimport{../preamble/}{preamble_en.tex}
```

# Documents
In the `documents` folder you can find multiple documents: _template_X.tex_,
and _example.tex._
## template_report.tex, template_dissertation.tex and template_blank.tex
To quickly get started, this repository contains three templates:

- *template_blank.tex*: The most bare bones template, which is set up for
  writing handins as part of the coursework.
  
- *template_report.tex*: For writing larger reports as the culmination of a
  course. This one closely resembles a generic template to write an article.
  
- *template_dissertation.tex*: For when you (knock on wood), need to write a
  very long dissertation in multiple parts and many chapters.

![Alt text](/img/template.png?raw=true "The template file")

With *template_blank.tex* you simultaneously have a completely blank document
with nothing more than just the title.

## examples.tex
A slowly growing document with explanations and examples of using the various
packages in the preamble. They are all made with the intent to be reverse
engineerable.

![Alt text](/img/example.png?raw=true "The template file")

# Python Template Generator
> This one has yet not been updated for the major rewrite. I never personally
> used it, so I have not much inclination to maintain it.

In the folder Python you can find a Python Template Generator, created by
Kristian 'Yurippe' Gausel. *prepare.py* is the file that creates *latexgen.py*
and packs the template and the *preamble_en*, *preamble_dk* and *preamble_base*
into *latexgen.py* to create a standalone script to generate a template from

This is especially useful for ShareLatTeX since you can add a --zip argument to
zip the template into a ShareLaTeX compatible format for easy upload.

The *latexgen.py* file can be found under
[Releases](https://github.com/SSoelvsten/LaTeX-Preamble_and_Examples/releases)
