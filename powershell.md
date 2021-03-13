Find all files in a certain (/Windows) directory

    Get-ChildItem /Windows -Recurse -File *.json
Display file contents

    Get-Content ./secret.json
Get number of subdirectories inside a folder

    (Get-ChildItem -Recurse -Directory).Length
Current logged in user

    $Env:USER
See all variables

    Get-Variable
Get the filename (just the filename) of a file that contains the word "brandon"

    Get-ChildItem -Path /Windows -Recurse | Select-String -Pattern "brandon" | group path | select name
Hash a filename

    Get-FileHash -Algorithm MD5 /my/filename.txt
Get a file's creation time (or other properties)

    Get-ChildItem ./my-file.txt | Select-Object -Property CreationTime
Grab the 10th item in history and just the part after quotation mark

    (Get-History)[9].CommandLine.Split('"')[1]
Decode a base64-encoded string in history:

    [System.Text.Encoding]::UTF8.GetString([System.Convert]::FromBase64String((Get-History)[9].CommandLine))
Get processes with username

    Get-Process -IncludeUserName
Get file run by a certain process (brandon-process)

    Get-ChildItem -Path / -Recurse -File brandon-process 2>$null
  
  
