# Remote Resource Markup Language Email Extension
## XML document specifaction for requesting and receving Email from a remote server.

The following is the layout of the document. It goes in the body of a RRML document.

```
Root Tag: errml 
    Tag: head
        Tag: header from:
        Tag: header to:
        Tag: header <other option here>:
    Tag: body
        Tag: attachment url:
        Tag: message    content:
```

Tag | Parmater | Description | Required
-----|-----|-----|-----|
head||May be repeated. ID's must be unique.|Yes
header|from|Email address of sender|As defined in email spec.
header|to|Email address of recipent|As defined in email spec.
header|<other option here>|Any other email headers here.|As defined in email spec.
body||Contains the message and attachments.|Yes
attachment|url|URL of attachment. Valiad protocols include http/https, ftp, and scp.|No
message|contnet|Type of content being sent. Content types include text, html, markdown.
