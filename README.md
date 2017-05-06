# Wireless Networking in the Developing World [WNDW](http://wndw.net/)

Digital source copy, forkable under [CC-BY-SA license](http://creativecommons.org/licenses/by-sa/3.0/).

## Contents

This repository contains:

* WNDW source file _translator's version_ (.odt)
* WNDW html file saved by libreoffice from .odt (.html)
    * A cleaned version is also available with relative urls.
        * With VIM, I used `:%s/src="\./src="src/g`
* WNDW markdown file converted using following procedure (.md)
    * [Install Pandoc](http://johnmacfarlane.net/pandoc/installing.html)
    * Execute `cat src/WNDW_UsTrade6_master#1.42.html | pandoc -s -r html -o wndw.md +RTS -K500M -RTS`
        * The `+RTS -Ksize -RTS` is to handle a haskell stack space overflow by bumping a memory limit up. Here one needs 500M of memory available.
    * Do a search/replace to update image locations in markdown.
        * With VIM, I used `:%s/\!\[\](\./\!\[\](src/g`
    * Using a terminal, run the command  
	``` cd /src`````
	```find /src/* -type f-iname ".png" -exec mv --backup=numbered -t .//images {} +```
	```find /src/* -type f-iname ".pdf" -exec mv --backup=numbered -t .//images {} +```
	This moves all images into a root directory of images for easy of portability.
    * Then we must use a text editor to change the links in the markdown file to point to the new folder. Regex below.
    ```\(src/.*/```
* WNDW mediawiki markup file converted from markdown (.wiki)
    * Execute `cat wndw.md | pandoc -s -S -r mediawiki -o wndw.wiki`
