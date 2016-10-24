local({r <- getOption("repos")
      r["CRAN"] <- "https://cran.revolutionanalytics.com"
      options(repos=r)})

if(.Platform$OS.type == "unix") {
  home <- Sys.getenv("HOME")
}   else if (.Platform$OS.type == "windows") {
  home <- Sys.getenv("USERPROFILE")
}

Sys.setenv("R_HISTFILE" = file.path(home, ".Rhistory"))

options(stringsAsFactors=FALSE)
options(max.print=100)
options(scipen=10)
options(prompt="> ")
options(continue="... +  ")
options(width = 80)

.localenv <- new.env()

.localenv$q <- function (save="no", ...) {
  quit(save=save, ...)
}
.localenv$unfactor <- function(df){
  id <- sapply(df, is.factor)
  df[id] <- lapply(df[id], as.character)
  df
}

.localenv$refactor <- function(df){
  id <- sapply(df, is.factor)
  df[id] <- lapply(df[id], as.character)
  df
}

.localenv$home <- home
rm(home)

suppressMessages(attach(.localenv))

message("\n*** Loaded WhoppeR's .Rprofile ***\n")
