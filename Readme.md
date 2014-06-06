Thesis Preparation Template (LaTeX)
	for The Chinese University of Hong Kong

Users are assumed to have basic knowledge and real experience with LaTeX,
a professional document preparation/typesetting system.



Software Tool
=============

Commercial product:
	PCTeX32 (for Windows)

Open source software:
	MiKTeX (for Windows and various platforms)
	TeX/LaTeX package (for Linux/Unix)



Usage
=====

- unzip the package to folder C:\thesis_template\ for example
  (you may use other path/folder, however, some earlier version software
   such as PCTeX32 V4.2 cannot handle path with space or non-English
   characters, which could cause problem)
- typeset with LaTeX the main file [thesis.tex] once or twice
- typeset the bibliography
  (you should click on the main file and make it current before
   clicking on the menu item Typeset->Bibliography under PCTeX32)
- typeset with LaTeX the main file [thesis.tex] once or twice
- check if there are any undefined reference(s) and correct them



File Description
================

Main file:
	[thesis.tex]
- user should customize and typeset this file
- this file is the heart of the whole document
- it links up other files

Preamble files:
	[abstract.tex]
	[acknowledgement.tex]
	[dedication.tex]
- user should edit these files accordingly

Chapter (normal/appendix) folders and files:
	[introduction/introduction.tex]
	[background/background.tex]
	[conclusion/conclusion.tex]
	[proof/proof.tex]
- keep chapters and related materials in different folders
- appendix chapters should be handled as normal chapters, see main file
- the main file takes care of the ordering of the chapters

Bibliography file:
	[database.bib]
- this is a BibTeX file
- construct the bibliography items one-by-one with proper labeling
- software should handle citation and sorting properly

Bibliography style file:
	[ieee.bst]
	[ieee_lastname_comes_first.bst]
- these are bibliography style files
- user should create/download/acquire/modify/apply different styles accordingly
- different disciplines, publishers, conventions accept different styles

Output files:
	[thesis.dvi]
	[thesis.ps]
	[thesis.pdf]
- DVI format is basically for screen preview
- PostScript format is for printing
- Portable Document Format is for both printing and sharing



TeX/LaTeX style file:
	[thesis.sty]
- advanced user may customize this file

Makefile:
	[Makefile]
- advanced Linux/Unix user may take advantage of work flow automation
- inspection and customizations are strongly advised before application



Related Information
===================

The following Improving Postgraduate Learning (IPL) courses offered by the CUHK
Graduate School and CLEAR provide more details on using LaTeX and the template
for professional document preparation and thesis typesetting:

	LaTeX Basics - Professional Document Preparation
	LaTeX Advanced - Thesis Preparation



Package prepared by
Michael FUNG (pffung@cuhk.edu.hk)
16 October 2008
(With reference to materials from Mr. Sau-Ming LAU)

