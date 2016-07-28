```
NAME
    cd2mp3 - simple command-line script to rip an audio cd to mp3 files.

SYNOPSIS 
    cd2mp3 [options] <album-directory>

DESCRIPTION
    cd2mp3 is a Bash command-line Ruby script which can be used to
    encode an audio cd in mp3 format. It requires ruby, cdparanoia, and
    lame to function properly. Make sure these are installed on your
    system before using this tool.

    cd2mp3 outputs files to the specified location in the format
    '<track number> - <track title>.mp3'.

OPTIONS
    -d data-file    path to file containing album info in a Ruby hash.

                    The data file is organized as follows:

                    @album_info = { 
                        album_title: 'title of album',
                        album_artist: 'artist for entire album',
                        album_genre: 'genre of album',
                        album_year: year of album,
                        album_art: 'path to jpg of album cover',
                        collection: 'name of collection for album',
                        sequence_number: 'sequence in collection',

                        tracks: [ 
                            { track_number: '01',
                              track_title: 'title of first track',
                              track_artist: 'artist for first track' },

                            rest of tracks as a nested hash

                        ]
                    }

                    Note that @ symbol in front of album_info. Since
                    this file will end up being required as a .rb file,
                    you are essentially creating a Ruby instance
                    variable.

    -q quality      either 1, 2, or 3:

                    1 corresponds to lame preset extreme
                    2 corresponds to lame preset standard
                    3 corresponds to lame preset medium

EXAMPLES

    Encode a cd from a datafile named album.info with quality level 2:

        cd2mp3 -d album.info -q 2 $HOME/Music/Artist/Album

    Note the use of environment variables; shell escape sequences are
    not advised (i.e., don't type ~/Music/Artist/Album). Doing so will
    create a literal '~' directory and then Music/Artist/Album inside.

TO DO

    - Add an option to select common output naming formats:

        <track number> - <track title>.mp3
        <track artist> - <track title>.mp3
        etc.

    - Establish album info lookup instead of requiring a data file

    - Add an option for customized lame options

    - Create a graphical interface

    - Rewrite this in Python (?)

LICENSE

    Copyright (c) 2016 Guymon Hall

    Permission is hereby granted, free of charge, to any person
    obtaining a copy of this software and associated documentation files
    (the "Software"), to deal in the Software without restriction,
    including without limitation the rights to use, copy, modify, merge,
    publish, distribute, sublicense, and/or sell copies of the Software,
    and to permit persons to whom the Software is furnished to do so,
    subject to the following conditions:

    The above copyright notice and this permission notice shall be
    included in all copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
    EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
    MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
    NONINFRINGEMENT.  IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS
    BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN
    ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
    CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
    SOFTWARE.
```
