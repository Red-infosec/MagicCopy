# MagicCopy
Powershell script to exfiltrate large files quickly and securely.

Files are split into multiple pieces and encrypted using AES. Multithreading is supported for increased copy speed. 


### Magic-Put

Store file to a remote or local location.

```
Magic-Put -PieceSize 10MB -File 'C:\MYBIGFILE.DATA' -Destination 'O:\' -Key "rJm0PP2KBhDoq87Q+hVqjwJt+NWguCRY1oLgRHmcSwY="  -Threads 20 
```

Recover lost pieces:

```
Magic-Put -PieceSize 10MB -File 'C:\MYBIGFILE.DATA' -Destination 'O:\' -Key "rJm0PP2KBhDoq87Q+hVqjwJt+NWguCRY1oLgRHmcSwY="  -FirstPiece 20 -LastPiece 25 
```

### Magic-Get

Recover file:

```
Magic-Get  -File 'O:\MYBIGFILE.DATA' -Destination 'C:\' -Key "rJm0PP2KBhDoq87Q+hVqjwJt+NWguCRY1oLgRHmcSwY="
```

### Generating Key

```
New-CryptographyKey -AsPlainText
```


### Sources

https://gallery.technet.microsoft.com/scriptcenter/EncryptDecrypt-files-use-65e7ae5d
https://gallery.technet.microsoft.com/scriptcenter/Powershell-functions-to-cb6bb05a
