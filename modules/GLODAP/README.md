# GLODAP module

[Data source](https://glodap.info/index.php/mapped-data-product/)

**Status**: This is a work in progress. Currently the data is not downloading using the module

example usage for this module
```julia
using NumericalEarth
using Oceananigans
using .GLODAP

arch = CPU()

meta = Metadatum(:alkalinity, dataset=GLODAPClimatology())

fields = Field(meta, arch)

```