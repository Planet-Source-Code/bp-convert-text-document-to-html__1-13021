<div align="center">

## Convert Text Document to HTML


</div>

### Description

This routine will allow you to convert any text document into an HTML document. This is a basic function that simply puts the template HTML tags into place and then adds line breaks after each line of the text file is read in. This would be handy function for converting large numbers of documents to web-format. This code would be used as following:

Call FileToHTML("c:\autoexec.bat", "c:\test.html", "Auto Execute File", "maroon", "white")
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[BP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/bp.md)
**Level**          |Intermediate
**User Rating**    |4.2 (21 globes from 5 users)
**Compatibility**  |VB 3\.0, VB 4\.0 \(16\-bit\), VB 4\.0 \(32\-bit\), VB 5\.0, VB 6\.0
**Category**       |[Files/ File Controls/ Input/ Output](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/files-file-controls-input-output__1-3.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/bp-convert-text-document-to-html__1-13021/archive/master.zip)





### Source Code

Public Sub FileToHTML(InputFile As String, OutputFile As String, title As String, bgcolor As String, textcolor As String)
  newline$ = Chr$(13) + Chr$(10)
  Open InputFile For Input As #1
  Open OutputFile For Output As #2
  If title = "" Then title = "No Document Title"
  If bgcolor = "" Then bgcolor = "white"
  If textcolor = "" Then textcolor = "black"
  Print #2, "<HTML>" + newline$
  Print #2, "<HEAD>" + newline$
  Print #2, "<TITLE>" + title + "</TITLE>" + newline$
  Print #2, "</HEAD>" + newline$
  Print #2, "<BODY bgcolor=" + bgcolor + " text=" + textcolor + ">" + newline$
  Do Until EOF(1)
    Line Input #1, myLine$
    Print #2, myLine$ + "<BR>"
  Loop
  Print #2, newline$
  Print #2, "</BODY>" + newline$
  Print #2, "</HTML>"
  Close #1
  Close #2
End Sub

