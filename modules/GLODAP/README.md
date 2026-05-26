# GLODAP module

[Data source](https://glodap.info/index.php/mapped-data-product/)

**Status**: runs successfully! But need to check units

# Example 

```julia
using NumericalEarth
using Oceananigans
using .GLODAP

arch = CPU()

meta = Metadatum(:alkalinity, dataset=GLODAPClimatology())

fields = Field(meta, arch)
```