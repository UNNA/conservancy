# Conservancy

## OVERVIEW

A utility for preserving websites on [mirrors.UNNA.org](http://mirrors.unna.org/). It is primarily a wrapper around `wget`, but performing additional verification tasks.

## PREREQUISITES

* `bash`
* [`curl`](https://curl.se/)
* [`jq`](https://stedolan.github.io/jq/)
* [`wget`](https://www.gnu.org/software/wget/)

## USAGE

Running `conserve <url>` will slowly and recursively mirror the page, plus sibling & child pages (but not parent pages), using `wget`.

The site will be archived into a directory named for the URL's hostname. A `wget` log file will also be generated.

Upon completion, it'll output the following to STDOUT:

* Any missing files (linking to Internet Archive's Wayback Machine if the files exist there, plus listing any similarly named files that were downloaded)
* Any files still containing links to the URL

One can then manually try to find & replace missing files, clean up links, etc.

## REFERENCE

* [curl(1)](https://curl.se/docs/manpage.html)
* [Wayback Machine API](https://archive.org/help/wayback_api.php)
* [Wget Manual](https://www.gnu.org/software/wget/manual/wget.html)
