# BESDUI Results for Rhizomer

This document reports the results for the BESDUI benchmark for the [Rhizomer](http://rhizomik.net/rhizomer/) tool, a semantic data exploration and visualization tool. Rhizomer automatically generates, after analyzing the semantic dataset, some user interface components to explore it. First, they facilitate gaining an overview of the dataset structure, concretely menus, TreeMaps, site maps and site indexes. Then, zooming and filtering into details through facets and the ability to pivot among sets of interrelated resources.

## Summary

|RHIZOMER|Capability|K (0.2s)|P (1.1s)|H (0.4s)|Operator Count|Time |
|--------|--------|--------|--------|--------|--------------|-----|
|Task 1  |0%      |        |        |        |              |     |
|Task 2  |100%    |10      |8       |3       |21            |12.0 |
|Task 3  |100%    |8       |2       |3       |13            |5.0  |
|Task 4  |0%      |        |        |        |              |     |
|Task 5  |0%      |        |        |        |              |     |
|Task 6  |100%    |38      |36      |3       |77            |48.4 |
|Task 7  |100%    |5       |1       |3       |9             |3.3  |
|Task 8  |100%    |24      |13      |3       |40            |20.3 |
|Task 9  |0%      |        |        |        |              |     |
|Task 10 |100%    |2       |2       |        |4             |2.6  |
|Task 11 |100%    |24      |14      |3       |41            |21.4 |
|Task 12 |0%      |        |        |        |              |     |
|SUM     |        |109     |76      |18      |203           |112.6|
|AVERAGE |58%     |15.6    |10.9    |2.6     |29            |16.1 |

## Results per Task

**Task 1**. [Find products for a given set of features combined](/Benchmark/1.md)
> "Look for products of type **sheeny** with product features **stroboscopes** and **gadgeteers**, and a **productPropertyNumeric1** greater than **450**".

This task cannot be performed because Rhizomer does not provide a way to define that all the selected values of a facet, in this case the productFeature facet, should be present at the same time for a given resource.

**Task 2**. [Find products for a given set of alternative features](/Benchmark/2.md)
> "List products of type **sheeny** with product features **stroboscopes** OR **gadgeteers**, and a **productPropertyNumeric1** greater than **450**".

| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
| 1. Click menu “ProductType” and then “Sheeny” submenu        |  2 |  2 |  1 |
| 2. Click “Show values” for facet “Product Feature”           |  1 |  1 |    |
| 3. Click facet value “stroboscopes”                          |  1 |  1 |    |
| 4. Type in input “Search Product Feature” “gad...”           |  4 |  1 |  1 |
| 5. Select “gadgeteers” from autocomplete                     |  1 |  1 |  1 |
| 6. Set left side of property "Numeric1" slider to "450"      |  1 |  2 |    |
| Total KLM Operations                                         | 10 |  8 |  3 |
| Time                                                         |      12      |

**Task 3**. [Retrieve basic information about a specific product for display purposes](/Benchmark/3.md)
> "Get details about product **boozed**".

From the entry page, type the product name in the "Quick search..." input box and select the requested product name.

| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
| 1. Click in search form and type "booz"                      |  5 |  1 |  2 |
| 2. Click "boozed" in autocomplete                            |  1 |  1 |  1 |
| Time                                                         |      4.6     |

**Task 4**. [Find products having some specific features and not having one feature](/Benchmark/4.md)
> "Look for products of type **sheeny** with product features **stroboscopes** but **NOT gadgeteers**, and **productPropertyNumeric1** value greater than **300** and **productPropertyNumeric3** smaller than **400**".

This task is not currently possible using Rhizomer because it does not provide a way to negate facet values.

**Task 5**. [Find products matching two different sets of features](/Benchmark/5.md)
> "Look for products of type **sheeny** with product features **stroboscopes** and **gadgeteers** and a **productPropertyNumeric1** value greater than **300** plus those of the same product type with product features **stroboscopes** and **rotifers** and a **productPropertyNumeric2** greater than **400**".

It cannot be performed using Rhizomer because it currently does not support AND for facet value neither the union of different query patterns.

**Task 6**. [Find products that are similar to a given product](/Benchmark/6.md)
> "Look for products similar to **boozed**, with at least one shared feature, and a **productPropertyNumeric1** value between **427 and 627** (100 more or less than its value for boozed, 527) and a **productPropertyNumeric2** value between **545 and 945** (200 more or less than its value for boozed, 745)".

The user can look for a specific product. As a result, the corresponding faceted view for it is generated and a query where the restriction is that the product is the one selected. The faceted view can be then used to select all the product features of the selected product. The user can also see the values for the numeric properties and manually set the ranges in the corresponding facet sliders. Finally, the user can remove the restriction for the specific product while keeping the rest of restrictions to retrieve similar products.

| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
| 1. Point search form, type "boozed" and click in autocomplete|  8 |  2 |  3 |
| 2. 5 Clicks to expand all Product Feature values             |  5 |  5 |    |
| 3. 20 Clicks to select all features for the current product  | 20 | 20 |    |
| 4. Click to remove restriction for current product           |  1 |  1 |    |
| 5. Set sliders for numeric properties 1 and 2 ranges         |  4 |  8 |    |
| Total Operators                                              | 38 | 36 |  3 |
| Time                                                         |    12.0      |

**Task 7**. [Find products having a name that contains some text](/Benchmark/7.md)
> "Search products whose name contains **ales**".

The user can directly use the “Quick search...” input box at the top, type “ales” and a list of entities whose label contains “ales” is shown, from where the user can select the one he is interested in.

| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
| 1. Type "ales" in search form, results in autocomplete       |  5 |  1 |  3 |
| Time                                                         |     3.3      |

Alternative: click “Product” in the menu and then use the “label” facet to search for label values containing water.

Alternative: not supported yet, “Quick search...” in addition to autocomplete user input also performs free text search and shows results in a view faceted by entity type.

**Task 8**. [Retrieve in-depth information about a specific product including offers and reviews](/Benchmark/8.md)
> "For the product **waterskiing sharpness horseshoes** list details for all its **offers** by Chinese vendors and still valid by **2008-05-28** plus details for all **reviews** for this product having either **rating1 or rating2**".

| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
| 1. Type "waterskiing" in search form and click autocomplete  | 13 |  2 |  3 |
| 2. Click “See related Offers” in the product description     |  1 |  1 |    |
| 3. In the “Vendor” facet click “Filter Vendor”               |  1 |  1 |    |
| 4. Click “Show values” for “Country” and check “CN”          |  2 |  2 |    |
| 5. Go back to offers by clicking “Offer” in breadcrumbs      |  1 |  1 |    |
| 6. Click “Show values” in “Valid to” facet                   |  1 |  1 |    |
| 7. Check 3 dates after “2008-05-28”                          |  3 |  3 |    |
| 8. Pivot to related products using "Filter Product"          |  1 |  1 |    |
| 9. Pivot to related reviews using "Filter Review"            |  1 |  1 |    |
| Total Operators                                              | 24 | 13 |  3 |
| Time                                                         |     20.3     |

**Task 9**. [Give me recent reviews in English for a specific product](/Benchmark/9.md)
> "For the product **waterskiing sharpness horseshoes** list the **20** more recent **reviews** in **English**".

Rhizomer does not currently provide a mechanism to filter literals by language.

**Task 10**. [Get information about a reviewer](/Benchmark/10.md)
> "Get all available information about the author of **Review5481**".

| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
| 1. Click "Person"                                            |  1 |  1 |    |
| 2. Type "5481" in "Is Reviewer of Review" facet input        |  5 |  1 |  1 |
| 3. Select autocompleted option "Review5481" pressing Enter   |  1 |    |    |
| 4. Click displayed "Reviewer268" for details                 |  1 |  1 |  1 |
| Total Operators                                              |  8 |  3 |  2 |
| Time                                                         |     5.7      |

**Task 11**. [Get offers for a given product which fulfill specific requirements](/Benchmark/11.md)
> "Look for the **cheapest** and still **valid** by **2008-06-15** **offer** for the product **waterskiing sharpness horseshoes** by a **US vendor** that is able to **deliver** within **3 days**".

| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
| 1. Type "waterskiing" in search form and click autocomplete  | 13 |  2 |  3 |
| 2. Click “See related Offers” in the product description     |  1 |  1 |    |
| 3. In the “Vendor” facet click “Filter Vendor”               |  1 |  1 |    |
| 4. Click “Show values” for “Country” and check “US”          |  2 |  2 |    |
| 5. Go back to offers by clicking “Offer” in breadcrumbs      |  1 |  1 |    |
| 7. Click "Valid to" values and 3 dates after “2008-06-15”    |  3 |  3 |    |
| 6. Slide “Delivery days” to 3 or less days                   |  1 |  2 |    |
| 8. Select "price" in "Sort by" selector                      |  2 |  2 |    |
| Total Operators                                              | 24 | 14 |  3 |
| Time                                                         |     21.4     |

**Task 12**. [Export the chosen offer into another information system which uses a different schema](/Benchmark/12.md)
> "Save in the local computer the information about the vendor for **Offer3499**, this is **half** the task. To **complete** it, restrict the output to just label, homepage and country and **map** them to schema.org terms name, url and nationality".

Currently, Rhizomer does not provide a way to map data and export it using a different schema.
