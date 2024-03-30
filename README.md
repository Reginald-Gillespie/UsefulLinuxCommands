# Useful Linux Commands
### A growing list of commands for linux, for various things.

At some point when this is larger I'll organize this into folders and sections or add section links. Maybe.

<br>

## Utilities

Search for a file by name.
```bash
find / -name "filename.txt" 2> /dev/null
```

---

## Pranks

Rickroll at bash startup. It runs as a silent background job while the video loads. To stop it, type `fg` and hit `Ctrl + c`
```bash
echo "{ mpv --quiet -vo=tct -cache-pause=no https://www.youtube.com/watch?v=dQw4w9WgXcQ & } 2>/dev/null;" >> ~/.bashrc
```
