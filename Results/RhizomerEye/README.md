# BESDUI Results for RhizomerEye

This document reports the results for the BESDUI benchmark for the [RhizomerEye](https://github.com/rhizomik/rhizomerEye) tool, a semantic data exploration and visualization frontend build on top of the [RhizomerAPI](https://github.com/rhizomik/rhizomerAPI) backend. RhizomerEye automatically generates, after analyzing the semantic dataset, some user interface components to explore it. First, they facilitate gaining an overview of the dataset structure through a network overview or wordmap. Then, zooming and filtering into details through a faceted view.

## Summary

| RhizomerEye | Capability | K (0.2s) | P (1.1s) | H (0.4s) | Operator Count | Time | Task Efficiency |
|-------------|------------|----------|----------|----------|----------------|------|-----------------|
| Task 1      | 100%       | 10       | 8        | 3        | 21             | 12   | 5.0             |
| Task 2      | 100%       | 11       | 9        | 3        | 23             | 13.3 | 4.5             |
| Task 3      | 100%       | 10       | 3        | 3        | 16             | 6.5  | 9.2             |
| Task 4      | 100%       | 13       | 12       | 3        | 28             | 17   | 3.5             |
| Task 5      |            |          |          |          |                |      |                 |
| Task 6      | 100%       | 25       | 22       | 3        | 50             | 30.4 | 2.0             |
| Task 7      | 100%       | 7        | 3        | 2        | 12             | 5.5  | 10.9            |
| Task 8      |            |          |          |          |                |      |                 |
| Task 9      |            |          |          |          |                |      |                 |
| Task 10     | 100%       | 15       | 4        | 2        | 21             | 8.2  | 7.3             |
| Task 11     |            |          |          |          |                |      |                 |
| Task 12     |            |          |          |          |                |      |                 |
| SUM         | 700%       | 91       | 61       | 19       | 171            | 92.9 | 42.6            |
| AVERAGE     | 58%        | 13.0     | 8.7      | 2.7      | 24.4           | 13.3 | 2.6             |

## Results per Task

**Task 1**. [Find products for a given set of features combined](/Benchmark/1.md)
> "Look for products of type **sheeny** with product features **stroboscopes** and **gadgeteers**, and a **productPropertyNumeric1** greater than **450**".

| Interaction Steps                                          | K   | P   | H   |
|------------------------------------------------------------|-----|-----|-----|
| 1. On the network overview, click on “sheeny” green bubble | 1   | 1   | 1   |
| 2. Click "+" for facet “productFeature”                    | 1   | 1   |     |
| 3. Click facet value “stroboscopes”                        | 1   | 1   |     |
| 4. Type in input “Search facet values” “gad...”            | 4   | 1   | 1   |
| 5. Select “gadgeteers” from autocomplete                   | 1   | 1   | 1   |
| 6. Expand facet "productPropertyNumeric1" clicking "+"     | 1   | 1   |     |
| 6. Set facet's slider left end to aprox. "450"             | 1   | 2   |     |
| Total KLM Operations                                       | 10  | 8   | 3   |
| Time                                                       | 12  |

**Task 2**. [Find products for a given set of alternative features](/Benchmark/2.md)
> "List products of type **sheeny** with product features **stroboscopes** OR **gadgeteers**, and a **productPropertyNumeric1** greater than **450**".

| Interaction Steps                                          | K    | P   | H   |
|------------------------------------------------------------|------|-----|-----|
| 1. On the network overview, click on “sheeny” green bubble | 1    | 1   | 1   |
| 2. Click "+" for facet “productFeature”                    | 1    | 1   |     |
| 3. Click facet value “stroboscopes”                        | 1    | 1   |     |
| 4. Type in input “Search facet values” “gad...”            | 4    | 1   | 1   |
| 5. Select “gadgeteers” from autocomplete                   | 1    | 1   | 1   |
| 6. Switch facet operator from AND to OR mode               | 1    | 1   |     |
| 7. Expand facet "productPropertyNumeric1" clicking "+"     | 1    | 1   |     |
| 8. Set facet's slider left end to aprox. "450"             | 1    | 2   |     |
| Total KLM Operations                                       | 11   | 9   | 3   |
| Time                                                       | 13.3 |

**Task 3**. [Retrieve basic information about a specific product for display purposes](/Benchmark/3.md)
> "Get details about product **boozed**".

| Interaction Steps                                             | K   | P   | H   |
|---------------------------------------------------------------|-----|-----|-----|
| 1. Type "boozed" in "Search all..." input and then RETURN key | 8   | 1   | 2   |
| 2. Click "Product" in "Type" facet                            | 1   | 1   | 1   |
| 3. Click result "boozed" from right column products list      | 1   | 1   |     |
| Total KLM Operations                                          | 10  | 3   | 3   |
| Time                                                          | 6.5 |

**Task 4**. [Find products having some specific features and not having one feature](/Benchmark/4.md)
> "Look for products of type **sheeny** with product features **stroboscopes** but **NOT gadgeteers**, and **productPropertyNumeric1** value greater than **300** and **productPropertyNumeric3** smaller than **400**".

| Interaction Steps                                                  | K    | P   | H   |
|--------------------------------------------------------------------|------|-----|-----|
| 1. On the network overview, click on “sheeny” green bubble         | 1    | 1   | 1   |
| 2. Click "+" for facet “productFeature”                            | 1    | 1   |     |
| 3. Click facet value “stroboscopes”                                | 1    | 1   |     |
| 4. Type in input “Search facet values” “gad...”                    | 4    | 1   | 1   |
| 5. Select “gadgeteers” from autocomplete                           | 1    | 1   | 1   |
| 6. Click selected value “gadgeteers” marked in yellow to negate it | 1    | 1   |     |
| 7. Expand facet "productPropertyNumeric1" clicking "+"             | 1    | 1   |     |
| 8. Set facet's slider left end to aprox. "300"                     | 1    | 2   |     |
| 9. Expand facet "productPropertyNumeric3" clicking "+"             | 1    | 1   |     |
| 10. Set facet's slider right end to aprox. "400"                   | 1    | 2   |     |
| Total KLM Operations                                               | 13   | 12  | 3   |
| Time                                                               | 13.3 |

**Task 5**. [Find products matching two different sets of features](/Benchmark/5.md)
> "Look for products of type **sheeny** with product features **stroboscopes** and **gadgeteers** and a **productPropertyNumeric1** value greater than **300** plus those of the same product type with product features **stroboscopes** and **rotifers** and a **productPropertyNumeric2** greater than **400**".

This task cannot be performed using RhizomerEye because it does not support modelling the union of different query patterns.

**Task 6**. [Find products that are similar to a given product](/Benchmark/6.md)
> "Look for products similar to **boozed**, with at least one shared feature, and a **productPropertyNumeric1** value between **427 and 627** (100 more or less than its value for boozed, 527) and a **productPropertyNumeric2** value between **545 and 945** (200 more or less than its value for boozed, 745)".

The user can look for a specific product. As a result, the corresponding faceted view for it is generated and a query where the restriction is that the product is the one selected. The faceted view can be then used to select all the product features of the selected product. The user can also see the values for the numeric properties and manually set the ranges in the corresponding facet sliders. Finally, the user can remove the restriction for the specific product while keeping the rest of restrictions to retrieve similar products.

| Interaction Steps                                                              | K    | P   | H   |
|--------------------------------------------------------------------------------|------|-----|-----|
| 1. On the network overview, click on “Product” blue bubble                     | 1    | 1   | 1   |
| 2. Expand facet "label" by clicking "+"                                        | 1    | 1   |     |
| 3. Type "booz" in facets's "Search facets value" input and RETURN key          | 6    | 1   | 1   |
| 4. Expand facet "productFeature" by clicking "+"                               | 1    | 1   | 1   |
| 5. Select all 11 values for "productFeature" facet                             | 11   | 11  |     |
| 6. Expand facets "productPropertyNumeric1" and "productPropertyNumeric2"       | 1    | 1   |     |
| 7. Notice that values for "boozed" are "527" and "745"                         |      |     |     |
| 8. Click value "boozed" in facet "label" to negate it                          | 1    | 1   |     |
| 9. Swith operator mode for facet "productFeature" from AND to OR               | 1    | 1   |     |
| 10. Set facet "productPropertyNumeric1" slider to range aprox. "427" and "627" | 1    | 2   |     |
| 10. Set facet "productPropertyNumeric2" slider to range aprox. "545" and "945" | 1    | 2   |     |
| Total KLM Operations                                                           | 25   | 22  | 3   |
| Time                                                                           | 30.4 |

**Task 7**. [Find products having a name that contains some text](/Benchmark/7.md)
> "Search products whose name contains **ales**".

| Interaction Steps                                          | K   | P   | H   |
|------------------------------------------------------------|-----|-----|-----|
| 1. On the network overview, click on “Product” blue bubble | 1   | 1   | 1   |
| 2. Expand facet "label" by clicking "+"                    | 1   | 1   |     |
| 3. Type "ales" in facets's "Search facets value" input     | 5   | 1   | 1   |
| 4. The results appear as autocomplete recommendations      |     |     |     |
| Total KLM Operations                                       | 7   | 3   | 2   |
| Time                                                       | 5.5 |

**Task 8**. [Retrieve in-depth information about a specific product including offers and reviews](/Benchmark/8.md)
> "For the product **waterskiing sharpness horseshoes** list details for all its **offers** by Chinese vendors and still valid by **2008-05-28** plus details for all **reviews** for this product having either **rating1 or rating2**".

This task requires defining facet restrictions for different related classes and it is not yet possible to perform it using RhizomerEye. The development of the pivoting support is currently future work.

**Task 9**. [Give me recent reviews in English for a specific product](/Benchmark/9.md)
> "For the product **waterskiing sharpness horseshoes** list the **20** more recent **reviews** in **English**".

RhizomerEye does not currently provide a mechanism to filter literals by language.

**Task 10**. [Get information about a reviewer](/Benchmark/10.md)
> "Get all available information about the author of **Review5481**".

| Interaction Steps                                                      | K   | P   | H   |
|------------------------------------------------------------------------|-----|-----|-----|
| 1. On the network overview, click on “Review” blue bubble              | 1   | 1   | 1   |
| 2. Type "Review5481" in "Search all facet values" input and RETURN key | 12  | 1   | 1   |
| 4. Click displayed "Review5481" for details                            | 1   | 1   |     |
| 4. Click reviewer link "Reviewer268"                                   | 1   | 1   |     |
| Total Operators                                                        | 15  | 4   | 2   |
| Time                                                                   | 8.2 |

**Task 11**. [Get offers for a given product which fulfill specific requirements](/Benchmark/11.md)
> "Look for the **cheapest** and still **valid** by **2008-06-15** **offer** for the product **waterskiing sharpness horseshoes** by a **US vendor** that is able to **deliver** within **3 days**".

This task requires defining facet restrictions for different related classes and it is not yet possible to perform it using RhizomerEye. The development of the pivoting support is currently future work.


**Task 12**. [Export the chosen offer into another information system which uses a different schema](/Benchmark/12.md)
> "Save in the local computer the information about the vendor for **Offer3499**, this is **half** the task. To **complete** it, restrict the output to just label, homepage and country and **map** them to schema.org terms name, url and nationality".

Currently, Rhizomer does not provide a way to map data and export it using a different schema.
