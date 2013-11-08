# Wireless Networking in the Developing World (WNDW)

Digital source copy, forkable under [CC-BY-SA license](http://creativecommons.org/licenses/by-sa/3.0/).

## Contents

This repository contains:

* WNDW source file __translator's version__ (.odt)
* WNDW html file saved by libreoffice from .odt (.html)
* WNDW markdown file converted using following procedure (.md)
    * [Install Pandoc](http://johnmacfarlane.net/pandoc/installing.html)
    * Execute `cat WNDW_UsTrade6_master#1.42.html | pandoc -s -r html -o wndw.md +RTS -K500M -RTS^C`
        * The `+RTS -Ksize -RTS` is to handle a haskell stack space overflow by bumping a memory limit up. Here one needs 500M of memory available.
