How to Keep Status Available and Green Always on Microsoft Teams 

1. Right-click on your desktop, hover up to new, and choose “Text Document“.
2. Notepad will now be up, simply copy the Virtual Basic script (VBS) below and paste it into your notepad.

```
Set objShell = CreateObject("WScript.Shell")
lngMinutes = InputBox("How long you want to keep your system awake?" & Replace(Space(5), " ", vbNewLine) & "Enter minutes:", "Awake Duration") 'we are replacing 5 spaces with new lines
If lngMinutes = vbEmpty Then 'If the user opts to cancel the process
	'Do nothing
Else
	On Error Resume Next
	Err.Clear
	boolValid = False
	lngMinutes = CLng(lngMinutes)
	If Err.Number = 0 Then 'input is numeric
		If lngMinutes > 0 Then 'input is greater than zero
			For i = 1 To lngMinutes
				WScript.Sleep 60000 '60 seconds
				objShell.SendKeys "{SCROLLLOCK 2}"
			Next
			boolValid = True
			MsgBox "Forced awake time over. Back to normal routine.", vbOKOnly+vbInformation, "Task Completed"
		End If
	End If
	On Error Goto 0
	If boolValid = False Then
		MsgBox "Incorrect input, script won't run" & vbNewLine & "You can only enter a numeric value greater than zero", vbOKOnly+vbCritical, "Task Failed"
	End If
End If

Set objShell = Nothing
Wscript.Quit 0
```
3. Once done, click on File and then on “Save File as“.

4. Now Give the file name as Deactivate Sleep mode.vbs and click on Save.

5. Close the notepad and come back to your desktop.

6. You will now see a VBS Script file on the desktop that you just created with an S symbol.

7. Double click on it to open and type the minutes till when you want the Status as Available.

8. So if you want to show your Microsoft Teams Status to Available for the next 10 hours then type 600 and then click on ok.

So now you are all done, leave your computer for again 15 minutes and check back the status.
