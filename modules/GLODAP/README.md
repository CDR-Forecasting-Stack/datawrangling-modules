# GLODAP module

[Data source](https://glodap.info/index.php/mapped-data-product/)

**Status**: The data downloads, but having some issues with the `retrieve_data` function.

# Error message
```julia
ERROR: LoadError: MethodError: objects of type Dict{Symbol, String} are not callable
The object of type `Dict{Symbol, String}` exists, but no method is defined for this combination of argument types when trying to treat it as a callable object.
Stacktrace:
 [1] retrieve_data(metadata::Metadatum{GLODAPClimatology, Nothing, Nothing, Symbol, String})
   @ Main.GLODAP ~/projects/datawrangling-modules/example.jl:174
 [2] Field(metadata::Metadatum{GLODAPClimatology, Nothing, Nothing, Symbol, String}, arch::CPU; inpainting::NumericalEarth.DataWrangling.NearestNeighborInpainting{Int64}, mask::Nothing, halo::Tuple{Int64, Int64, Int64}, cache_inpainted_data::Bool)
   @ NumericalEarth.DataWrangling ~/.julia/packages/NumericalEarth/va8kf/src/DataWrangling/metadata_field.jl:238
 [3] Field(metadata::Metadatum{GLODAPClimatology, Nothing, Nothing, Symbol, String}, arch::CPU)
   @ NumericalEarth.DataWrangling ~/.julia/packages/NumericalEarth/va8kf/src/DataWrangling/metadata_field.jl:194
 [4] top-level scope
   @ ~/projects/datawrangling-modules/example.jl:239
 [5] include(mod::Module, _path::String)
   @ Base ./Base.jl:306
 [6] exec_options(opts::Base.JLOptions)
   @ Base ./client.jl:317
 [7] _start()
   @ Base ./client.jl:550
```

# Example 

```julia
using NumericalEarth
using Oceananigans
using .GLODAP

arch = CPU()

meta = Metadatum(:alkalinity, dataset=GLODAPClimatology())

fields = Field(meta, arch)

```