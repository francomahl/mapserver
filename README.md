# MapServer

### Run

```sh
docker-compose up
```

### Download source image and rename it as 5band.tiff
https://drive.google.com/file/d/0B-vzf2mGcaRzWnFmYzBpZVhJd3c/view

### Requests

**WCS query to MapServer selecting bands 1,2,3:**

http://localhost:8080/?map=/maps/config.map&SERVICE=WCS&VERSION=2.0.1&REQUEST=GetCoverage&COVERAGEID=fband&FORMAT=image%2Ftiff&SCALESIZE=x(512),y(512)&SUBSETTINGCRS=EPSG%3A4326&SUBSET=x,EPSG:4326(-119.6386,-119.3585)&SUBSET=y,EPSG:4326(34.8851,35.1154)&RANGESUBSET=1,2,3

**Output file out(3).tif**

```sh
gdalinfo -stats out\ \(3\).tif 
```

```sh
Driver: GTiff/GeoTIFF
Files: out (3).tif
Size is 512, 512
Coordinate System is:
GEOGCS["WGS 84",
    DATUM["WGS_1984",
        SPHEROID["WGS 84",6378137,298.257223563,
            AUTHORITY["EPSG","7030"]],
        AUTHORITY["EPSG","6326"]],
    PRIMEM["Greenwich",0],
    UNIT["degree",0.0174532925199433],
    AUTHORITY["EPSG","4326"]]
Origin = (-119.638599999999983,35.115400000000001)
Pixel Size = (0.000547070312500,-0.000449804687500)
Metadata:
  AREA_OR_POINT=Area
  TIFFTAG_RESOLUTIONUNIT=2 (pixels/inch)
  TIFFTAG_XRESOLUTION=72
  TIFFTAG_YRESOLUTION=72
Image Structure Metadata:
  INTERLEAVE=PIXEL
Corner Coordinates:
Upper Left  (-119.6386000,  35.1154000) (119d38'18.96"W, 35d 6'55.44"N)
Lower Left  (-119.6386000,  34.8851000) (119d38'18.96"W, 34d53' 6.36"N)
Upper Right (-119.3585000,  35.1154000) (119d21'30.60"W, 35d 6'55.44"N)
Lower Right (-119.3585000,  34.8851000) (119d21'30.60"W, 34d53' 6.36"N)
Center      (-119.4985500,  35.0002500) (119d29'54.78"W, 35d 0' 0.90"N)
Band 1 Block=512x4 Type=Byte, ColorInterp=Red
  Minimum=0.000, Maximum=176.000, Mean=14.751, StdDev=10.563
  Metadata:
    STATISTICS_MAXIMUM=176
    STATISTICS_MEAN=14.751251220703
    STATISTICS_MINIMUM=0
    STATISTICS_STDDEV=10.562612605579
Band 2 Block=512x4 Type=Byte, ColorInterp=Green
  Minimum=0.000, Maximum=201.000, Mean=21.681, StdDev=13.437
  Metadata:
    STATISTICS_MAXIMUM=201
    STATISTICS_MEAN=21.681121826172
    STATISTICS_MINIMUM=0
    STATISTICS_STDDEV=13.436800538165
Band 3 Block=512x4 Type=Byte, ColorInterp=Blue
  Minimum=0.000, Maximum=198.000, Mean=23.918, StdDev=17.781
  Metadata:
    STATISTICS_MAXIMUM=198
    STATISTICS_MEAN=23.917995452881
    STATISTICS_MINIMUM=0
    STATISTICS_STDDEV=17.780657246315
Band 4 Block=512x4 Type=Byte, ColorInterp=Undefined
  Minimum=0.000, Maximum=255.000, Mean=243.759, StdDev=52.346
  Metadata:
    STATISTICS_MAXIMUM=255
    STATISTICS_MEAN=243.7589263916
    STATISTICS_MINIMUM=0
    STATISTICS_STDDEV=52.346079454647
```

**WCS query to MapServer selecting bands 1,2,3,4:**

http://localhost:8080/?map=/maps/config.map&SERVICE=WCS&VERSION=2.0.1&REQUEST=GetCoverage&COVERAGEID=fband&FORMAT=image%2Ftiff&SCALESIZE=x(512),y(512)&SUBSETTINGCRS=EPSG%3A4326&SUBSET=x,EPSG:4326(-119.6386,-119.3585)&SUBSET=y,EPSG:4326(34.8851,35.1154)&RANGESUBSET=1,2,3,4

**Output file out(4).tif**

```sh
gdalinfo -stats out\ \(4\).tif 
```

```sh
Driver: GTiff/GeoTIFF
Files: out (4).tif
Size is 512, 512
Coordinate System is:
GEOGCS["WGS 84",
    DATUM["WGS_1984",
        SPHEROID["WGS 84",6378137,298.257223563,
            AUTHORITY["EPSG","7030"]],
        AUTHORITY["EPSG","6326"]],
    PRIMEM["Greenwich",0],
    UNIT["degree",0.0174532925199433],
    AUTHORITY["EPSG","4326"]]
Origin = (-119.638599999999983,35.115400000000001)
Pixel Size = (0.000547070312500,-0.000449804687500)
Metadata:
  AREA_OR_POINT=Area
  TIFFTAG_RESOLUTIONUNIT=2 (pixels/inch)
  TIFFTAG_XRESOLUTION=72
  TIFFTAG_YRESOLUTION=72
Image Structure Metadata:
  INTERLEAVE=PIXEL
Corner Coordinates:
Upper Left  (-119.6386000,  35.1154000) (119d38'18.96"W, 35d 6'55.44"N)
Lower Left  (-119.6386000,  34.8851000) (119d38'18.96"W, 34d53' 6.36"N)
Upper Right (-119.3585000,  35.1154000) (119d21'30.60"W, 35d 6'55.44"N)
Lower Right (-119.3585000,  34.8851000) (119d21'30.60"W, 34d53' 6.36"N)
Center      (-119.4985500,  35.0002500) (119d29'54.78"W, 35d 0' 0.90"N)
Band 1 Block=512x4 Type=Byte, ColorInterp=Red
  Minimum=0.000, Maximum=175.000, Mean=10.548, StdDev=11.556
  Metadata:
    STATISTICS_MAXIMUM=175
    STATISTICS_MEAN=10.547557830811
    STATISTICS_MINIMUM=0
    STATISTICS_STDDEV=11.556411228163
Band 2 Block=512x4 Type=Byte, ColorInterp=Green
  Minimum=0.000, Maximum=199.000, Mean=17.559, StdDev=14.457
  Metadata:
    STATISTICS_MAXIMUM=199
    STATISTICS_MEAN=17.558898925781
    STATISTICS_MINIMUM=0
    STATISTICS_STDDEV=14.457137666237
Band 3 Block=512x4 Type=Byte, ColorInterp=Blue
  Minimum=0.000, Maximum=196.000, Mean=19.798, StdDev=18.754
  Metadata:
    STATISTICS_MAXIMUM=196
    STATISTICS_MEAN=19.79761505127
    STATISTICS_MINIMUM=0
    STATISTICS_STDDEV=18.753888418108
Band 4 Block=512x4 Type=Byte, ColorInterp=Undefined
  Minimum=0.000, Maximum=189.000, Mean=35.913, StdDev=15.675
  Metadata:
    STATISTICS_MAXIMUM=189
    STATISTICS_MEAN=35.91284942627
    STATISTICS_MINIMUM=0
    STATISTICS_STDDEV=15.674673112687
```