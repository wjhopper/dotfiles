local({r <- getOption("repos")
      r["CRAN"] <- "https://cran.revolutionanalytics.com"
      options(repos=r)})

if(.Platform$OS.type == "unix") {
  Sys.setenv("R_HISTFILE" = file.path(Sys.getenv("HOME"), ".Rhistory"))
}   else if (.Platform$OS.type == "windows") {
  Sys.setenv("R_HISTFILE" = file.path(Sys.getenv("USERPROFILE"), ".Rhistory"))
}

options(stringsAsFactors=FALSE)
options(max.print=100)
options(scipen=10)
options(prompt="> ")
options(continue="... +  ")
options(width = 80)

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

attach(.env)

message("\n*** Successfully loaded .Rprofile ***\n")
