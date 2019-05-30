# DSStoreParser
macOS .DS_Store Parser. Searches recursively for .DS_Store files in the path provided and parse them.

Usage
-------------

```
usage: DSStoreParser.py [-h] -s SOURCE -o OUTDIR [-f]

DSStoreParser CLI tool. v0.2.0

Search for .DS_Store files in the path provided and parse them.

optional arguments:
  -h, --help            show this help message and exit
  -s SOURCE, --source SOURCE
                        The source path to search recursively for .DS_Store
                        files to parse.
  -o OUTDIR, --out OUTDIR
                        The destination folder for generated reports.
  -f, --files_exist     While parsing check if record filename in ds_store
                        exists on disk.```
