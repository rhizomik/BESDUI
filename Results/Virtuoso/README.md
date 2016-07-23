# BESDUI Results for Virtuoso

This document reports the results for the BESDUI benchmark for the [Virtuoso](http://virtuoso.openlinksw.com/dataspace/doc/dav/wiki/Main/) tool.

## Summary

|VIRTUOSO|Capacity|K (0.2s)|P (1.1s)|H (0.4s)|Operator Count|Time |
|--------|--------|--------|--------|--------|--------------|-----|
|Task 1  |100%    |28      |18      |5       |51            |27.4 |
|Task 2  |100%    |29      |19      |5       |53            |28.7 |
|Task 3  |100%    |9       |2       |3       |14            |5.2  |
|Task 4  |0%      |        |        |        |              |     |
|Task 5  |0%      |        |        |        |              |     |
|Task 6  |0%      |        |        |        |              |     |
|Task 7  |0%      |        |        |        |              |     |
|Task 8  |100%    |33      |21      |3       |57            |30.9 |
|Task 9  |0%      |        |        |        |              |     |
|Task 10 |100%    |2       |2       |0       |4             |2.6  |
|Task 11 |100%    |41      |26      |5       |72            |38.8 |
|Task 12 |50%     |1       |1       |0       |2             |1.3  |
|SUM     |        |143     |89      |21      |253           |134.9|
|AVERAGE |54%     |20.4    |12.7    |3.0     |36.1          |19.3 |

## Results per Task

**Task 1**. [Find products for a given set of features combined](/Benchmark/1.md)
> "Look for products of type **sheeny** with product features **stroboscopes** and **gadgeteers**, and a **productPropertyNumeric1** greater than **450**".

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
| Time                                                            |    27.4   |

**Task 2**. [Find products for a given set of alternative features](/Benchmark/2.md)
> "List products of type **sheeny** with product features **stroboscopes** OR **gadgeteers**, and a **productPropertyNumeric1** greater than **450**".

Virtuoso also supports this task in a very similar way to Task 1, though in this case alternative feature values are defined using the “Add condition: IN” feature.

| Interaction Steps                                               | K | P | H |
|-----------------------------------------------------------------|---|---|---|
| 1. Type “sheeny” and “Enter”, then click “ProductType10”        | 9 | 2 | 3 |
| 2. Click “Go” for “Start New Facet”, then click "Options"       | 2 | 2 |   |
| 3. Click “Inference Rule” and select rules then "Apply"         | 2 | 2 |   |
| 4. Click “Attributes”, then “productFeature”                    | 1 | 1 |   |
| 5. Click “Add condition: None” and select “>”                   | 2 | 2 |   |
| 6. Click "stroboscopes" and then "Add value"                    | 2 | 2 |   |
| 7. Click "gadgeteers" and then "Set IN Condition"               | 2 | 2 |   |
| 6. Click “Attributes” and “productPropertyNumeric1”             | 2 | 2 |   |
| 7. Click “Add condition: None” and select “>”                   | 2 | 2 |   |
| 8. Type “450” and click “Set Condition”                         | 5 | 2 | 2 |
| Total KLM Operations                                            | 29| 19| 5 |
| Time                                                            |    28.7   |

**Task 3**. [Retrieve basic information about a specific product for display purposes](/Benchmark/3.md)
> "Get details about product **boozed**".

Using the entry page search box, the user types “boozed” and finally clicks the entry for the requested product in the results listing to get the product details.

| Interaction Steps                                               | K | P | H |
|-----------------------------------------------------------------|---|---|---|
| 1. Type "boozed" in search form and "Enter"                     | 8 | 1 | 2 |
| 2. Point to the "boozed" product entry in results               | 1 | 1 | 1 |
| Total KLM Operations                                            | 9 | 2 | 3 |
| Time                                                            |    5.2    |

**Task 4**. [Find products having some specific features and not having one feature](/Benchmark/4.md)
> "Look for products of type **sheeny** with product features **stroboscopes** but **NOT gadgeteers**, and **productPropertyNumeric1** value greater than **300** and **productPropertyNumeric3** smaller than **400**".

Virtuoso Facets does not seem to support this task. Though it is possible to specify that a property is different from a particular URI, or not int a set of defined URIs, it is not possible to define that a particular URI should not exist.

**Task 5**. [Find products matching two different sets of features](/Benchmark/5.md)
> "Look for products of type **sheeny** with product features **stroboscopes** and **gadgeteers** and a **productPropertyNumeric1** value greater than **300** plus those of the same product type with product features **stroboscopes** and **rotifers** and a **productPropertyNumeric2** greater than **400**".

There does not seem to be a way to define a union of patters with Rhizomer.

**Task 6**. [Find products that are similar to a given product](/Benchmark/6.md)
> "Look for products similar to **boozed**, with at least one shared feature, and a **productPropertyNumeric1** value between **427 and 627** (100 more or less than its value for boozed, 527) and a **productPropertyNumeric2** value between **545 and 945** (200 more or less than its value for boozed, 745)".

There is not a way to get a faceted view of a given product and the relax the restrictions.

**Task 7**. [Find products having a name that contains some text](/Benchmark/7.md)
> "Search products whose name contains **ales**".

Virtuoso does not generate REGEX-based queries and the "bif:contains" does not seem to work with part of words.

**Task 8**. [Retrieve in-depth information about a specific product including offers and reviews](/Benchmark/8.md)
> "For the product **waterskiing sharpness horseshoes** list details for all its **offers** by Chinese vendors and still valid by **2008-05-28** plus details for all **reviews** for this product having either **rating1 or rating2**".

| Interaction Steps                                               | K | P | H |
|-----------------------------------------------------------------|---|---|---|
| 1. Type "waterskiing" in search form and "Enter"                |13 | 1 | 2 |
| 2. Click “any Attribute” and restrict property to "rdfs:label"  | 2 | 2 | 1 |
| 3. Click "Values" and select "product"                          | 2 | 2 |   |
| 4. Click "Attributes" and select "vendor"                       | 2 | 2 |   |
| 5. Click "Attributes" and select "country"                      | 2 | 2 |   |
| 6. Click "CN" and go back to offers clicking "?s2"              | 2 | 2 |   |
| 7. Click "Attributes" and select "validTo"                      | 2 | 2 |   |
| 8. Click "Add condition" and select "In"                        | 2 | 2 |   |
| 9. Click the 3 dates after "2008-05-28"                         | 3 | 3 |   |
| 10. Click "Set IN Condition"                                    | 1 | 1 |   |
| 11. Click "Values" and select "reviewFor"                       | 2 | 2 |   |
| Total KLM Operations                                            |33 |21 | 3 |
| Time                                                            |   30.9    |

**Task 9**. [Give me recent reviews in English for a specific product](/Benchmark/9.md)
> "For the product **waterskiing sharpness horseshoes** list the **20** more recent **reviews** in **English**".

Virtuoso does not provide a mechanism to filter literals by language.

**Task 10**. [Get information about a reviewer](/Benchmark/10.md)
> "Get all available information about the author of **Review5481**".

| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
| 1. Click "Describe" for review                               |  1 |  1 |    |
| 2. Click "reviewer" value "Stansie-Klenja"                   |  1 |  1 |    |
| Total Operators                                              |  2 |  2 |    |
| Time                                                         |     2.6      |

**Task 11**. [Get offers for a given product which fulfill specific requirements](/Benchmark/11.md)
> "Look for the **cheapest** and still **valid** by **2008-06-15** **offer** for the product **waterskiing sharpness horseshoes** by a **US vendor** that is able to **deliver** within **3 days**".

| Interaction Steps                                               | K | P | H |
|-----------------------------------------------------------------|---|---|---|
| 1. Type "waterskiing" in search form and "Enter"                |13 | 1 | 2 |
| 2. Click "any Attribute" and restrict property to "rdfs:label"  | 2 | 2 | 1 |
| 3. Click "Values" and select "product"                          | 2 | 2 |   |
| 4. Click "Attributes" and select "vendor"                       | 2 | 2 |   |
| 5. Click "Attributes" and select "country"                      | 2 | 2 |   |
| 6. Click "US" and go back to offers clicking "?s2"              | 2 | 2 |   |
| 7. Click "Attributes" and select "validTo"                      | 2 | 2 |   |
| 8. Click "Add condition" and select "In"                        | 2 | 2 |   |
| 9. Click the 3 dates after "2008-06-15"                         | 3 | 3 |   |
| 10. Click "Set IN Condition" and back to offers "?s2"           | 1 | 1 |   |
| 11. Click "Attributes" and select "deliveryDays"                | 2 | 2 |   |
| 12. Click “Add condition: None” and select “<”                  | 2 | 2 |   |
| 13. Type “3” and click “Set Condition”                          | 5 | 2 | 2 |
| 14. Go back to offers clicking "?s2"                            | 1 | 1 |   |
| Total KLM Operations                                            |41 |26 | 5 |
| Time                                                            |   38.8    |

**Task 12**. [Export the chosen offer into another information system which uses a different schema](/Benchmark/12.md)
> "Save in the local computer the information about the vendor for **Offer3499**, this is **half** the task. To **complete** it, restrict the output to just label, homepage and country and **map** them to schema.org terms name, url and nationality".

Currently, Virtuoso Facet can just export the data, but not map it using a different schema. Consequently, half of the task can be completed and the Capacity measure is 50%.

| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
| 1. Click the desired output format from the page footer      |  1 |  1 |    |
| Time                                                         |      1.3     |
