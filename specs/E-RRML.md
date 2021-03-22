# Remote Resource Markup Language Email Extension
## XML document specifaction for requesting and receving Email from a remote server.

The following is the layout of the document. It goes in the body of a RRML document.

```
Root Tag: errml 
    Tag: head
        Tag: header from:
        Tag: header to:
        Tag: header relay:
        Tag: header <other option here>:
    Tag: body
        Tag: attachment url:
        Tag: message    content:
```

Tag | Parmater | Description | 
-----|-----|-----|-----|
head||May be repeated. ID's must be unique.|Yes
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
