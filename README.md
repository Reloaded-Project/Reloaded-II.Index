# Reloaded-II.Index

This repository holds the `search index` for various sources used by [Reloaded-II](https://github.com/Reloaded-Project/Reloaded-II).  

The `search index` is a collection of downloadable packages (mods). This index is downloaded from the Reloaded client and allows for virtually instant lookups in the `Download Mods` menu.  

This repository, and in turn the index are automatically built by a bot [`Reloaded.AutoIndexBuilder`] and updated at fixed frequent time intervals; followed by a push to GitHub Pages via actions.  

## Structure

- 'Index.json.br' holds a mapping of each corresponding source (GameBanana Game and/or NuGet Server) to a file which contains the package information.  
- Package information is found under the `Search` folders.  

## Systemd Service

```
[Unit]
Description=Reloaded II Auto Index Builder

[Service]
Type=simple
WorkingDirectory=/opt/Reloaded.AutoIndexBuilder
ExecStart=/snap/bin/dotnet_50 /opt/Reloaded.AutoIndexBuilder/Reloaded.AutoIndexBuilder.dll
Restart=always
User=root # Important!! Snap bug?? Can be any other valid user.

[Install]
WantedBy=multi-user.target
```