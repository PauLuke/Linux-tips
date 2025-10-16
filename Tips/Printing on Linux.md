Install the `cups` package. 

Enable cups service

```
systemctl enable cups.service
```

Start cups service

```
systemctl start cups.service
```
If you have a Epson printer like me, intall the `epson-inkjet-printer-escpr` package.

Then go to `http://localhost:631/`

Add a new print and select the Epson driver for your printer model.
