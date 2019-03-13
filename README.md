# dynamicPrint
Label Print App for FileMaker

(requirement) Chrome only

In DEMO movie, though I transferred FileMaker data by drag and drop, 
it's more practical to embed JSON data directly into the code and export the html file.
Replace the sample JSON data with your data.

e.g.  
Let(  
code = "
 /* dynamicPrinter code here */  
 ......  
const data = "\__JSON\__";  
.......
" ;  
Substitute(code; "\_\_JSON\__"; YOUR_JSON_DATA)  
)