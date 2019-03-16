# dynamicPrint
Label Print App for FileMaker

(requirement) Mac, Chrome only

One of the annoying thing in FileMaker development is to prepare various layouts according to various printers or various customer's needs.
Each printer has its own characteristics. On one printer you can print well, but not on the others. Have you ever wanted to change objects position slightly before print?
If users don't have the privilege to enter into layout mode, developers of the app are called and complained.
That's the place where Dynamic Print comes in.
This approach does not resolve all these problems, but in some cases I think it's useful.
By delegating print to web browser(Chrome), FileMaker has no need to prepare layouts/scripts relating to print.
FileMaker's task is only to pass the data to Chrome. Users can define objects positions and its size freely on Chrome.
And those information ( object size and position ) is saved in Chrome's localStorage.
Users can use the same settings they defined yesterday.

-- How to pass the data from FileMaker to Chrome --  
There are two ways.
1. Drag and Drop via 'Data Source Selector'  
DataSourceSelector is a webviewer widget I made. Using this, you can generate csv data and drag and drop it into Chrome.
2. Embed the data into the code directly in FileMaker  
FileMaker exports the html file after that.  
In DEMO file, you can test these two ways.

-- How to use it --  
At first there are no styles, so all objects resides in the left top corner. Move those as you want.
There are three functions of the object.
1. Resize: use bottom-right corner. Dragging the bottom-right corner,font-size is changed.
font-size is restricted not to be less than 14px.
2. Change writing direction( vertical - horizontal ): use right-top corner
3. Expand spacing: use left-top corner By clicking, the mode is changed. Dragging the bottom-right corner, character-spacing is changed.
4. Move: grasp the center of the object and drag

DEMO FILE: Customers.fmp12   
In DEMO, postcard means Japanese postcard.
