Func _dirremovecontents($folder)
	Local $search, $file
	If StringRight($folder, 1) <> "\" Then $folder = $folder & "\"
	If NOT FileExists($folder) Then Return 0
	FileDelete($folder & "*")
	$search = FileFindFirstFile($folder & "*.*")
	If $search = -1 Then Return 0
	While 1
		$file = FileFindNextFile($search)
		If @error Then ExitLoop
		If StringRight($file, 1) = "." Then ContinueLoop
		If FileGetAttrib($folder & $file) = "D" Then DirRemove($folder & $file, 1)
	WEnd
	FileClose($search)
	Return 1
EndFunc
