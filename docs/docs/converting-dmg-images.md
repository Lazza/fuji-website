---
title: Converting DMG images
---

Fuji produces DMG disk images. Some forensic tools work more effectively with
other formats, such as sparse images or raw (uncompressed) images. This page
describes how to convert a DMG into these formats. These methods are not
specific to Fuji and apply to any compatible DMG.

## DMG to sparse image (macOS only)

Converting a DMG to a sparse image is effectively the reverse of what Fuji
does when it produces a DMG from a sparse image. The conversion usually takes
only a few minutes.

On macOS, use `hdiutil`:

``` bash
hdiutil convert /path/to/image.dmg -format UDSP -o /path/to/image.sparseimage
```

The examiner can run this on the acquired Mac itself before leaving the scene
if needed. The drawback is that the command is only available on macOS.

## DMG to uncompressed / RAW image

### On macOS

You can convert a DMG to an uncompressed disk image on macOS. The output file
will be much larger than the original.

``` bash
hdiutil convert /path/to/image.dmg -format UDRW -o /path/to/image_uncompressed.dmg
```

### On Windows and Linux

You can use [dmgwiz][dmgwiz] to extract a DMG to a raw (sector-by-sector) disk
image. The resulting file is large because it is uncompressed. Simply use the
`extract` subcommand with the input DMG and the desired output path, or see the
[documentation][dmgwiz] for other options.

``` bash
dmgwiz extract image.dmg output.raw
```

## DMG to EWF (E01) on Linux and macOS

On Linux and macOS you can produce an E01 (Expert Witness Format) image by
piping `dmgwiz` output into `ewfacquirestream` (from [libewf][libewf]):

``` bash
dmgwiz extract image.dmg /dev/stdout | ewfacquirestream
```

This can be useful in environments where E01 is the preferred format.

[dmgwiz]: https://github.com/citruz/dmgwiz
[libewf]: https://github.com/libyal/libewf
