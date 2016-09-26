# datapasta

datapasta is about reducing resistance associated with copying and pasting data into R Studio. It is a response to the realisation that I often found myself using Sublime as an intermediate text munging step when copying data. Hopefully addins in this package will remove such intermediate steps from our copy-pasta workflows.  

At the moment this package contains functional versions of these R Studio addins:
* `tribble_paste()` which pastes a table on the clipboard as a nicely formatted call to `tribble()`
    - Recomend `ctrl + shift + t` as shortcut.
* `vector_paste()` which will paste delimited data as a character vector definition, e.g. `c("a", "1")` etc.
    - Recommend `ctrl + shift + v` as shortcut.

# Pitfalls

* Data is not parsed from string to any other format. This is challenging to do robustly in an efficient manner. Ideas on this are welcome!
* `tribble_paste` works well with csv's, plain excel files, and html tables, but is currently brittle with respect to irregular table structures like merged cells. 
* Some kinds of Excel formatting can trip up `tribble_paste`, I am working on diagnosing this issue currently.

##Installation

1. Get the package: `devtools::install_github("milesmcbain/datapasta")`
2. Set the keyboard shortcuts using **Tools** -> **Addins** -> **Browse Addins**, then click **Keyboard Shortcuts...**

##Prior art

This package is made mpossible by [mdlincon's clipr](https://github.com/mdlincoln/clipr) and [hadley's tibble](https://github.com/hadley/tibble). I especially appreciate `clipr's` thoughtful approach to the clipboard on Linux, which pretty much every other R clipboard package just nope'd out on. 
