---
layout: post
title: "Vim spellcheck"
date: 2014-01-23 00:05:05 +0100
comments: true
categories: 
---

I've discovered today while setting up this blog that Vim has an spell checker
included since version 7. You can activate it with:
    :set spell 
This will set the language to default (en).

If you want to change the language use (e.g. Catalan):
    :set spell spelllang=ca_ES
If you do not have the word list for the language you can download it from the
OpenOffice extensions page: http://extensions.services.openoffice.org/dictionary

The OpenOffice extension files are zipped files containing the dictionaries.
Just extract the .aff and .dic files to a directory (e.g. /tmp) and import them
to Vim with (do not specify the extension .aff or .dic):
    :mkspell ~/.vim/spell/ca /tmp/catalan
The first parameter is where to store the generated word list and the second
one is the input word list (in this case the catalan.aff and catalan.dic
files). If the destination directory does not exists Vim will complain that it
can not load the generated file

After this just change the spelllang to the new language with:
    :set spell spelllang=ca_ES

Once you have spell checking enabled misspelled word will appear highlighted. You
can use "z=" over a highlighted word to see a list of alternatives.

+ Sources:
  + https://www.linux.com/learn/tutorials/357267:using-spell-checking-in-Vim
  + Vim help: ":help mkspell"
