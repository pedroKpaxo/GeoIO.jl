# GeoIO.jl

[![][build-img]][build-url] [![][codecov-img]][codecov-url]

Load geospatial data from known file formats
as geospatial tables compatible with the
[GeoStats.jl](https://github.com/JuliaEarth/GeoStats.jl)
framework. 

GeoIO.jl uses various backend packages spread across
different Julia organizations to load a universal
representation of geospatial data as discussed in
the book ["Geospatial Data Science with Julia"]().

## Supported formats

- .shp
- .geojson
- .parquet
- .gpkg
- .kml
- .jpg
- .jpeg
- .png
- .tif
- .tiff
- .ply

## Usage

### Loading/saving data from/to disk

The `load` and `save` functions are self-explanatory:

```julia
using GeoIO

table = GeoIO.load("file.shp")

GeoIO.save("file.geojson", table)
```

Additional keyword arguments are forwarded to the backends:

```julia
# read `.geojson` geometries with Float64 precision
table = GeoIO.load("file.geojson", numbertype = Float64)

# force writing on existing `.shp` file
GeoIO.save("file.shp", table, force = true)
```

Please read the docstrings for more details.

### Loading data from GADM

The `gadm` function (down)loads data from the GADM dataset:

```julia
julia> GeoIO.gadm("BRA", depth = 1)
```

Please read the docstring for more details.

## Asking for help

If you have any questions, please [contact our community](https://juliaearth.github.io/GeoStats.jl/stable/about/community.html).

[build-img]: https://img.shields.io/github/actions/workflow/status/JuliaEarth/GeoIO.jl/CI.yml?branch=master&style=flat-square
[build-url]: https://github.com/JuliaEarth/GeoIO.jl/actions

[codecov-img]: https://img.shields.io/codecov/c/github/JuliaEarth/GeoIO.jl?style=flat-square
[codecov-url]: https://codecov.io/gh/JuliaEarth/GeoIO.jl
