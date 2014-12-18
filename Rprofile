local({r <- getOption("repos")
      r["CRAN"] <- "http://cran.revolutionanalytics.com"
      options(repos=r)})

options(stringsAsFactors=FALSE)
options(max.print=100)
options(scipen=10)
options(prompt="> ")
options(continue="... +  ")
options(width = 80)
options(contrasts = c("contr.helmert", "contr.poly"))
q <- function (save="no", ...) {
  quit(save=save, ...)
}


.env <- new.env()

.env$unfactor <- function(df){
  id <- sapply(df, is.factor)
  df[id] <- lapply(df[id], as.character)
  df
}

.env$refactor <- function(df){
  id <- sapply(df, is.factor)
  df[id] <- lapply(df[id], as.character)
  df
} 

.env$getMyPath <- function() {
#initial.options <- commandArgs(trailingOnly = FALSE)
#file.arg.name <- "--file="
#script.name <- sub(file.arg.name, "", initial.options[grep(file.arg.name, initial.options)])
#script.basename <- dirname(script.name)
#return(script.basename)

frame_files <- lapply(sys.frames(), function(x) x$ofile)
frame_files <- Filter(Negate(is.null), frame_files)
PATH <- dirname(frame_files[[length(frame_files)]])
return(PATH)


#whereFrom=sys.calls()[[1]]
#print(whereFrom)
## This should be an expression that looks something like
## source("pathname/myfilename.R")
#whereFrom=as.character(whereFrom[2]) # get the pathname/filename
#print(whereFrom)
#whereFrom=paste(getwd(),whereFrom,sep="/") # prefix it with the current working directory
#print(whereFrom)
#pathnameIndex=gregexpr(".*/",whereFrom) # we want the string up to the final '/'
#print(pathnameIndex)
#pathnameLength=attr(pathnameIndex[[1]],"match.length")
#print(pathnameLength)
#whereFrom=substr(whereFrom,1,pathnameLength-1)
#print(whereFrom) # or "setwd(whereFrom)" to set the working directory
}

attach(.env)

message("\n*** Successfully loaded .Rprofile ***\n")
