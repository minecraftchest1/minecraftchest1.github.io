# Remote Resource Markup Language
## XML document specifaction for requesting and receving resources from a remote service.

The following is the layout of the document.

```
Root Tag: Packet   id:
  Tag: header
    Tag:checksum   md5:  sha1:   sha256:   sha512:
    Tag: sender    ipv4:  ipv6:   hostname;   fqdn:
    Tag: destination  ipv4:  ipv6:   hostname;   fqdn:
    Tag: proxyhist  ipv4:  ipv6:   hostname;   fqdn:
    Tag: authencation   user:   password:   bearer:
  Tag: body
Tag: payload
```

Tag | Parmater | Description | Flags
-----|-----|-----|-----|
Packet||May be repeated. ID's must be unique.|Yes
Packet|ID|Identifies the packet. Created by hashing the header and body.|Yes
Header||May only exist once in each packet.|Yes
