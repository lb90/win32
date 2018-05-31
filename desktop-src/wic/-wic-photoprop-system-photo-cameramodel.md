---
Description: The photo metadata policy for the System.Photo.CameraModel property.
ms.assetid: ff85e6ee-dc75-45bc-a406-2290b012c22d
title: System.Photo.CameraModel Photo Metadata Policy
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# System.Photo.CameraModel Photo Metadata Policy

The photo metadata policy for the [System.Photo.CameraModel](http://msdn.microsoft.com/en-us/library/bb760388(VS.85).aspx) property.

### PKEY

PKEY\_Photo\_CameraModel

### Containers

JPEG, TIFF

### Read-Only

No

### Output PROPVARIANT Type

VT\_LPWSTR

### Input Type

String.

### Conflict Resolution Policy

Values from different schemas are reconciled.

### JPEG Policy

### Read Paths



| Order | Path                   | Disk Format |
|-------|------------------------|-------------|
| 1     | /app1/ifd/{ushort=272} | ascii       |
| 2     | /xmp/tiff:Model        | unicode     |
| 3     | /xmp/tiff:model        | unicode     |



 

### Write Paths



| Order | Path                   | Disk Format |
|-------|------------------------|-------------|
| 1     | /app1/ifd/{ushort=272} | ascii       |
| 2     | /xmp/tiff:Model        | unicode     |
| 3     | /xmp/tiff:model        | unicode     |



 

### Remove Paths



| Order | Path                   |
|-------|------------------------|
| 1     | /app1/ifd/{ushort=272} |
| 2     | /xmp/tiff:Model        |
| 3     | /xmp/tiff:model        |



 

### TIFF Policy

### Read Paths



| Order | Path                | Disk Format |
|-------|---------------------|-------------|
| 1     | /ifd/{ushort=272}   | ascii       |
| 2     | /ifd/xmp/tiff:Model | unicode     |
| 3     | /ifd/xmp/tiff:model | unicode     |



 

### Write Paths



| Order | Path                | Disk Format |
|-------|---------------------|-------------|
| 1     | /ifd/{ushort=272}   | ascii       |
| 2     | /ifd/xmp/tiff:Model | unicode     |
| 3     | /ifd/xmp/tiff:model | unicode     |



 

### Remove Paths



| Order | Path                |
|-------|---------------------|
| 1     | /ifd/{ushort=272}   |
| 2     | /ifd/xmp/tiff:Model |
| 3     | /ifd/xmp/tiff:model |



 

## Remarks

## Related topics

<dl> <dt>

[System.Photo.CameraModel](http://msdn.microsoft.com/en-us/library/bb760388(VS.85).aspx)
</dt> </dl>

 

 


