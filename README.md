# extract_images.py
Extract images from PDFs

Parses PDFs for image files. 

Some notes:
* The PDF file format supports binary streams enclosed by `stream` and `endstream`. 
* Each stream is preceded by a dictionary denoted by `<<` and `>>`. 
* The contents of the dictionary should contain a `/filter` object followed by a decode format. 
* Since we are expecting JPEGs, this flag should always be `DCTDecode`.
* The magic number to be expected is`FF D8 FF E0 00 10 4A 46 49 46 00 01`. 
* It is not known whether other JPEG streams are accepted, since this one contains the ASCII word `JFIF`. 
* Likewise, it should be possible for PNG streams to be embedded as well, and therefore extracted. 

Additional research:
https://github.com/josch/img2pdf - to convert images as-is into PDFs.
