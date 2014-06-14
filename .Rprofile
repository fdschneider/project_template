
# function calling pandoc

pandoc <- function(source = "manuscript.md", output = "manuscript.pdf", directory = "manuscript/", biblio = "assets/biblio.bib", style= "assets/pnas.csl", template = "assets/pretty.template", other = NULL) {
  wd <- getwd()
  setwd(paste0(wd,"/", directory))
  
  if(!is.null(biblio)) biblio <- paste0(" --bibliography ",  biblio)
  if(!is.null(style)) style <- paste0(" --csl ",  style)
  if(!is.null(template)) template <- paste0(" --template ",  template)
  
  system(paste0("pandoc -S ",  source, biblio, style, template, other, " -o ",  output ))
  setwd(wd)
}


## md to html
options(rstudio.markdownToHTML = 
          function(inputFile, outputFile) {      
            system(pandoc( inputFile, outputFile, directory = NULL, template = NULL , other = " -s --mathjax --css custom.css ") )
          }
)  

# pandoc("manuscript.md", "manuscript.html", template = NULL )

pandoc_doc <- function() system(pandoc( "manuscript.md", "manuscript.docx", template = NULL , other = " -s -S -m ") )
