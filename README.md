Study bibles into OSIS / sword modules BETA
===========================================

This conversion utility is able to convert various bible commentary (study bible) ePub files
into SWORD modules. You must obtain ePub file (i.e. if e-book is being sold, you must buy it first).
 When you have the ePub file, you can use this utility to convert that file into a SWORD commentary module.

SWORD modules can be used with various Bible study software, including Xiphos on Linux/Windows desktop,
Eloquent for Apple OS X, AndBible on Android and Pocketsword on iPhone.

The following modules are tested to work:

 * The ESV Global Study Bible (download for free from [ESV.org e-books](http://esv.org/e-books)).
 * The ESV Study Bible (buy from [ESV.org e-books](http://esv.org/e-books)).
 * McArthur Study Bible (buy from [ESV.org e-books](http://esv.org/e-books)).

Others ePub commentaries may work or not, but feel free to try out. Support for other ePub commentary books can be
suggested via Github issue or by email. This software is at beta stage.

Installing and converting to SWORD module
-----------------------------------------

Install some python packages (requires python 3):

    pip install -r requirements.txt

Install osis2mod tool that can be obtained from http://www.crosswire.org/wiki/DevTools:Modules

To convert ePub to SWORD module (compressed in a zip file), run command

    python studybible_to_osis.py your_book.epub --sword

This will generate SWORD module in a file called your_book_module.zip

Quality
-------
 - All resources included: studynotes, charts, figures, articles etc
 - Articles and resources as a general book module (--sword will pack them in single zip file)
 - Convenient links are added from comments to larger-range comments
 - Tested with AndBible & Xiphos -- software is  BETA because of limited testing and due to many issues listed below

Known issues
------------
 - Xiphos displays ```<q>``` as another paragraph (Heb.1)
 - Not Xiphos, nor AndBible obey DisplayLevel option. Only Bibletime seems to obey it. So can't use it for now
   => need to use manual hack to merge smaller sections together..
 - Bibletime issues: paragraphs not displayed, genbook links cause crash, images are not scaled

TODO
----
  - In links, verse range end could be checked too.
  - Backreferences from comments to other resources (i.e. if verse is mentioned in article/etc., it is linked)
  - Write manually some TOCs in genbook

CHANGES
-------
 - revision 5: articles + book introductions as genbook

