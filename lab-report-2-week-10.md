# Week 10 Lab Report 5

  1. How you found the tests with different results (Did you use diff on the results of running a bash for loop? Did you search through manually? Did you use some other programmatic idea?)

In order to find the tests with all the different results I searched through the results.txt file and searched manually for each test that had a different result apart from []. Since all results were under one txt file which was able to be created using bash but it was easy to spot different results since most files were [] and any extra characters stood out to the rest. If it were more results or reusults that were harder to spot I can see how it can be essential to use diff to find these different results.

## Different Tests

Test 14:

  Output: [/foo]
  
  The expected output is [] which is correct since /foo is not a link since it is missing any html and is simply a string of characters. The bug of this is that       MarkdownParse returns anything that is in between the brackets without checking it is actuallya link or not.
  
Test 22:

  Output: [/bar\* "ti\*tle"]
  
  The output for this test should be [] since the link between the backets have quotations marks which should not be allowed in links. The bug of this is the         MarkdownParse file has no regulation or does not check for any quotation marks so it passes it as another character in the string and therefore does not detect     the marks and outputs the link even if it incorrect.
  
Test 32:

  Output: [/f&ouml;&ouml; "f&ouml;&ouml;"]
  
  The output for this test should be [] since the result also has quotations and the bug of this is that there is no code that checks for quotation marks and just     lets it pass as a link.
  
Test 41:

  Output: [url &quot;tit&quot;]
  
  The output foe this test should be [] since the url that is printed out contains a space and an ampersand which should not be allowed in a url link. The             MarkdownParse file fails to check for these specific characters that are unsafe or not allowed and therefore simply is only checking for parantheses and brackets   without checking for these special characters.
