# gdrive-webdav

![Go Workflow](https://github.com/mikea/gdrive-webdav/workflows/Go/badge.svg)

Simple Google Drive => WebDAV bridge.

## Usage

* Enable GDrive API and create OAuth keys(https://console.cloud.google.com/apis/library/drive.googleapis.com)
* Run using docker:
```
docker run -ti --rm -p 8765:8765 skippa/gdrive-webdav --client-id=<client_id> --client-secret=<client_secret>
```    
* Connect to WebDAV network drive using http://localhost:8765/

## Building From Source

```
go build
./gdrive-webdav --client-id=<client_id> --client-secret=<client_secret>
```

## Status

Alpha quality. I trust it my files.

* Linux Nautilus: Readable/Writable
* Linux davfs2: Some issues
* Mac Finder: Read-only
* Cyberduck: Appears to work (works also with Win8)
* Win8: Cannot connect to http://localhost:8765/ , using WIN8 network share builtin webdav support
  * Win8 MiniRedirector Client does not seem to send correct PROPFIND. Missing xml on request body 0 length.
