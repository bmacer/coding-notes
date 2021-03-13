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
Get name and parent of processes

    Get-Process | select Name, Parent
Kill process

    kill {{pid}}
    Stop-Process -Name process-name -Force
See all commands

    Get-Command
Create directory

    New-Item -Path /tmp/here -ItemType Directory
Copy file

    Copy-Item
Delete file

    Remove-Item
Get length of XML file

    (Import-Clixml /tmp/here.xml).length
Count unique "Id" value in an xml file

    ((Import-Clixml ./tmp/here.xml).id | select -Unique).length
Count occurrences in xml file

    (Import-Clixml ./Sec/Security.xml).id | group
Find inside xml object

    $logs | Where-Object {$_.Id -eq 1234 }
Get listening ports

    netstat -nota
Make web request

    Invoke-WebRequest 127.0.0.1:1234
For each and if example (range 1-50, make web request return only if content doesn't equal 59)

    foreach ($i in (1..50)) {$res = (Invoke-WebRequest 127.0.0.1:9999/$i); if($res.RawContentLength -ne 59) {echo $i};} 
