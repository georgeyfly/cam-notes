# VScode-LaTex Setup for Mac

Note: This is only for Mac users
## Step 1. Download & Install TeX Live
Download `MacTex.pkg` [here](https://mirror.ctan.org/systems/mac/mactex/MacTeX.pkg)

## Step 2. Setup PATH

```bash
# 1. Open your shell configuration file with nano
nano ~/.zshrc

# 2. Add the following line to include TeX binaries in your PATH
export PATH="/Library/TeX/texbin:$PATH"

# 3. After saving and exiting nano, reload your configuration
source ~/.zshrc
```

## Step 3. Download & Install Visual Studio Code

## Step 4. Install & Configure LaTeX Workshop

copy paste this snippets into `json` file
<details>
    <summary>Click to expand JSON</summary>

```json
"latex-workshop.latex.tools": [
       {
           "name": "xelatex",
           "command": "xelatex",
           "args": [
             "-synctex=1",
             "-interaction=nonstopmode",
             "-file-line-error",
             "%DOC%"
           ]
       },
       {
           "name": "pdflatex",
           "command": "pdflatex",
           "args": [
             "-synctex=1",
             "-interaction=nonstopmode",
             "-file-line-error",
             "%DOC%"
           ]
       },
       {
           "name": "bibtex",
           "command": "bibtex",
           "args": [
             "%DOCFILE%"
           ]
       }
   ],

   "latex-workshop.latex.recipes": [
     {
       "name": "pdflatex -> bibtex -> pdflatex*2",
       "tools": [
         "pdflatex",
         "bibtex",
         "pdflatex",
         "pdflatex"
       ]
     },
       {
         "name": "XeLaTeX",
         "tools": [
           "xelatex"
         ]
       },
       {
         "name": "PDFLaTeX",
         "tools": [
           "pdflatex"
         ]
       }, 
       {
         "name": "latexmk",
         "tools": [
           "latexmk"
         ]
       },
       {
         "name": "BibTeX",
         "tools": [
           "bibtex"
         ]
       },
       {
         "name": "xelatex -> bibtex -> xelatex*2",
         "tools": [
           "xelatex",
           "bibtex",
           "xelatex",
           "xelatex"
         ]
       }
   ],
```

</details>






## Reference
[A Fast Guide on Writing LaTeX with LaTeX Workshop in VS Code](https://mathjiajia.github.io/vscode-and-latex/) 

[2024年LaTex常见编辑器汇总：优缺点及配置教程 （Texlive/VSCode/Overleaf）](https://zhuanlan.zhihu.com/p/607473890)