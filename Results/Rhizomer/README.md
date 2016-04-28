# SDEBM Results for Rhizomer

This document reports the results for the SDEBM benchmark for the [Rhizomer](http://rhizomik.net/rhizomer/) tool, a semantic data exploration and visualization tool. Rhizomer automatically generates, after analyzing the semantic dataset, some user interface components to explore it. First, they facilitate gaining an overview of the dataset structure, concretely menus, TreeMaps, site maps and site indexes. Then, zooming and filtering into details through facets and the ability to pivot among sets of interrelated resources.

## Summary

Two [Quality in Use metrics](http://www.jucs.org/jucs_19_8/using_SWET_QUM_to) have been used, one about effectiveness and the other about efficiency:

* **Task Success** (effectiveness): what proportion of one task is completed. 0% if not possible to complete or 100% otherwise.
* **Interaction Steps** (efficiency): how many clicks C and how many typing events T are required at least to complete the task.

|Benchmark|Task Success|Interaction Steps|
|---------|-------------|----------------|
|1a       |0%           |-               |
|1b       |100%         |5C/1T           |
|2        |             | |
|3        |             | |
|4        |             | |
|5        |             | |

## Results per Benchmarks

**Benchmark 1a**. [Find products for a given set of features combined](Benchmarks/1a.md)

This task cannot be performed because Rhizomer does not provide a way to define that all the selected values of a facet, in this case the productFeature facet, should be present at the same time for a given resource.

**Benchmark 1b**. [Find products for a given set of alternative features](Benchmarks/1b.md)

Interaction steps:

1. Over Top Menu “ProductType”.
1. Click “Sheeny” from submenu.
1. Click “Show values” for facet “Product Feature”.
1. Check facet value “stroboscopes”.
1. Type in the “Search Product Feature” input box “gadget...”.
1. Click “gadgeteers” from the input box autocomplete recommendations.
1. Set the left side of the slider for facet “Product Property Numeric1” to “450”. (Or type “450” in the “From” input box for facet “Product Property Numeric1” and then press tabulator).

**Benchmark 2**. [Retrieve basic information about a specific product for display purposes](Benchmarks/2.md)

**Benchmark 3**. [Find products having some specific features and not having one feature](Benchmarks/3.md)

**Benchmark 4**. [Find products matching two different sets of features](Benchmarks/4.md)

**Benchmark 5**. [Find products that are similar to a given product](Benchmarks/5.md)

**Benchmark 5**. [Find products having a name that contains some text](Benchmarks/6.md)

...work in progress
