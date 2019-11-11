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
