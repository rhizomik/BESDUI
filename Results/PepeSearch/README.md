# BESDUI Results for ...

This document reports the results for the BESDUI benchmark for the [PepeSearch](https://github.com/guiveg/pepesearch) tool.

## Summary

|PEPESEARCH|Capacity|K (0.2s)|P (1.1s)|H (0.4s)|Operator Count| Time |
|----------|--------|--------|--------|--------|--------------|------|
|  Task 1  |   0%   |    x   |    y   |    z   |       n      |  0.0 |
|  Task 2  |   0%   |    x   |    y   |    z   |       n      |  0.0 |
|  Task 3  |  100%  |    5   |    3   |    3   |      11      |  5.5 |
|  Task 4  |   0%   |    x   |    y   |    z   |       n      |  0.0 |
|  Task 5  |   0%   |    x   |    y   |    z   |       n      |  0.0 |
|  Task 6  |  100%  |   22   |   11   |   11   |      44      | 20.9 |
|  Task 7  |  100%  |    4   |    2   |    2   |       8      |  3.8 |
|  Task 8  |   0%   |    x   |    y   |    z   |       n      |  0.0 |
|  Task 9  |   0%   |    x   |    y   |    z   |       n      |  0.0 |
|  Task 10 |   0%   |    x   |    y   |    z   |       n      |  0.0 |
|  Task 11 |   0%   |    x   |    y   |    z   |       n      |  0.0 |
|  Task 12 |   0%   |    x   |    y   |    z   |       n      |  0.0 |
|  SUM     |        |   31   |    Y   |    Z   |      63      | 30.2 |
|  AVERAGE |  25%   |   10.3 |    5.3 |    5.3 |      21.0    | 10.1 |

## Results per Task

**Task 1**. [Find products for a given set of features combined](/Benchmark/1.md)
> "Look for products of type **sheeny** with product features **stroboscopes** and **gadgeteers**, and a **productPropertyNumeric1** greater than **450**".

This task cannot be performed because PepeSearch does not allow to set several values for a property. More specifically, it is possible to set the product feature **stroboscopes** or **gadgeteers**, but not the two of them at the same time.


**Task 2**. [Find products for a given set of alternative features](/Benchmark/2.md)
> "List products of type **sheeny** with product features **stroboscopes** OR **gadgeteers**, and a **productPropertyNumeric1** greater than **450**".

This task cannot be performed because PepeSearch does not allow to set several values for a property. More specifically, it is possible to set the product feature **stroboscopes** or **gadgeteers**, but not the two of them at the same time.


**Task 3**. [Retrieve basic information about a specific product for display purposes](/Benchmark/3.md)
> "Get details about product **boozed**".


| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
| 1. Select "Product" in the list of concepts                  |    |  1 |  1 |
| 2. Click on the product label field and type "bo"            |  2 |  1 |  1 |
| 3. Select “boozed” from autocomplete                         |  2 |    |    |
| 4. Press enter to get results and select product "boozed"    |  1 |  1 |  1 |
| Total Operators                                              |  5 |  3 |  3 |
| Time                                                         |      5.5     |

**Task 4**. [Find products having some specific features and not having one feature](/Benchmark/4.md)
> "Look for products of type **sheeny** with product features **stroboscopes** but **NOT gadgeteers**, and **productPropertyNumeric1** value greater than **300** and **productPropertyNumeric3** smaller than **400**".

This task is not currently possible because PepeSearch does not support negation.


**Task 5**. [Find products matching two different sets of features](/Benchmark/5.md)
> "Look for products of type **sheeny** with product features **stroboscopes** and **gadgeteers** and a **productPropertyNumeric1** value greater than **300** plus those of the same product type with product features **stroboscopes** and **rotifers** and a **productPropertyNumeric2** greater than **400**".

This task cannot be performed because PepeSearch does not allow to set several values for a property. More specifically, it is possible to set the product feature **stroboscopes** or **gadgeteers**, but not the two of them at the same time.


**Task 6**. [Find products that are similar to a given product](/Benchmark/6.md)
> "Look for products similar to **boozed**, with at least one shared feature, and a **productPropertyNumeric1** value between **427 and 627** (100 more or less than its value for boozed, 527) and a **productPropertyNumeric2** value between **545 and 945** (200 more or less than its value for boozed, 745)".

The user begins by searching the product "boozed"", as in Task 3. Then, he creates a new search for a product with product feature "stroboscopes" and the ranges specified in the description.

| Interaction Steps                                                 |  K |  P |  H |
|-------------------------------------------------------------------|----|----|----|
| 1. Get information about product "boozed" (as in Task 4)          |  5 |  3 |  3 |
| 2. Go home and select "Product" in the list of concepts           |    |  2 |    |
| 3. Expand the collapsible "ProductFeature", click on the label field, type "st" and select "stroboscopes" from autocomplete|  4 |  2 |  1 |
| 4. Set the range of "productPropertyNumeric1" between 427 and 627 |  6 |  2 |  3 |
| 5. Set the range of "productPropertyNumeric2" between 545 and 945 |  6 |  2 |  3 |
| 6. Press enter to get the results                                 |  1 |    |  1 |
| Total Operators                                                   | 22 | 11 | 11 |
| Time                                                              |     20.9     |

**Task 7**. [Find products having a name that contains some text](/Benchmark/7.md)
> "Search products whose name contains **ales**".

| Interaction Steps                                                 |  K |  P |  H |
|-------------------------------------------------------------------|----|----|----|
| 1. Select "Product" in the list of concepts                       |    |  1 |  1 |
| 2. Click on the product label field and type "ales"               |  3 |  1 |  1 |
| 3. Press enter to get results                                     |  1 |    |    |
| Total Operators                                                   |  4 |  2 |  2 |
| Time                                                              |      3.8     |

**Task 8**. [Retrieve in-depth information about a specific product including offers and reviews](/Benchmark/8.md)
> "For the product **waterskiing sharpness horseshoes** list details for all its **offers** by Chinese vendors and still valid by **2008-05-28** plus details for all **reviews** for this product having either **rating1 or rating2**".

This task cannot be solved with PepeSearch due to:
1) Countries are filtered out because they do not have a type in the dataset
2) It is not possible to specify an OR clause for a datatype property value

**Task 9**. [Give me recent reviews in English for a specific product](/Benchmark/9.md)
> "For the product **waterskiing sharpness horseshoes** list the **20** more recent **reviews** in **English**".>

PepeSearch does not  provide a mechanism to filter literals by language.


**Task 10**. [Get information about a reviewer](/Benchmark/10.md)
> "Get all available information about the author of **Review5481**".

The label "Review5481" is included in the URI of a review, but there is no other data property value with this information. Since PepeSearch does not allow searches in resource URIs, the task cannot be fulfilled.


**Task 11**. [Get offers for a given product which fulfill specific requirements](/Benchmark/11.md)
> "Look for the **cheapest** and still **valid** by **2008-06-15** **offer** for the product **waterskiing sharpness horseshoes** by a **US vendor** that is able to **deliver** within **3 days**".

This task cannot be solved with PepeSearch because the countries of the dataset are filtered out (as they do not have a specific type).


**Task 12**. [Export the chosen offer into another information system which uses a different schema](/Benchmark/12.md)
> "Save in the local computer the information about the vendor for **Offer3499**, this is **half** the task. To **complete** it, restrict the output to just label, homepage and country and **map** them to schema.org terms name, url and nationality".

PepeSearch does not provide a way to map data and export it using a different schema.
