# Remote Resource Markup Language
## XML document specifaction for requesting and receving resources from a remote service.

```
Root Tag: Payload   id:
  Tag: header
    Tag:checksum   md5:  sha1:   sha256:   sha512:
    Tag: sender    ipv4:  ipv6:   hostname;   fqdn:
    Tag: destination  ipv4:  ipv6:   hostname;   fqdn:
    Tag: proxyhist  ipv4:  ipv6:   hostname;   fqdn:
    Tag: authencation   user:   password:   bearer:
  Tag: body
Tag: payload
```