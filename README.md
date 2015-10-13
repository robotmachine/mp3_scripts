# RoboTag
### Version 2.1

### Dependencies:
* [eyeD3](http://eyed3.nicfit.net) v0.7.5
* [Image Magick](http://imagemagick.org)
* [glyr](https://github.com/sahib/glyr)

## How It Works
RoboTag uses file names, directory names, and metadata files to create ID3v2 tags on MP3 files. The goal is to create clean tags without unwanted junk in them without having to go full manual. As an added bonus the use of metadata files allows non Latin characters to be stored safely outside of filenames while still resulting in properly spelled tags.  

RoboTag expects a directory structure where an Artist Name directory contains Album Name directories which then contain MP3 files. An example of the full path to the fifth track on the second disc of Radiohead's 2007 album "In Rainbows" would be as follows:
`/home/brian/music/Radiohead/2007 In Rainbows/02-05 Last Flowers.mp3`

RoboTag is run from inside the Album Name folder and will find MP3 files located within.  

### Metadata Files
A metadata file inside of the Album Name folder will supersede a metadata file of the same name in the Artist Name directory. (ie. If both `2007 In Rainbows/.genre.txt` and `Radiohead/.genre.txt` in the example above, the data from `2007 In Rainbows/.genre.txt` will be used.  
Only the first line is read for files that are only meant to contain a single value (ie. .artist.txt). Any additional data will not be used.  

#### .album.txt
Contains the title of the album.  

#### .albumartist.txt
Contains the name to be used in the Album Artist field.  
Example usage: Thee Silver Mt. Zion Memorial Orchestra has used several different names for various releases, but you don't want them randomly sorted everywhere. Album Artist is supported by most MP3 players and will allow all releases to be sorted together, but display the right artist name for the release.  

#### .artist.txt
Contains the artist name.

#### .genre.txt
Contains the genre name for the artist or album.    

#### .tracks01.txt; tracks02.txt; &c
The title of the album tracks. The first line corresponds to the first track and so on. In the event of a multi-disc album, the metadata file should be .tracks01.txt, tracks02.txt and so on.  

Within the Artist Name folder, the following metadata files are supported:
* .artist.txt
* .genre.txt

Within the Album Name folder, the following metadata files are supported:
* .album.txt
* .albumartist.txt
* .artist.txt
* .genre.txt
* .tracks01.txt
* .year.txt
