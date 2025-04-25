---
title: "3D printable ITX mounting brackets"
draft: false
menu:
  docs:
    title:
    parent: "ROCKPro64/Hardware"
    identifier: "ROCKPro64/Hardware/3D_printable_ITX_mounting_brackets"
    weight:
---

{{< figure src="/documentation/images/ITX-Bracket-Mounted.jpg" title="A Quartz64-A mounted in an ITX case using 3D printed brackets" width="300" >}}

Allows mounting a ROCKPro64-A or Quartz64-A board inside a regular PC case that conforms to the ITX standard, using 3D printed brackets:

* AMF/STL/STEP files plus the original FreeCAD file used to create the models https://wiki.pine64.org/wiki/File:RP64-A_Q64-A_to_ITX_mounting_brackets.zip
* Make sure to flip the two brackets by 180 degrees on one of the horizontal axes (X/Y) in your slicer of choice before printing to avoid unnecessary supports
* To allow enough clearance between the board and the bracket you either need to print four copies of the washer model or add nut(s) between the board and the bracket
* If using nuts for the clearance between the board and the brackets, make sure it creates at least 3.2mm of spacing in between
* Depending on the accuracy and calibration of a 3D printer, slight deviation can occur and you likely need to manually widen some of the holes to allow screws to fit
