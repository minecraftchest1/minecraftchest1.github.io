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
Checksum||Contains hashes of the body used to verify the integrity of the data sent. At least one hash must be included if used.|Recomended
Checksum|MD5|MD5 checksum of the body.|No
Checksum|SHA1|SHA1 checksum of the body.|No
Checksum|SHA256|SHA256/SHA2 checksum of the body.|No
Checksum|SHA512|SHA512/SHA3 checksum of the body.|No
Sender||Used to identify the sender of ther packet.|Yes
Sender|IPv4|IPv4 address of sender|Yes*
Sender|IPv6|IPv6 address of sender|Yes*
Sender|Hostname|Hostname of sender|No
Sender|FQDN|Fully Qualified Domain Address of sender|No
Destination||Used to identify the Destination of ther packet.|Yes
Destination|IPv4|IPv4 address of Destination|Yes*
Destination|IPv6|IPv6 address of Destination|Yes*
Destination|Hostname|Hostname of Destination|No
Destination|FQDN|Fully Qualified Domain Address of Destination|No
Proxyhost||Used to identify any proxies that have passed on the packet. May repeat several times in the header.|Yes
Proxyhost|IPv4|IPv4 address of Proxyhost|Yes*
Proxyhost|IPv6|IPv6 address of Proxyhost|Yes*
Proxyhost|Hostname|Hostname of Proxyhost|No
Proxyhost|FQDN|Fully Qualified Domain Address of Proxyhost|No
Authencation||Used to identify and authorize the sender. Either username and password (basic auth), or bearer token may be used.|No
Authencation|Username|Username of the sender of the packet.|No
Authencation|Password|Password of the user that sent the packet.|No
Authencation|Bearer|Authencation token created by other authencation systems.|No
Body||Contains data being sent. Not to be used as root tag.|Yes


*Either IPv4 or IPv6 address must be included.

<script src="https://utteranc.es/client.js"
        repo="minecraftchest1/minecraftchest1.github.io"
        issue-term="pathname"
        label="discussion"
        theme="github-dark"
        crossorigin="anonymous"
        async>
</script>
