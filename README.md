# DSStoreParser
macOS .DS_Store Parser. Searches recursively for .DS_Store files in the path provided and parses them.
MacOS Finder uses .DS_Store files to remember how a folder view was customized by the user.

Usage
-------------

```
usage: DSStoreParser.py [-h] -s SOURCE -o OUTDIR [-f]

DSStoreParser CLI tool. v0.2.1

Search for .DS_Store files in the path provided and parse them.

optional arguments:
  -h, --help            show this help message and exit
  -s SOURCE, --source SOURCE
                        The source path to search recursively for .DS_Store
                        files to parse.
  -o OUTDIR, --out OUTDIR
```

Output Reports
--------------------------

Three reports are generated in the output folder specified using the -o option.
```
  DS_Store-All_Parsed_Report-YYYYMMDD-HHMMSS.tsv: Contains all parsed records.
  DS_Store-Folder_Access_Report-YYYYMMDD-HHMMSS.tsv: Contains records specific to folder accesses.
  DS_Store-Miscellaneous_Info_Report-YYYYMMDD-HHMMSS.tsv: Contains other miscellaneous records parsed.
```
Report Columns
--------------------------

- generated_path: The generated path using the location of the .DS_Store file and the record filename stored in the .DS_Store file.
- record_filename: The record filename stored in the .DS_Store file.
- record_type: One of 42 identified record types. Contains the 4 letter code of the record type as well as a description of the code.
- record_format: The format that the record data is stored in.
- record_data: The record data.
- src_create_time: The created timestamp of the source .DS_Store file.
- src_mod_time: The modified timestamp of the source .DS_Store file.
- src_acc_time: The accessed timestamp of the source .DS_Store file.
- src_metadata_change_time: The metadata change timestamp of the source .DS_Store file.
- src_permissions: The permissions, owner ID, and group ID of the source .DS_Store file.
- src_size: The size of the source .DS_Store file.
- block: The block within the .DS_Store that this record was parsed from.
- src_file: The location of the .DS_Store file this record was parsed from.

Record Types
--------------------------
There are 42 record types currently identified.
Some indicate that a folder was opened and other are for other miscellaneous info purposes used by Finder and do not necessarily indicated a folder was opened.

Types Indicating a Folder was Accessed
--------------------------
These records types are set when a folder has been opened in some form.
- BKGD: Finder Folder Background Picture
- bRsV: Browse in Selected View
- bwsp: Browser Window Settings
- dscl: Directory is Expanded in List View
- fdsc: Directory is Expanded in Limited Finder Window
- fwi0: Finder Window Information
- fwsw: Finder Window Sidebar Width
- fwvh: Finder Window Sidebar Height
- glvp: Gallery View Settings
- GRP0: Group Items By
- icgo: icgo. Unknown. Icon View?
- icsp: icsp. Unknown. Icon View?
- ICVO: Icon View Options
- icvo: Icon View Options
- icvp: Icon View Settings
- icvt: Icon View Text Size
- info: info: Unknown. Finder Info?:
- lssp: List View Scroll Position
- lsvC: List View Columns
- LSVO: List View Options
- lsvo: List View Options
- lsvp: List View Settings
- lsvP: List View Settings
- lsvt: List View Text Size
- pBB0: Finder Folder Background Image Bookmark
- pBBk: Finder Folder Background Image Bookmark
- pict: Background Image
- vSrn: Opened Folder in new tab
- vstl: View Style Selected

Other Miscellaneous Types
--------------------------
These record types can be set without opening a folder.
- clip: Text Clipping
- cmmt: Finder Comments
- dilc: Desktop Icon Location
- extn: File Extension
- Iloc: Icon Location
- lg1S: Logical Size
- logS: Logical Size
- modD: Modified Date
- moDD: Modified Date
- ph1S: Physical Size
- phyS: Physical Size
- ptbL: Trash Put Back Location
- ptbN: Trash Put Back Name




