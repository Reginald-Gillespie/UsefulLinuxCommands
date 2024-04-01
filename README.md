# Useful Linux Commands
### A growing list of commands for linux that I find useful for various things.

At some point when this is larger I'll organize this into folders and sections or add section links. Maybe.

<br>

## Utilities

Search for a file by name.
```bash
find / -name "filename.txt" 2> /dev/null
```

<br>

Regenerate fstab.

I was going to make a simple command for this but then I found [this](https://github.com/glacion/genfstab) standalone version of Arch's genfstab.

```bash
# Preview
genfstab -U /

# Write into /etc/fstab:
# mv /etc/fstab /etc/fstab.bal
# genfstab -L / > /etc/fstab
```

<br>

## Troubleshooting / Error resolution

### Library not found error:
```
./program: error while loading shared libraries: libraryName.so.14: cannot open shared object file: No such file or directory
```
Solution:
If you have googled and installed where the library comes from, it is possible you have a newer version of the library installed than the program wants.
In this case, look for what version you have installed with this command:
```bash
find / -name "libraryName.so.*" 2> /dev/null
```
Then, if you found the library, create a symbolic link between where the program is looking for the old library, and where the new library is:
```bash
ln -s <current library location> <where program is checking location>
```

<br>

## Pranks

Rickroll at bash startup. It runs as a silent background job while the video loads. To stop it, type `fg` and hit `Ctrl + c`
```bash
echo "{ mpv --quiet -vo=tct -cache-pause=no https://www.youtube.com/watch?v=dQw4w9WgXcQ & } 2>/dev/null;" >> ~/.bashrc
```
