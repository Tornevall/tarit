# TarIT 1.0.5 - the lazy-user helper for automatically tar and compress directories

## Usage

```text
tarit <directory|archive>
```

When given a directory, TarIT creates a tar archive, compresses it with the best
available compressor, and removes the source directory after successful
compression.

When given a supported archive, such as `archive.zip` or `archive.rar`, TarIT
extracts it into a temporary directory, creates a tar archive, compresses it,
and removes the source archive after successful compression.

Run `tarit --help` for the complete built-in usage information.

## What this script does

First of all, I will be very surprised if this was not yet another inventing-the-wheel-again tool.
This script was once created as we worked a lot with tar archiving that required not only taring down directory structures.
There was also a big need of packing them with an available archiver. So what this tools is actually doing is the following:

* Tell the user how big the directory is before taring it down
* Tar the directory
* Pack it with best available packer: gzip, bzip2 or xz. If xz exists, it will use that archiver and pack the tar archive with the -e(xtreme compression) flag.

The script can also repack supported archives. It does the following:

* Unpack the primary file archive (and calculate the unpacked folder size)
* Tar the directory that was just extracted
* Pack it with the best available compressor: gzip, bzip2 or xz. If xz exists, it uses that compressor with the `-e` (extreme compression) flag.


## Supported input archives (if the required unpacker exists)

* rar
* zip
* tgz
* txz
* tbz
* tbz2
* tar
