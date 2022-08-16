shapeR
======

R package to study otolith shape variation among fish populations

##Shape R has recently been archived (June 2022) and so the following is to be able to install the package from the archived file

##download Rtools installer from CRAN - https://cran.r-project.org/bin/windows/Rtools/rtools40.html
## after installation create .txt document named .Renviron in documents folder with the following line:

PATH="${RTOOLS40_HOME}\usr\bin;${PATH}"

##open R and code

write('PATH="${RTOOLS40_HOME}\\usr\\bin;${PATH}"', file = "~/.Renviron", append = TRUE)

##restart R and perform the following tests
##verify that make can be found, which should show the path to your Rtools installation.

Sys.which("make")
## "C:\\rtools40\\usr\\bin\\make.exe"

##test package installation

install.packages("jsonlite", type = "source")

##to install shapeR use the following steps 

##create pathway 

install.packages("devtools")
library(devtools)
url = "https://cran.r-project.org/src/contrib/Archive/shapeR/shapeR_0.1-5.tar.gz"
pkgFile = "shapeR_0.1-5.tar.gz"
download.file(url=url, destfile = pkgFile)

##download dependencies

install.packages(c("gplots", "jpeg", "pixmap", "wavethresh", "vegan"))

##install package

install.packages(pkgs=pkgFile, type="source", repos=NULL)
unlink(pkgFile)

library(shapeR)
