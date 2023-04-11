# Allowed MIME Types
To ensure that your website runs smoothly and securely, certain restrictions may be placed on the types of files that can be uploaded. Here is a list of the allowed MIME types for file uploads by default:


```plain
application/json
application/octet-stream
application/ogg
application/pdf
application/photoshop
application/rar
application/svg+xml
application/vnd.ms-excel
application/vnd.ms-powerpoint
application/vnd.ms-word
application/vnd.oasis.opendocument.spreadsheet
application/vnd.oasis.opendocument.text
application/vnd.openxmlformats-officedocument.presentationml.presentation
application/vnd.openxmlformats-officedocument.spreadsheetml.sheet
application/vnd.openxmlformats-officedocument.wordprocessingml.document
application/zip
audio/mp4
audio/mpeg
image/gif
image/jpeg
image/png
image/svg+xml
image/vnd.microsoft.icon
image/webp
image/x-icon
text/css
text/html
text/plain
text/x-asm
video/avi
video/mp4
video/mpeg
video/ogg
video/quicktime
video/webm
video/x-flv
video/x-matroska
video/x-ms-wmv
```

However, if you need to upload a file type that is not listed here, you can add it using the `media_mime` [action](/developer/actions?id=core). This allows you to specify custom MIME types that your website will recognize and accept. Please keep in mind that adding custom MIME types should be done with caution, as it can pose a security risk if not properly implemented.
