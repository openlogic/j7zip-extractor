j7zip-extractor
===============

j7zip-extractor is a fork of the [J7Zip project](http://p7zip.sourceforge.net) intended to be used only for
extracting the contents of a 7zip archive into a specified directory. Consequently, it doesn't support creating 7z
archives or listing their contents.

 This version supports only
 
 * non-encrypted archives
 
 * archives with Copy or LZMA codec.


j7zip-extractor also includes a version of the [JAVA LZMA SDK](http://www.7-zip.org/sdk.html).


LZMA is default and general compression method of 7z format in 7-Zip compression program (www.7-zip.org). LZMA
provides high compression ratio and very fast decompression.

LZMA is an improved version of famous LZ77 compression algorithm. It was improved in way of maximum increasing of
compression ratio, keeping high decompression speed and low memory requirements for decompressing.


LICENSE
=======

 LGPL (see LGPL.txt)
 read also: http://www.gnu.org/licenses/lgpl-java.html


How To Compile
==============
With ant (any system with http://ant.apache.org/)

  - remove all built items
    
      `ant clean`
      
  - build dist/j7zip-extractor.jar
    
      `ant`

  Note: this code compiles with JAVA 5 or later


How To Use
==========

The executable j7zip-extractor
------------------------------

  - Tests archive files
  
	`java -jar dist/j7zip-extractor.jar t archive.7z`

  - Extracts files from archive to their full paths in the current directory
  
	`java -jar dist/j7zip-extractor.jar x archive.7z`

  - Extracts files from archive to their full paths under a given directory
  
	`java -jar dist/j7zip-extractor.jar x archive.7z target_dir`

The jar j7zip-extractor.jar
---------------------------

Please read SevenZip\J7zip.java and SevenZip\ArchiveExtractCallback.java as samples. Look at
   
`SevenZip.Archive.SevenZip.Handler`

`SevenZip.Archive.SevenZipEntry`

`SevenZip.Archive.IArchiveExtractCallback`

`SevenZip.Archive.IInArchive`


The executable LZMA (this hasn't been tested under the new code)
----------------------------------------------------------------

  to decompress: 
  
  `java -cp dist/j7zip-extractor.jar SevenZip.LzmaAlone d file.lzma file`


TODO
====
0. Add tests
1. Support creation of 7-zip archives
2. Improve speed
3. Support compression methods: PPMd, BZip2
4. Support encrypted archives


Copyright
=========
Marked portions of the code are Copyright (c) by OpenLogic, Inc.

The remaining code is provided by the p7zip project at http://p7zip.sourceforge.net.

All code licensed under the GNU LESSER GENERAL PUBLIC LICENSE. See LGPL.txt for full details.
