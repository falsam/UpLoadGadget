# UpLoadGadget
An open source gadget for SpiderBasic language that provides drag’n’drop file uploads.   
This gadget uses the JavaScript dropzone.js

## Demo  
http://falsam.com/sbtest/uploadgadget.php

## Syntax
Result = UploadGadget(Gadget, x, y, Width, Height, Prompt$, Pattern$="", _CallBack=#False_, _MaxFiles=1_, _MaxFilesSize=2_)

## Description
Create a Upload gadget. This gadget provides drag’n’drop file uploads.

## Events
**#DZ_EventType_Add**  
An element is added on the DropZone.   
 
**#DZ_EventType_Progress**  
A file is being transferred to the server.  

**#DZ_EventType_Error** 
An error has just occurred. (_Error type of file, file too big, etc..._)  

**#DZ_EventType_Success**  
Transfer completed.  
    
**#DZ_EventType_Maxfilesexceeded**  
Number of files transferred simultaneously exceeding the allowed limit (MaxFiles).

## Installation. 
When creating your web application, it is important to enter an application name followed by the **.php** extension.  
_Example_: **yourapp.php**  

Copy the **upload.php** script to the installation folder of your web application.  

Copy the **dropzone.js** script to the installation folder of your web application.  


## Example

```
OpenWindow(0, 0, 0, 440, 400, "Demo", #PB_Window_ScreenCentered)
UploadGadget(0, 20, 20, 400, 200, "Drag your image file to this area", "*.png,*.jpg", @onUpload(), 1, 1) 

; UpLoadGadget() events
Procedure OnUpload(Event.i, FileName.s, Size.i, Message.s)
  Select Event
      
    Case #DZ_EventType_Add
      Debug FileName + " (" + Str(Size) + ") Add"
        
    Case #DZ_EventType_Progress
      Debug FileName + " " + Message
      
    Case #DZ_EventType_Success
      Debug FileName + " End of processing"
      
    Case #DZ_EventType_Error
      Debug FileName + " Error " + Message
      
    Case #DZ_EventType_Maxfilesexceeded
      Debug FileName + " Error " + Message
      
  EndSelect  
EndProcedure
```

