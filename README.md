# tarit - the lazy user's tar-archiver-helper

## What this script does

First of all, I will be very surprised if this was not yet another inventing-the-wheel-again tool.
This script was once created as we worked a lot with tar archiving that required not only taring down directory structures.
There was also a big need of packing them with an available archiver. So what this tools is actually doing is the following:

* Tell the user how big the directory is before taring it down
* Tar the directory
* Pack it with best available packer: gzip, bzip2 or xz. If xz exists, it will use that archiver and pack the tar archive with the -e(xtreme compression) flag.

For a few weeks ago, this script also repacks archives and is currently supporting rar and zip-archives. What it does then is this:

* Unpack the primary file archive (and calculate the unpacked folder size)
* Tar the directory that was just extracted
* Pack it with best available packer: gzip, bzip2 or xz. If xz exists, it will use that archiver and pack the tar archive with the -e(xtreme compression) flag.

If the archive already exists as a xz/gz/bz2-file, it tries to recompress the file with best available compression.
And if the archive is only named "tar", yes - it tries to compress that file.
