MarkDownload only saves to ```~/Downloads```  so I had to create a folder there and make a symbolic link to a folder in my Vault (Web pages). 

1. Create a folder for MarkDownload:

```
mkdir ~/Downloads/MarkDownload
```

2. Make the symbolic link:

```
ln -s ~/Documents/"Obsidian Vault"/"Web pages" ~/Downloads/MarkDownload
```

Result:

![[Pasted image 20220528135942.png]]
