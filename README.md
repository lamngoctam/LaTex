## Setting up the Latex

1. Download and set up MikTex from https://miktex.org/download
2. Download and set up text editor: TexMaker from https://www.xm1math.net/texmaker/download.html
3. Fix error with bibliography: 
- [ ] **For bibtex**
  - Change BibTeX.exe to Biber.exe from Options -> Configure TexMaker -> TEX Commands -> Bib(la)Tex. Example: "C:/Users/19107262/AppData/Local/Programs/MiKTeX 2.9/miktex/bin/x64/biber.exe" %"
    - [ ] `\usepackage{biblatex}`
    - [ ] `\addbibresource{citation.bib}  `  
    - [ ] `\begin{document}`    
    - [ ] ` ....    `
    - [ ] `\printbibliography    `
    - [ ] `\end{document}`
 - [ ] **For biber**
4. References:
- https://tex.stackexchange.com/questions/406205/no-citation-bibdata-or-bibstyle-commands
- https://tex.stackexchange.com/questions/154751/biblatex-with-biber-configuring-my-editor-to-avoid-undefined-citations
- https://www.overleaf.com/learn/latex/Articles/Getting_started_with_BibLaTeX
- https://tex.stackexchange.com/questions/25701/bibtex-vs-biber-and-biblatex-vs-natbib/299286#299286
5. Guide for writing Thesis on LaTex:
https://www.dickimaw-books.com/latex/thesis/thesis-screen.pdf
6. Bib LaTex Package:
https://www.emse.fr/~picard/files/biblatex.pdf

## Running Sagemath in TexMaker
1. Install miktex 2.9 64-bit, full install.
2. Install TexMaker 64-bit, full install.
3. Install Sagemath from http://www.sagemath.org/
4. VIP step: This can be done copying al files in *c:\Program Files\SageMath 8.9\runtime\opt\sagemath-8.6\local\share\texmf\tex\latex\sagetex* into *c:\Program Files\MiKTeX 2.9\tex\latex\sagetex* or *C:\Users\19107262\AppData\Local\Programs\MiKTeX 2.9\tex\latex\sagetex*

5. \usepackage{sagetex} in Latex
6. Open Sagemath 8.9, NOT Sagemath 8.9 Shell or Sagemat 8.6 Notebook. 
7. Using 'cd'&'ls' command to find the Latex folder.
8. Run load('fileName.sagetex.sage') in Sagemath Console : fileName is the same file name of Latex, but *.sagetex.sage
9. Compile Latex file again in TexMaker
  
  - Example: From http://www.sagemath.org/tour-research.html
  - Ref: https://ask.sagemath.org/question/39812/how-to-use-sagetex-with-windows/
