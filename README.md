## Setting up the Latex

1. Download and set up MikTex from https://miktex.org/download
2. Download and set up text editor: TexMaker from https://www.xm1math.net/texmaker/download.html
3. Fix error with bibliography: 
  - Change BibTeX.exe to Biber.exe from Options -> Configure TexMaker -> TEX Commands -> Bib(la)Tex. Example: "C:/Users/19107262/AppData/Local/Programs/MiKTeX 2.9/miktex/bin/x64/biber.exe" %"
  - \usepackage{biblatex}
    \addbibresource{citation.bib}    
    \begin{document}    
    ....    
    \printbibliography    
    \end{document}
4. References:
- https://tex.stackexchange.com/questions/406205/no-citation-bibdata-or-bibstyle-commands
- https://tex.stackexchange.com/questions/154751/biblatex-with-biber-configuring-my-editor-to-avoid-undefined-citations
- https://www.overleaf.com/learn/latex/Articles/Getting_started_with_BibLaTeX
- https://tex.stackexchange.com/questions/25701/bibtex-vs-biber-and-biblatex-vs-natbib/299286#299286
5. Guide for writing Thesis on LaTex:
https://www.dickimaw-books.com/latex/thesis/thesis-screen.pdf
6. Bib LaTex Package:
https://www.emse.fr/~picard/files/biblatex.pdf
