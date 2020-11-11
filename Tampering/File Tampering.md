Poke around in the About us section for a link to a file storage folder.
</br>
Attempting to access most files shows a restriction error that limits the files which can be accessed. That's what it means when it states Only .md and .pdf files are allowed!
</br>
Since we can see many files that seem inaccessible this tells us that they are likley legitimate files, but there's a filter preventing you from accessing them. 
</br>
## Null byte
Adding a nullbyte to a string is great for bypassing filters. The null byte is 00, a way to try to add it to the end of the file is to use %, which html encodes to %25. After this null byte, add a file extension that is allowed.
Then save the file.
