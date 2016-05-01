# SDEBM Results for Rhizomer

This document reports the results for the SDEBM benchmark for the [Rhizomer](http://rhizomik.net/rhizomer/) tool, a semantic data exploration and visualization tool. Rhizomer automatically generates, after analyzing the semantic dataset, some user interface components to explore it. First, they facilitate gaining an overview of the dataset structure, concretely menus, TreeMaps, site maps and site indexes. Then, zooming and filtering into details through facets and the ability to pivot among sets of interrelated resources.

## Summary

|Benchmark|Task Success|Interaction Steps|Speed|
|---------|------------|-----------------|-----|
|1        | 0%         |                 |     |
|2        | 100%       | 10K, 8P, 3H     | 12.0|
|3        | 100%       | 1K, 1P          |  1.3|
|4        | 0%         |                 |     |
|5        | 0%         |                 |     |
|6        | 100%       | 25K/1T/4S       |
|7        | 100%       | 1K/1T           |
|8        | 100%       | 12K/1T          |
|9        | 0%         |                 |     |
|10       | 100%       | 3K              |
|11       | 100%       | 10K/1T/1S       |
|12       | 100%       | 1K              |
|13       | 0%         |                 |     |

## Results per Task

**Task 1**. [Find products for a given set of features combined](Benchmarks/1.md)

This task cannot be performed because Rhizomer does not provide a way to define that all the selected values of a facet, in this case the productFeature facet, should be present at the same time for a given resource.

**Task 2**. [Find products for a given set of alternative features](Benchmarks/2.md)

The interaction steps and KLM Operators are:

| Interaction Steps                                               | K | P | H |
|-----------------------------------------------------------------|---|---|---|
| 1. Click menu “ProductType” and then “Sheeny” submenu           | 2 | 2 | 1 |
| 2. Click “Show values” for facet “Product Feature”              | 1 | 1 |   |
| 3. Click facet value “stroboscopes”                             | 1 | 1 |   |
| 4. Type in input “Search Product Feature” “gad...”              | 4 | 1 | 1 |
| 5. Select “gadgeteers” from autocomplete                        | 1 | 1 | 1 |
| 6. Set left side of “Product Property Numeric1”slider to “450”  | 1 | 2 |   |
| Total KLM Operations                                            | 10| 8 | 3 |
| Speed                                                           |    12     |

**Task 3**. [Retrieve basic information about a specific product for display purposes](Benchmarks/3.md)

From Query 2 Rhizomer shows the list of selected products and a short description for each one (label, types and comment). Click any product to retrieve all the metadata for the selected product.

The interaction steps and KLM Operators are:

| Interaction Steps                                               | K | P | H |
|-----------------------------------------------------------------|---|---|---|
| 1. Click product label "boozed"                                 | 1 | 1 |   |
| Speed                                                           |    1.3    |

**Task 4**. [Find products having some specific features and not having one feature](Benchmarks/4.md)

This task is not currently possible using Rhizomer because it does not provide a way to negate facet values.

When this feature is implemented, these will be the interaction steps:

1. Over Top Menu “ProductType” and click “Sheeny” from submenu.
1. Click “Show values” for facet “Product Feature”.
1. Check facet value “stroboscopes”.
1. Type in the “Search Product Feature” input box “gadget”.
1. Click “gadgeteers” from the input box autocomplete recommendations.
1. **TODO** Mark that the “gadgeteers” value should NOT be present
1. Set the left side of the slider for facet “Product Property Numeric1” to “300”.
1. Set the right side of the slider for facet “Product Property Numeric3” to “400”.

**Task 5**. [Find products matching two different sets of features](Benchmarks/5.md)

It cannot be performed using Rhizomer because it currently does not support AND for facet value neither the union of different query patterns.

**Task 6**. [Find products that are similar to a given product](Benchmarks/6.md)

The user can look for a specific product. As a result, the corresponding faceted view for it is generated and a query where the restriction is that the product is the one selected. The faceted view can be then used to select all the product features of the selected product. The user can also see the values for the numeric properties and manually set the ranges in the corresponding facet sliders. Finally, the user can remove the restriction for the specific product while keeping the rest of restrictions to retrieve similar products.

1. Type "boozed" in search form
1. 4 Clicks to expand all feature values
1. 20 Clicks to select all features for the current product
1. Click to remove restriction for current product
1. 4 Slides to set ranges for numeric properties 1 and 2

**Task 7**. [Find products having a name that contains some text](Benchmarks/7.md)

The user can directly use the “Quick search...” input box at the top, type “water” and a list of entities whose label contains “water” is shown, from where the user can select the one he is interested in.

Alternative: click “Product” in the menu and then use the “label” facet to search for label values containing water.

Alternative: not supported yet, “Quick search...” in addition to autocomplete user input also performs free text search and shows results in a view faceted by entity type.

**Task 8**. [Retrieve in-depth information about a specific product including offers and reviews](Benchmarks/8.md)

Interaction steps:

1. The user types “waterski...” in the search field and selects the product “waterskiing sharpness horseshoes”.
1. Click “See related Offers” at the bottom of the product description. Now showing faceted view for the product offers.
1. Click “Vendor” in right column “Related to...”. (Or in the “Vendor” facet click “Filter Vendor”). The faceted view for product offer vendors is shown.
1. Click “Show values” for the “Country” facet.
1. Check “CN” for China. Details for the two chinese vendors having offers for the product are shown.
1. Click “Offer” in the breadcrumbs (or “Offer” in right column “Back to...” or “Filter Offer” in the “Is Vendor of Offer” facet). Details for the five offers by Chinese vendors are shown.
1. Click “Show values” for the “Valid to” facet. There is no range selector for date facets, the user has to check each relevant date manually.
1. Check “2008-06-13”, the first date after “2008-05-28”.
1. Check “2008-07-10”, the second one.
1. Check “2008-08-04”, the last one. The details for the 3 selected offers are shown.
1. Click “Product” in right column “Related to...”. (Or “Filter Product” in the “Product” facet). The details for the selected product and its faceted view are shown.
1. Click “Review” in right column “Related to...”. (Or “Filter Review” in the “Is Review For of Review” facet). Details for five reviews for the selected product are shown, including rating1, rating2 or both when available.

**Task 9**. [Give me recent reviews in English for a specific product](Benchmarks/9.md)

Rhizomer does not currently provide a mechanism to filter literals by language.

If this feature is implemented, the interaction steps will be:

1. The user types “waterski...” in the search field and selects the product “waterskiing sharpness horseshoes”.
1. Click “Review” in right column “Related to...”. (Or “Filter Review” in the “Is Review For of Review” facet).  
1. Click “Sort by” and from the dropdown select “Review date”.
1. Click “DESC” to sort the reviews by descending review date. The 10 most recent reviews are shown.
1. To see the next 10 click “Next”. The 10 next more recent reviews are shown.

**Task 10**. [Get information about a reviewer](Benchmarks/10.md)

Interaction steps:

1. Click menu option "Reviews".
1. Click "Review1".
1. Click the reviewer link, “Reviewer1”. All the data for that reviewer is shown.

**Task 11**. [Get offers for a given product which fulfill specific requirements](Benchmarks/11.md)

Interaction steps:

1. Quick search for “waterskiing” and selected the product “waterskiing sharpness horseshoes”.
1. Click “See related Offers” at the bottom of the product description. Now showing faceted view for the product offers.
1. Click “Vendor” in right column “Related to...”. (Or in the “Vendor” facet click “Filter Vendor”). The faceted view for product offer vendors is shown.
1. Click “Show values” for the “Country” facet.
1. Check “US” for the United State. Details for the four US vendors having offers for the product are shown.
1. Click “Offer” in the breadcrumbs (or “Offer” in right column “Back to...” or “Filter Offer” in the “Is Vendor of Offer” facet). Details for the seven offers by US vendors are shown.
1. For the “Delivery days” facet, slide the upper bound of the range down to 3 days. The set of selected offers is reduced to three.
1. Click “Show values” for the “Valid to” facet. There is no range selector for date facets, the user has to check all dates greater than “2008-06-01” date manually.
1. **TODO** Click “Sort by” and from the dropdown select “Price”.
1. Click “DESC” to sort the selected offers by descending price. The cheapest offer from the selected ones is shown first, “Offer3499”.

**Task 12**. [Export the chosen offer into another information system which uses a different schema](Benchmarks/12.md)

Currently, Rhizomer does not provide a way to map data and export it using a different schema.
