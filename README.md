# Customizable template of Cover Letter and CV in LaTeX

Este repositório hospeda o código-fonte, em
[LaTeX](http://www.latex-project.org/), e a versão final, em PDF, de
meu currículo.

Sinta-se à vontade para utilizar a estrutura (e não os dados) em seu currículo,
sob os termos da licença [GPL 2](http://www.gnu.org/licenses/gpl-2.0.html).


Requisitos
----------

Você necessita de alguma distribuição do LaTeX para compilar o código-fonte.
Caso utilize Debian ou derivados (como Ubuntu), basta rodar como root:

    aptitude install texlive

Caso você não tenha o `aptitude` instalado, execute (também como root):

    apt-get install aptitude


Compilação
----------

Para compilar seu currículo, basta rodar:

    pdflatex nome-do-arquivo-fonte.tex

Ou utilizar o `Makefile`, que já compila e limpa os arquivos indesejados
(`\*.aux` e `\*.log`):

    make

## Description

**Customizable CV template**, `mateus-cv`, allow you to choose **color themes**, display or not some personal information (age, address, pictures, etc.) with respect to **English and French convention**, define some sections on left bar (skills, etc.), and define some sections in the body (education, experience, etc.) of the CV.

**Customizable cover letter template**, `mateus-cover-letter`, is classical with the same **header** than the CV template. The template allow **English conventions** (address and date at right and recipient information at left) and **French conventions** (address and date at left, and recipient information at right).

___

## Example preview

### English version

With respect to English conventions (without age, address and picture).

___

### French version

With respect to French conventions (with picture, address and age).
___

## Customized colors

The default theme color of CV and cover letter is different kind of blue, but you can freely custom themes color, see below some non-exhaustive examples:


### Green

``` latex
\usepackage{xcolor}
\definecolor{leftcolorband}{HTML}{d0f0c0}
\definecolor{boxcolor}{HTML}{59762f}
\definecolor{maincolor}{HTML}{556b2f}
\definecolor{secondcolor}{HTML}{85b145}
\definecolor{thirdcolor}{HTML}{6b8e23}
```

### Red

``` latex
\usepackage{xcolor}
\definecolor{leftcolorband}{HTML}{e0e0e0}
\definecolor{boxcolor}{HTML}{851919}
\definecolor{maincolor}{HTML}{420c0c}
\definecolor{secondcolor}{HTML}{861919}
\definecolor{thirdcolor}{HTML}{591111}
```

### Grey

``` latex
\usepackage{xcolor}
\definecolor{leftcolorband}{HTML}{e0e0e0}
\definecolor{boxcolor}{HTML}{606060}
\definecolor{maincolor}{HTML}{484848}
\definecolor{secondcolor}{HTML}{909090}
\definecolor{thirdcolor}{HTML}{606060}
```

### Yellow

``` latex
\usepackage{xcolor}
\definecolor{leftcolorband}{HTML}{fef2bf}
\definecolor{boxcolor}{HTML}{bfa100}
\definecolor{maincolor}{HTML}{5f5000}
\definecolor{secondcolor}{HTML}{e1b400}
\definecolor{thirdcolor}{HTML}{7f6b00}
```

___

## CV environment style and commands

This template is divided in three parts:
  - The **header** where you can define some personal information;
  - The **left bar** to display some skills or other;
  - The **body** of your CV to display your experiences, educations, etc.

The left bar and body must be each one in a `minipage` environment with respectively `0.37\textwidth` and `0.61\textwidth` parameters.
You can look one of the following examples: `example_cv.tex`, `Mateus_Macedo_CV_Fr.tex` or `Mateus_Macedo_CV_En.tex`

### Header

Set personal information (if you don't want to display one (or several) personal information let the command empty):

``` latex
\profilepic{path/picture}
\cvname{Your Name}
\cvlinkedin{/in/your-linkedin}
\cvgithub{YourGitHub}
\cvmail{your.address@email.com}
\cvnumberphone{your phone number}
\cvaddress{Your address}
\cvjobtitle{Title of your CV}
\cvsite{www.your-website.com}
\cvyearsold{your years old}
```

### Left bar

Set section in left bar:

``` latex
\sectionleft{Title of this section}
```

Set items in left bar:

``` latex
\subsectionleft{Item name}{Optional description}
```

### Body

Set body section:

``` latex
\section{Title of this section}
```

Set items in body:

``` latex
\begin{rightenv}
  \subsectionright{year}[1st optional argument]{title of item}[2nd optional argument][3rd optional argument]{Description of item}
  \subsectionright{Date}[Level degree]{Title}[University][Location]{Description}
  \subsectionright{Date}{Title job}[Firm][Location]{Description}
\end{rightenv}
```

___

## Cover letter environment style and commands

### Header

Set personal information (if you don't want to display one (or several) personal information let the command empty):

``` latex
\profilepic{path/picture}
\cvname{Your Name}
\cvlinkedin{/in/your-linkedin}
\cvgithub{YourGitHub}
\cvmail{your.address@email.com}
\cvnumberphone{your phone number}
\cvjobtitle{Title of your CV}
\cvsite{www.your-website.com}
```

### Address and recipient

#### English convention

Address, date, and location are set at top right and the recipient is set at left.

``` latex
\address{John \capit{DOE},\\123, somestreet\\Somecity}
\recipient{Sir \capit{COMPANY},\\456, somestreet\\Somecity}
\location{Somecity, \today}
```

#### French convention

Address, date and location are set at top left and the recipient is set at right.

``` latex
\addressfr{John \capit{DOE},\\123 rue des Avenue\\Ville}
\recipientfr{Monsieur \capit{COMPANY},\\456 avenue des Rues\\Ville}
\locationfr{Ville, \today}
```

### Body

``` latex
\begin{coverletter}
  \subject{Application to job of my life}
  \opening{Dear Sir or Madam,}
  % write here the letter body
  \closing{Your sincerly,} % To adapt following recipient
  \signing{John \capit{DOE}}
\end{coverletter}
```

___

## Requirements

- Compile with **XeLaTex** or **LuaLaTeX**.

- LaTeX packages:

  - fontspec;
  - ClearSans;
  - fontawesome;
  - ragged2e;
  - parskip;
  - hyperref;
  - textpos;
  - titlesec;
  - tikz;
  - xcolor;
  - multirow;
  - xargs;
  - tcolorbox;
  - enumitem;
  - ifthen.

___
# AltaCV, yet another LaTeX CV/Résumé class

v1.1.4 (27 July 2018), by LianTze Lim (liantze@gmail.com)

(Thanks to [Nur](https://github.com/nurh) for the name.)

It all started with this:

[<img src="tweet-that-started-this.png" width="500px">]
(https://twitter.com/Leonduck/status/764281546408923136)

Leonardo was talking about a [résumé of Marissa Mayer that Business Insider put together](http://www.businessinsider.my/a-sample-resume-for-marissa-mayer-2016-7/) using [enhancv.com](https://enhancv.com).
I _knew_ I had to do something about it. And so AltaCV was born.

## Samples

This is how the re-created résumé looks like ([view/open on Overleaf](https://www.overleaf.com/read/gtqfpbwncfvp)):

<img src="mmayer.png" alt="Marissa Mayer's résumé, re-created with AltaCV" width="600px">

Though if you're creating your own CV/résumé, you'd probably prefer using the basic template ([view/open on Overleaf](https://www.overleaf.com/read/trgqjpwnmtgv)):

<img src="sample.png" alt="sample barebones AltaCV template" width="600px">


## Requirements and Compilation

* pdflatex + biber + pdflatex
* AltaCV uses [`fontawesome`](http://www.ctan.org/pkg/fontawesome) and [`academicons`](http://www.ctan.org/pkg/academicons); they're included in both TeX Live 2016 and MikTeX 2.9.
* Loading `academicons` is optional: enable it by adding the `academicons` option to `\documentclass`.
* Can now be compiled with pdflatex, XeLaTeX and LuaLaTeX!
* However if you're using `academicons`, you _must_ use either XeLaTeX or LuaLaTeX. If the doc then compiles but the icons don't show up in the output PDF, try compiling with LuaLaTeX instead.
* The samples here use the [Lato](http://www.latofonts.com/lato-free-fonts/) font.


## MIT License

Copyright (c) 2020-2021 Mateus Macedo

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

## Dúvidas

Insira uma _Issue_ neste projeto :-)

## 👨🏻‍🚀 Sobre mim
<a href="https://www.linkedin.com/in/mateus-macedo-937a32163/">
 <img style="border-radius:50%" width="100px; "src="https://avatars.githubusercontent.com/u/63172367?s=460&u=11fd26ea8a7f5663d7707d7ef254e4f8bfca1b05&v=4"/>
 <p>Mateus Macedo</p>
</a>
