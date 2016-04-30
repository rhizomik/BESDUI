# SDEBM Results for Virtuoso

This document reports the results for the SDEBM benchmark for the [Virtuoso](http://virtuoso.openlinksw.com/dataspace/doc/dav/wiki/Main/) tool.

## Summary

Two [Quality in Use metrics](http://www.jucs.org/jucs_19_8/using_SWET_QUM_to) have been used, one about effectiveness and the other about efficiency:

* **Capacity** (effectiveness): what proportion of one task is completed. 0% if not possible to complete or 100% otherwise.
* **Operation Count** (efficiency): how many clicks C, how many typing events T and how many slides S are required at least to complete the task.
* **Speed** (efficiency)

|Benchmark|Task Success|Interaction Steps|
|---------|------------|-----------------|
|1        | 100%       | 17C/2T          |
|2        | 0%         |                 |
|3        | 100%       | 1C              |
|4        |            | |
|5        |            | |
|6        |            | |

## Results per Benchmarks

**Task 1**. [Find products for a given set of features combined](Benchmarks/1.md)

Virtuoso Facets can complete this task and the outcome is the expected considering the sample dataset, the products “driveled” and “auditoriums reducing pappies”. To complete this task, the interaction steps are:

1.	Type “sheeny” and click “Search”.
2.	Click “ProductType10”.
3.	Click “Go” for “Start New Facet”.
4.	Click “Options”.
5.	For “Interence Rule” Click and then Select graph containing inference rules for the dataset, for instance http://rhizomik.net/bsbm/schema/rules/
6.	Click “Apply”.
7.	Click “Attributes”.
8.	Click “productFeature”.
9.	Click “stroboscopes”.
10.	Click “Attributes”.
11.	Click “productFeature”.
12.	Click “gadgeteers”.
13.	Click “Attributes”.
14.	Click “productPropertyNumeric1”.
15.	Click “Add condition: None” and select “>”.
16.	Type “450” and click “Set Condition”.

**Task 2**. [Find products for a given set of alternative features](Benchmarks/2.md)

Virtuoso, on the other hand, does not seem to feature a mechanism to define alternative values for a property. Consequently, it is not possible to complete this task with this tool.

**Task 3**. [Retrieve basic information about a specific product for display purposes](Benchmarks/2.md)

From Task one Virtuoso shows the list of selected products. Click any product to retrieve all the metadata for the selected product..

Interaction steps:

1. Click product label "driveled".

**Task 4**. [Find products having some specific features and not having one feature](Benchmarks/4.md)

**Task 5**. [Find products matching two different sets of features](Benchmarks/5.md)


**Task 6**. [Find products that are similar to a given product](Benchmarks/6.md)


**Task 7**. [Find products having a name that contains some text](Benchmarks/7.md)


**Task 8**. [Retrieve in-depth information about a specific product including offers and reviews](Benchmarks/8.md)


**Task 9**. [Give me recent reviews in English for a specific product](Benchmarks/9.md)


**Task 10**. [Get information about a reviewer](Benchmarks/10.md)


**Task 11**. [Get offers for a given product which fulfill specific requirements](Benchmarks/11.md)


**Task 12**. [Get all information about an offer](Benchmarks/12.md)


**Task 13**. [Export the chosen offer into another information system which uses a different schema](Benchmarks/13.md)
