# gazettes

## Government

### National Gov

###Regulation
incl. Labour

### Separate gazettes
http://www.gpwonline.co.za/Gazettes/Pages/Published-Separate-Gazettes.aspx

- Public works
- StatesSec Agency
- Basic edu
- TradeIn
- Transport
- EnvAffars
- Rural DEV
- higher edu
- health
- presidency
- energy
- small business

### legal
### liquor
### tender bulletins

## Provincial
only:

- Limpopo
- NCape
- ECape
- Gauteng
- Mpumalanga
- KwaZulu Natal


#JSON template:
https://openc.github.io/openc-schema/docson/index.html#https://raw.githubusercontent.com/openc/openc-schema/master/build/gazette-notice-schema.json$$expand



# requirements:

written in Python3

pip install:

- pdfminer3k v. 1.3.0 (Python3)
  note: there are significant API differences between versions and is very different
  to pdfminer (Python2)

- jsonpickle
https://jsonpickle.github.io/

# improvements and fixes:
- splitting the date field?
There is a document called Monthly Gazette Index to which access is denied:

"Since there are many gazette editions additional to the weekly gazette, the GPW compiles an index of all gazettes published during a month. This is a service to the public, to assist interested parties in keeping track of all editions.""

Might be good to split date into separate fields for day, month, year to make
e.g. month/year queries

- url field is not gazette specific
- parse notice summary: for now it's all found in the outline (keywords, select English)
- in the documents tested so far, just one scenario does not recover all
  pages from the outline section: when different lines of text referring to
    the pages where the notices are come as a single sentence joined by multiple-dots.
`
    noticeX .... pageX
    noticeY ... pageY
`
    is in fact stored as:

    `
         noticeX.... page X ..... noticeY....... page Y .... etc
    `
    It does recover first and last though, which is sufficient to fetch the information,
    and notice descriptions can be parsed directly from the pages.
    However, if at later stages we need a direct link between notice description
    and pages, this should be fixed.

- some gazettes have notices as figures, so special parsing is needed
e.g. 2667_18-3_MpumalangaSeparate.pdf or the Presidency contains signed docs
