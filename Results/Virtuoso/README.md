# SDEBM Results for Virtuoso

This document reports the results for the SDEBM benchmark for the [Virtuoso](http://virtuoso.openlinksw.com/dataspace/doc/dav/wiki/Main/) tool.

## Summary

|Benchmark|Task Success|Interaction Steps|Speed|
|---------|------------|-----------------|-----|
|1        | 0%         | 28K, 18P, 5H    | 27.4|
|2        | 100%       |                 |     |
|3        | 100%       | 1K, 1P          |  1.3|
|4        | 0%         |                 |     |
|5        | 0%         |                 |     |
|6        | 0%         |                 |     |
|7        | 100%       | 14K, 2P, 3H     |  6.2|
|8        |            |                 |
|9        |            |                 |
|10       |            |                 |
|11       |            |                 |
|12       |            |                 |
|13       |            |                 |

## Results per Task

**Task 1**. [Find products for a given set of features combined](Benchmarks/1.md)

Virtuoso Facets can complete this task and the outcome is the expected considering the sample dataset, the products “driveled” and “auditoriums reducing pappies”. To complete this task, the interaction steps are and KLM operators are:

| Interaction Steps                                               | K | P | H |
|-----------------------------------------------------------------|---|---|---|
| 1. Type “sheeny” and “Enter”, then click “ProductType10”        | 9 | 2 | 3 |
| 2. Click “Go” for “Start New Facet”, then click "Options"       | 2 | 2 |   |
| 3. Click “Inference Rule” and select rules then "Apply"         | 2 | 2 |   |
| 4. Click “Attributes”, then “productFeature” and “stroboscopes" | 3 | 3 |   |
| 5. Click “Attributes”, then “productFeature” and “gadgeteers”   | 3 | 3 |   |
| 6. Click “Attributes” and “productPropertyNumeric1”             | 2 | 2 |   |
| 7. Click “Add condition: None” and select “>”                   | 2 | 2 |   |
| 8. Type “450” and click “Set Condition”                         | 5 | 2 | 2 |
| Total KLM Operations                                            | 28| 18| 5 |
| Speed                                                           |    27.4   |

**Task 2**. [Find products for a given set of alternative features](Benchmarks/2.md)

Virtuoso, on the other hand, does not seem to feature a mechanism to define alternative values for a property. Consequently, it is not possible to complete this task with this tool.

**Task 3**. [Retrieve basic information about a specific product for display purposes](Benchmarks/2.md)

From Task one Virtuoso shows the list of selected products. Click any product to retrieve all the metadata for the selected product..

The interaction steps and KLM Operators are:

| Interaction Steps                                               | K | P | H |
|-----------------------------------------------------------------|---|---|---|
| 1. Click product label "driveled"                               | 1 | 1 |   |
| Speed                                                           |    1.3    |

**Task 4**. [Find products having some specific features and not having one feature](Benchmarks/4.md)

Virtuoso Facets does not seem to support this task. Though it is possible to specify that a property is different from a particular URI, or not int a set of defined URIs, it is not possible to define that a particular URI should not exist.

**Task 5**. [Find products matching two different sets of features](Benchmarks/5.md)

There does not seem to be a way to define a union of patters with Rhizomer.

**Task 6**. [Find products that are similar to a given product](Benchmarks/6.md)

There is not a way to get a faceted view of a given product and the relax the restrictions.

**Task 7**. [Find products having a name that contains some text](Benchmarks/7.md)

The interaction steps are:

| Interaction Steps                                               | K | P | H |
|-----------------------------------------------------------------|---|---|---|
| 1. Type "waterskiing" in the main page search form              |13 | 1 | 2 |
| 2. Click "Product768"                                           | 1 | 1 | 1 |
| Total KLM Operations                                            |14 | 2 | 3 |
| Speed                                                           |    6.2    |

**Task 8**. [Retrieve in-depth information about a specific product including offers and reviews](Benchmarks/8.md)


**Task 9**. [Give me recent reviews in English for a specific product](Benchmarks/9.md)


**Task 10**. [Get information about a reviewer](Benchmarks/10.md)


**Task 11**. [Get offers for a given product which fulfill specific requirements](Benchmarks/11.md)


**Task 12**. [Get all information about an offer](Benchmarks/12.md)


**Task 13**. [Export the chosen offer into another information system which uses a different schema](Benchmarks/13.md)
