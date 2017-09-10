## mdgBookSVGKit

**Here's an opportunity for one to "compose" minuets and to author a Collection Book!!!**

This folder contains materials that allow the user to author a book containing a collection of [Musical Dice Games (MDG)](https://en.wikipedia.org/wiki/Musikalisches_W%C3%BCrfelspiel) minuets, generated based on the rules given in  [*Musikalisches Würfelspiel, K.516f* (Mozart, Wolfgang Amadeus)](http://imslp.org/wiki/Musikalisches_W%C3%BCrfelspiel,_K.516f_(Mozart,_Wolfgang_Amadeus)).

To creat a book, simply [download](https://github.com/justineuro/mdgBookSVGKit/archive/master.zip) (or [clone](`git clone https://github.com/justineuro/mdgBookSVGKit.git`) this project) to one's computer, unzip the downloaded archive, and at the command line inside the main folder (`mdgBookSVGKit-master` directory) issue the following command (pre-requisites: `BASH`, `ABCMIDI`, `ABCM2PS`, `Ghostscript`, `Inkscape`, and `LaTeX`):

```shell
bash HOWTO
```

Wait for a **few** minutes, i.e., until one gets the bash prompt again.  The compiled book in PDF format (`mdgBookSVGv1.pdf`), among other things, should be located in the `res` folder (subdirectory).
  

## For the Impatient
To download and examine an example of a book (`mdgBookSVGv1_1.pdf`) that was generated in a similar manner, simply right-click (then "Save Link As ...") on the following image:

[![Front Cover](./mdgBookSVGv1-tit-125.jpg)](./mdgBookSVGv1_1.pdf)

(**Note**: To enable the MIDI audio links in the book, one should download [mdgBookSVG_1-midi.zip](./mdgBookSVG_1-midi.zip) and unzip in the same directory in one's computer that contains the book, i.e., the book and midi files have to be in the same directory).

## Important Parameters
To personalize one's generated book (in addition to the randomly generated minuets), one may want to change some of the default parameters/values in the following (all three files are initially found in the main directory but are eventually moved into the `res` folder): 

- `mdgBookSVGv1.tex` - (main latex file) see lines 35-45; also, one may have to occassionally change the \\topmargin and \\textheight values in lines 267 and 268, to ensure that each audio MIDI file will be on the same page as the corresponding musical score
- `mdgBookSVGv1-cover.tex`- makes the cover of the book; see lines 35-45 of `mdgBookSVGv1.tex` for default values
- `hyperref.cfg` - contains the `\hypersetup` keyvalues; one may wish to change the default value of `pdfauthor`, among other keyvalues; see the documentation for the TeX package `hyperref` for more information on these keyvalues.

Once the desired changes have been made to the files above, one can then re-compile the book by issuing, in the `res` subdirectoy, the last set of commmands in the HOWTO file:
```shell
pdflatex -synctex=1 -interaction=nonstopmode -shell-escape mdgBookSVGv1.tex
bibtex mdgBookSVGv1.aux
pdflatex -synctex=1 -interaction=nonstopmode -shell-escape mdgBookSVGv1.tex
pdflatex -synctex=1 -interaction=nonstopmode -shell-escape mdgBookSVGv1.tex
```

## Related Sites
- [Mozart](https://marian-aldenhoevel.de/mozart/) - A site maintained by Marian Aldenh&ouml;vel allows the visitor to generate a MDG (user-specified or randomly-generated) and the corresponding audio (<tt> midi</tt>, <tt>wav</tt>) and image files (<tt>pdf</tt>, <tt>png</tt>) based on *Musikalisches W&uuml;rferspiel, K. 516f*.
- [Opus Infinity](https://opus-infinity.org/) - Collaborative work of Robbert Harms, Hein Moors, and Suus van Petegem whose goal is to unravel the mystery behind the tables used for generating MDGs.  Site visitors can generate MDGs based on works of Kirnberger, Mozart, Stadler/Haydn), and Bach.  Corresponding audio files (<tt>mid</tt>, <tt>ogg</tt>, and/or <tt>mp3</tt>) and image files (<tt>pdf</tt> or <tt>png</tt>) are also made available for listening, viewing, or downloading.
- [Mozart](http://sunsite.univie.ac.at/Mozart/dice/) - A site maintained by John Chuang that allows the site visitor to generate MDGs based on the work of Stadler/Haydn.
- [`mozart.zip`](http://www.amaranthpublishing.com/MozartDiceGame.htm) -  This is a Windows software (&copy; 1995 VisionSoft) by John Chuang and Stephen Goodwin that generates MDG based on input from user and is available for <em> free</em> from  [Amaranth Publishing](http://www.amaranthpublishing.com/MozartDiceGame.htm). 
-  [Mozart - Musical Game in C K. 516f* (http://www.asahi-net.or.jp/~rb5h-ngc/e/k516f.htm)](http://www.asahi-net.or.jp/\~rb5h-ngc/e/k516f.htm), Mozart Studies Online - The site of Hideo Noguchi that offers an explanation linking <tt> Musikalisches W&uuml;rferspiel, K. 516f</tt> and <tt>K. 294d (K. Anh. C 30.01)</tt>.

## Acknowledgements
My sincerest gratitude to Chris Walshaw et al. for the [ABC music notation](http://www.abcnotation.com);  Jean-Francois Moine for [abcm2ps](http://moinejf.free.fr/) and the accompanying examples, templates, and pointers for the appropriate use of these resources;  Guido Gonzato for the [ABC Plus Project](http://abcplus.sourceforge.net/) and the [abcmidi resources](http://abcplus.sourceforge.net/#abcMIDI) available there, more especially for the ABC resource book *Making Music with ABC 2*; James R. Allwright and Seymour Shlien for [abcmidi](http://abc.sourceforge.net/abcMIDI) source and binaries; [Artifex, Inc.](https://artifex.com) for Ghostscript v.9.06 (includes the `ps2pdf` converter); [Inkscape v.0.48.5](https://www.inkscape.org) for the tool for converting SVGs to PDFs for inclusion into LaTeX documents; and, [<tt>User:Martin H</tt>](https://tex.stackexchange.com/users/632/martin-h) for his [reply](https://tex.stackexchange.com/questions/2099/how-to-include-svg-diagrams-in-latex) to a TeX/LaTeX Stack Exchange question on including SVGs into LaTeX documents.  Special thanks also to the [International Music Score Library Project (IMSLP)](http://imslp.org/) for making available the score for *Musikalisches Würfelspiel, K.516f* and [Amaranth Publishing](http://www.amaranthpublishing.com/MozartDiceGame.htm) for a copy of <tt>mozart.zip</tt>.  Ditto to Machtelt Garrels for the book [Bash Guide for Beginners](http://tldp.org/LDP/Bash-Beginners-Guide/html/Bash-Beginners-Guide.html), Vivek Gite for the book [Linux Script Shell Tutorial](http://www.freeos.com/guides/lsst/), Steve Parker for the [Unix/Linux Shell Cheatsheet](http://steve-parker.org/sh/cheatsheet.pdf).  John Fogarty's GitHub Site: [Latex CreateSpace BookCover](https://github.com/jfogarty/latex-createspace-bookcover) and Peter Wilson's reply in TeX/LaTeX Stack Exchange on [designing a book cover](https://tex.stackexchange.com/questions/17579/how-can-i-design-a-book-cover) were sources of ideas, information, and materials for creating the book cover and title page, thanks to both of them. Many thanks to the [Debian Project](https://www.debian.org) for the Debian 8 (Jessie) GNU/Linux OS, [TeXLive](http://www.tug.org/texlive/) for the TeX distribution, and [GitHub](https://github.org) for its generosity in providing space for [this project](https://github.com/justineuro/mdgBookSVGKit).

## License
<p xmlns:dct="http://purl.org/dc/terms/" xmlns:vcard="http://www.w3.org/2001/vcard-rdf/3.0#">
  <a rel="license"
     href="http://creativecommons.org/publicdomain/zero/1.0/">
    <img src="http://i.creativecommons.org/p/zero/1.0/88x31.png" style="border-style: none;" alt="CC0" />
  </a>
  <br />
  To the extent possible under law,
  <a rel="dct:publisher"
     href="https://github.com/justineuro">
    <span property="dct:title">Justine Leon A. Uro</span></a>
  has waived all copyright and related or neighboring rights to
  <span property="dct:title"><a href="https://github.com/justineuro/mdgBookSVGKit">mdgBookSVGKit</a></span>.
This work is published from:
<span property="vcard:Country" datatype="dct:ISO3166"
      content="PH" about="https://github.com/justineuro/mdgBookSVGKit">
  Philippines</span>.
</p>