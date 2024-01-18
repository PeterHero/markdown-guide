# Markdown guide

## Sources

Syntax guide is available [here](https://www.markdownguide.org/).

## Why use markdown

I find markdown to be a great tool for simplifying creation of already simple documents or webpages. What I would do int raw html or in some office suite document writer I now can do in a clear text file. For most usecases I do not need advanced feature of the document writer or I do not have to bother with writing html.

## Workflow

For people who'd like to use markup as their language of choice when writing documents there are options to export markdown to html or pdf. There are many programs that do this; see pandoc, wkhtmltopdf. But they are quite heavy if you just want a raw markdown.

I found lightweight tools that fulfill my expectations.
I use:
- lowdown
- htmldoc

### Lowdown

According to the [website](https://kristaps.bsd.lv/lowdown/):

"lowdown is a Markdown translator producing HTML5, roff documents in the ms and man formats, LaTeX, gemini, OpenDocument, and terminal output. The open source C source code has no dependencies."

It is a BSD project.

My usage:
```
lowdown -s foo.md > foo.html
```

### HTMLDOC

According to the [website](https://www.msweet.org/htmldoc/):
"HTMLDOC converts HTML and Markdown source files or web pages to EPUB, PostScript, or PDF files with an optional table of contents. While it currently does not support many things in “the modern web” such as Cascading Style Sheets (CSS), forms, full Unicode, and Emoji characters, it is still useful for converting HTML documentation, invoices, and reports."

I find this tool to be very useful and unique because it "does not support many things in the modern web". For my usecase this is a plus because that makes the tool lightweight and fulfill the purpose I have for it.

HTMLDOC can directly convert markdown to pdf but the conversion is correct. But md -> html -> pdf works very well.

My usage:
```
htmldoc --webpage -f foo.pdf foo.html
```
directly to pdf:
```
lowdown -s foo.md | htmldoc --webpage -f foo.pdf -
```

## Other

lowdown allows many formats e.g. odt.

When exporting to html you can also add the css file for creating a uniform style for your website. This cannot be used with htmldoc.

### To-do

- add example makefile for this workflow
- can title be added to the webpage?
