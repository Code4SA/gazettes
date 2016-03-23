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

#IMPORTANT:
some gazettes have notices as figures (optical character recognition?)
e.g. 2667_18-3_MpumalangaSeparate.pdf (or Presidency contains signed docs)

Monthly Gazette Index- access denied

"Since there are many gazette editions additional to the weekly gazette, the GPW compiles an index of all gazettes published during a month. This is a service to the public, to assist interested parties in keeping track of all editions.""


#JSON template:
https://openc.github.io/openc-schema/docson/index.html#https://raw.githubusercontent.com/openc/openc-schema/master/build/gazette-notice-schema.json$$expand



# requirements:

written in Python3

pip install:

- pdfminer3k v. 1.3.0 (Python3)
  note: there are significant API differences between versions and is very different
  to pdfminer (Python2)

- jsonpickle
