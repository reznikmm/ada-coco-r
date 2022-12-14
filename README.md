Compiler-Generator Coco/R
=========================

The Coco/R is the tool that generates recursive descent parsers and their
associated scanners from attributed grammars.
Coco/R was originally written in Oberon by Hanspeter Moessenboeck.
Then it was been ported to many other programming languages.

This release is the port of the Coco/R with release level 1.53 into Ada language
environment. It was been done by using Linux OS and GNAT compiler (V-3.15p).

The genegal information about Coco/R itself and it usage is available on the WWW at

     http://cs.ru.ac.za/homes/cspt/cocor.htm



How to build & install Ada Coco/R from sources
==============================================

The Coco/R Ada sources are placed into subdirectory "src".

To build Coco/R from sources just issue the commant:

     gnatmake -o acr cr.adb

When it is finished You will have Coco/R executable file "acr" (by mean Ada Coco/R).
You can put it in some appropriate place for Your system and make "acr" command
available through "PATH" environment variable, i.e. put it into "/usr/local/bin".
Then You will need to place common Coco/R frame files from the "common_frame_files"
subdirectory of distribution to some appropriate place for Your system,
i.e. into "/usr/share/ada_cocor/frames/", and to export environment variable
"CRFRAMES" that point to this directory. If You are using BASH, it can be done
with simple BASH command:

     export CRFRAMES="/usr/share/ada_cocor/frames/"



How to regenerate Coco/R Ada sources
====================================

When You will have Coco/R installed on Your system You can try to regenerate
Coco/R Ada sources. The distribution has the separate subdirectory "src_gen"
that holds all source files that You will need to do so. To start this process
You will need just issue in this directory the command:

     acr cr

Next files will be generated as result of this process:
   "ca.adb"             - Coco/R main procedure file
   "crp.ads", "crp.adb" - Coco/R parser package (specification and body)
   "crs.ads", "crs.adb" - Coco/R scanner package (specification and body)



Known limitations
=================

At this time it is not possible to use Ada attributes into production code.
It is because any Ada attribute starts from character ''', and it is interferenced
with string declaration into Coco/R attributed grammar.



Notes
=====

It must be noted that at present time the internal algorithms
that allocate string values in heap don't care about freeing
dynamically allocated space.



(C) O.Havva (alex@lviv.bank.gov.ua)


