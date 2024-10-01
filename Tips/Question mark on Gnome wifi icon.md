You may have to disable NetworkManager's connectivity check. Use the following configuration:

```
/etc/NetworkManager/conf.d/20-connectivity.conf
---

[connectivity]
enabled=false
```
