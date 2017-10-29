# UpLoadGadget
An open source gadget for SpiderBasic language that provides drag’n’drop file uploads.   
This gadget uses the JavaScript dropzone.js

## Demo  
http://falsam.com/sbtest/uploadgadget.php

## Syntax
Result = UploadGadget(Gadget, x, y, Width, Height, Prompt$, Pattern$="", CallBack=#False, MaxFiles=1, MaxFilesSize=2)

## Description
Create a Upload gadget. This gadget provides drag’n’drop file uploads.

## Events
#DZ_EventType_Add  
An element is added on the DropZone 
 
#DZ_EventType_Progress  
A file is being transferred to the server.

#DZ_EventType_Error 
An error has just occurred. (_Error type of file, file too big, etc..._)

#DZ_EventType_Success  
Transfer completed
    
#DZ_EventType_Maxfilesexceeded  
Number of files transferred simultaneously exceeding the allowed limit (MaxFiles).

## Example
   
