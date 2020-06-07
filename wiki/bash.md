# Bash

## Protips
- Lookup who is listening on PORT: `lsof -nP -i4TCP:PORT | grep LISTEN`
- `vidir` (edit file names with vim): install the `moreutils` package
- Terminal blocked (not reacting to keyboard input): press `CTRL+q` (probably pressed `CTRL+s` previously by mistake)
- Edit current command line in `$EDITOR`: `CTRL+x CTRL+e`
- Split a file (useful for example for putting a big file on a FAT32 usb key): `split -b 3000mb my_big_file`. Recreate the file: `cat file1 file2 > my_big_file`
