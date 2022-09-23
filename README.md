# photo-workflow

This implements my workflow for importing photos and videos from various
devices into my library. It's probably fairly idiosyncratic but may just be
useful for others, so here goes. It performs the following tasks:

* Strips GPS tags from photos from certain devices that are known to add bogus ones
* Rotates photos according to EXIF orientation tag using `exifautotran`
* Finds suitable candidates for GPX files photos could be correlated with
* GPS-correlates photos with the above files or manually specified ones,
distinguishing between various GPS trackers
(currently supported: btq1000-based devices, OSMand, Tiny Travel Tracker)
* Renames files to include a time stamp as a prefix so they will sort
chronologically even in a directory that mixes files from various cameras.

## Requirements
* `exifautotran`
* `gpscorrelate`
* Perl 5.24 or higher
* Perl modules `Moo`, `Types::Standard`, `Path::Tiny`, `Image::ExifTool`,
`DateTime` and `XML::Twig`

## TODO
* Add a config file for things like camera models
* Make supported GPS devices configurable, including corresponding `gpscorrelate` args
