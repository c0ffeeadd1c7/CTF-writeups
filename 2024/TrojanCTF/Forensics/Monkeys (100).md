---
category: forensics
points: "100"
description: Image metadata
---
An file were given without an extention.
First thought was to see the output of the file command:
```
arctic: JPEG image data, JFIF standard 1.01, resolution (DPI), density 300x300, segment length 16, Exif Standard: [TIFF image data, little-endian, direntries=0], comment: "Trojan{wh0_tHe_f***_ArE_aRctIC_mOnKEyS?}", progressive, precision 8, 3200x2316, components 3
```
And the comment metadata field of the this image file contained the flag.
Otherwise to work with metadata I heard exiftools is a great tool.

