# Move files based on partial name match using Windows Powershell

The program will grab any files that mention the name "Harlo" from the source folder "Data" and send them to the destination folder "Data" and create a destination folder named "Harlow"(Example: both 123Harlo.pdf and Harlo90_.pdf files will be transferred to the Harlow folder)

Replace the $map term on the left side of the "=" sign with your own search term ("Harlo") and replace the term on the right side of the "=" sign with your preferred folder name ("Harlow")


Order of Operations:
1.	Setting the source root directory path to "C:\Users\joshj\Downloads\Data".
2.	Setting the destination root directory path to "C:\Users\joshj\Downloads\Data".
3.	Creating a hashtable named "map" to map the first 5 characters of the file name to the corresponding destination folder name.
4.	Getting a list of all files in the source root directory and its subdirectories using the Get-ChildItem cmdlet.
5.	Looping through each file in the file list.
6.	Getting the first 5 characters of the file's base name, checking if it is in the "map" hashtable keys, and storing the corresponding value as the key.
7.	If the key is found in the hashtable, creating the destination folder path by combining the destination root directory path with the value of the key in the hashtable.
8.	Checking if the destination folder exists, and creating it if it doesn't.
9.	Moving the file to the destination folder. If the destination file already exists, the script throws an error message.

This script uses several cmdlets such as Get-ChildItem, Join-Path, Test-Path, mkdir, Write-Verbose, Write-Error, and Move-Item.
