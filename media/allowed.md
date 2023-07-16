# Allowed File Types
To ensure that your website runs smoothly and securely, certain restrictions may be placed on the types of files that can be uploaded. Here is a list of the allowed MIME types and their extensions for file uploads by default:


## MIME Types

```
application/msword
application/octet-stream
application/ogg
application/pdf
application/vnd.rar
application/x-rar
application/vnd.ms-excel
application/vnd.ms-powerpoint
application/vnd.oasis.opendocument.spreadsheet
application/vnd.oasis.opendocument.text
application/vnd.openxmlformats-officedocument.presentationml.presentation
application/vnd.openxmlformats-officedocument.spreadsheetml.sheet
application/vnd.openxmlformats-officedocument.wordprocessingml.document
application/zip
audio/mp4
audio/mpeg
image/avif
image/gif
image/jpeg
image/png
image/svg+xml
image/vnd.microsoft.icon
image/webp
image/x-icon
text/plain
video/mp4
video/mpeg
video/ogg
video/quicktime
video/webm
video/x-flv
video/x-matroska
video/x-ms-wmv
video/x-msvideo
```

## Extensions

```
avi
avif
doc
docx
flv
gif
ico
jpeg
jpg
m4a
mkv
mov
mp3
mp4
mpg
ods
odt
ogg
ogv
pdf
png
ppt
pptx
rar
svg
txt
webm
webp
wmv
xls
xlsx
zip
```


However, if you need to upload a file type that is not listed here, you can add it using the `media_mime` and the `media_extension` [actions](/developer/actions?id=core). This allows you to specify custom file types that your website will recognize and accept. Please keep in mind that adding custom file types should be done with caution, as it can pose a security risk if not properly implemented.



