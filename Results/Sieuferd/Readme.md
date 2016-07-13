# SDEBM Results for SIEUFERD

This document reports the results for the SDEBM benchmark for the [SIEUFERD](http://people.csail.mit.edu/ebakke/sieuferd) tool.

## Summary

|SIEUFERD|Capacity|K (0.2s)|P (1.1s)|H (0.4s)|Operator Count|Speed|
|--------|--------|--------|--------|--------|--------------|-----|
|Task 1|100%|47|19|1|67|30.70|
|Task 2|100%|38|19|1|58|28.90|
|Task 3|100%|23|3|1|27|8.30|
|Task 4|100%|62|32|1|95|48.00|
|Task 5|100%|92|32|4|128|55.20|
|Task 6|100%|87|40|14|141|67.00|
|Task 7|100%|15|3|1|19|6.70|
|Task 8|100%|60|24|4|88|40.00|
|Task 9|100%|27|15|2|44|22.70|
|Task 10|100%|24|12|1|37|18.40|
|Task 11|100%|61|24|3|88|39.80|
|Task 12|50%|48|14|2|64|25.80|
|SUM|11.5|584|237|35|856|391.50|
|AVERAGE|96%|48.7|19.75|2.92|71.3|32.63|

## Results per Task

In the following interaction sequences, it is assumed that foreign key relationships have been declared at the database level, as part of the schema definition. SIEUFERD will detect such relationships and make relevant joins available in the field selector, allowing the user to avoid the manual join dialog most of the time.

**Task 1**. [Find products for a given set of features combined](/Benchmark/1.md)
> "Look for products of type **sheeny** with product features **stroboscopes** and **gadgeteers**, and a **productPropertyNumeric1** greater than **450**".

| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
|1. Create and open a perspective from the "product" table|4|3|0|
|2. Make the "propertyNum1", "productfeatureproduct.productfeature.label", and "producttypeproduct.producttype.label" fields visible|9|7|0|
|3. Filter to show only products for which "producttypeproduct.producttype.label" is "sheeny"|4|3|0|
|4. Open the filter toolbox on the "productfeature.label" field|2|2|0|
|5. Click "stroboscopes" and "gadgeteers" and close the filter box|3|2|0|
|6. Insert a calculated field next to "product.label"|2|2|0|
|7. Key the cursor to the calculated column and type the formula "=[propertyNum1]>450 and count([productfeature\label])=2" (field references inserted by arrow keypresses)|17|0|1|
|8. Filter to show only products for which the formula is "true" (use keyboard shortcut since hand is already on keyboard)|6|0|0|
|Total Operators|47|19|1|
|Speed|30.7|||

In the future, we expect to implement range filters so that conditions such as "=[propertyNum1]>450" can be expressed without the use of a formula.

**Task 2**. [Find products for a given set of alternative features](/Benchmark/2.md)
> "List products of type **sheeny** with product features **stroboscopes** OR **gadgeteers**, and a **productPropertyNumeric1** greater than **450**".

| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
|1. Create and open a perspective from the "product" table|4|3|0|
|2. Make the "propertyNum1", "productfeatureproduct.productfeature.label", and "producttypeproduct.producttype.label" fields visible|9|7|0|
|3. Filter to show only products for which "producttypeproduct.producttype.label" is "sheeny"|4|3|0|
|4. Open the filter toolbox on the "productfeature.label" field|2|2|0|
|5. Click "stroboscopes" and "gadgeteers" and close the filter box|3|2|0|
|6. Insert a calculated field next to "product.label"|2|2|0|
|7. Key the cursor to the calculated column and type the formula "=[propertyNum1]>450" (field reference inserted by single arrow keypress)|8|0|1|
|8. Filter to show only products for which the formula is "true" (use keyboard shortcut since hand is already on keyboard)|6|0|0|
|Total Operators|38|19|1|
|Speed|28.9|||

**Task 3**. [Retrieve basic information about a specific product for display purposes](/Benchmark/3.md)
> "Get details about product **boozed**".

| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
|1. Create and open a perspective from the "product" table|4|3|0|
|2. Make all the fields visible (use keyboard shortcuts)|8|0|1|
|3. Open the filter box (keyboard shortcut)|1|0|0|
|4. Type "boozed", down, down, space, enter|10|0|0|
|Total Operators|23|3|1|
|Speed|8.3|||

**Task 4**. [Find products having some specific features and not having one feature](/Benchmark/4.md)
> "Look for products of type **sheeny** with product features **stroboscopes** but **NOT gadgeteers**, and **productPropertyNumeric1** value greater than **300** and **productPropertyNumeric3** smaller than **400**".

| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
|1. Create and open a perspective from the "product" table|4|3|0|
|2. Make the "nr", "propertyNum1", "propertyNum3", "productfeatureproduct.productfeature.label", and "producttypeproduct.producttype.label" fields visible|11|9|0|
|3. Filter to show only products for which "producttypeproduct.producttype.label" is "sheeny"|4|3|0|
|4. Do a custom join operation to join in another instance of the productfeatureproduct table|5|5|0|
|5. Make the "productfeatureproduct2.productfeature.label" field visible|4|3|0|
|6. Filter for "stroboscopes" in "productfeatureproduct"|4|3|0|
|7. Filter for "NOT gadgeteers" in "productfeatureproduct2"|5|4|0|
|8. Insert a calculated field next to "product.label"|2|2|0|
|9. Key the cursor to the calculated column and type the formula "=[propertyNum1]>300 and [propertyNum3]<400" (field references inserted by arrow key presses)|17|0|1|
|10. Filter to show only products for which the formula is "true" (use keyboard shortcut since hand is already on keyboard)|6|0|0|
|Total Operators|62|32|1|
|Speed|48.0|||

**Task 5**. [Find products matching two different sets of features](/Benchmark/5.md)
> "Look for products of type **sheeny** with product features **stroboscopes** and **gadgeteers** and a **productPropertyNumeric1** value greater than **300** plus those of the same product type with product features **stroboscopes** and **rotifers** and a **productPropertyNumeric2** greater than **400**".

| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
|11. Create and open a perspective from the "product" table|4|3|0|
|12. Make the "nr", "propertyNum1", "propertyNum3", "productfeatureproduct.productfeature.label", and "producttypeproduct.producttype.label" fields visible|11|9|0|
|13. Filter to show only products for which "producttypeproduct.producttype.label" is "sheeny"|4|3|0|
|14. Do a custom join operation to join in another instance of the productfeatureproduct table|5|5|0|
|15. Make the "productfeatureproduct2.productfeature.label" field visible|4|3|0|
|16. Filter for "stroboscopes" in "productfeatureproduct"|4|3|0|
|17. Insert a calculated field next to "product.label"|2|2|0|
|18. Key the cursor to the calculated column and type the formula "=[pfp2.pf.label]='gadgeteers' and [propertyNum1]>300 or [pfp2.pf.label]='rotifiers' and [propertyNum2]>400" (field references inserted by mouse clicks)|52|4|4|
|19. Filter to show only products for which the formula is "true" (use keyboard shortcut since hand is already on keyboard)|6|0|0|
|Total Operators|92|32|4|
|Speed|55.2|||

**Task 6**. [Find products that are similar to a given product](/Benchmark/6.md)
> "Look for products similar to **boozed**, with at least one shared feature, and a **productPropertyNumeric1** value between **427 and 627** (100 more or less than its value for boozed, 527) and a **productPropertyNumeric2** value between **545 and 945** (200 more or less than its value for boozed, 745)".

| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
|1. Create and open a perspective from the "product" table|4|3|0|
|2. Make the "propertyNum1", "propertyNum3", and "productfeatureproduct.productFeature" fields visible|7|6|0|
|3. Do a custom join operation to join the existing instance of productfeatureproduct with another instance of productfeatureproduct on the productFeature field|5|5|0|
|4. Make "product2" then "propertyNum1", "propertyNum3", and "label" fields visible under productfeatureproduct2 (the second instance of productfeatureproduct2)|5|4|0|
|5. Filter "product2.label" to only include the product "boozed" (open filter with keyboard shortcut, type "boozed", click result and close filter popup)|9|8|2|
|6. Insert a calculated field next to "product.label"|2|2|0|
|7. Key the cursor to the calculated column and type the formula "=[propertyNum1]<[product2\propertyNum1]+100 and [propertyNum1]>[product2\propertyNum1]-100" (field references inserted by mouse clicks)|22|4|4|
|8. Copy the formula to the clipboard from the formula bar|2|2|2|
|9. Insert another calculated column next the previous one|2|2|0|
|10. Key the cursor to the new calculated column and paste the formula|3|0|1|
|11. Change "propertyNum1" to "propertyNum3" in each place in the formula in the formula bar, and "100" to "200".|20|6|7|
|12. Filter the two formulas to only include values of "true"|12|0|0|
|Total Operators|87|40|14|
|Speed|67.0|||

**Task 7**. [Find products having a name that contains some text](/Benchmark/7.md)
> "Search products whose name contains **ales**".

| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
|1. Create and open a perspective from the "product" table|4|3|0|
|2. Open the filter and type "ales"|5|0|1|
|3. Select all the results (multiple selection via page down + space), then press enter to close the filter popup|6|0|0|
|Total Operators|15|3|1||Speed|6.7|||

**Task 8**. [Retrieve in-depth information about a specific product including offers and reviews](/Benchmark/8.md)
> "For the product **waterskiing sharpness horseshoes** list details for all its **offers** by Chinese vendors and still valid by **2008-05-28** plus details for all **reviews** for this product having either **rating1 or rating2**".

| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
|1. Create and open a perspective from the "product" table|4|3|0|
|2. Open the filter popup and type "wat sha" (assume this makes the right product visible)|8|0|1|
|3. Select the "waterskiing sharpness horseshoes" product and close the filter popup|2|1|1|
|4. Make all the relevant fields visible, including from the "offer" and "review" table instances|16|15|0|
|5. Filter "product.offer.vendor.country" to China only.|4|3|0|
|6. Insert a calculated column next to "offer.validto"|2|2|0|
|7. Key the cursor to the new calculated column and enter the formula "=[validTo]>{2008-05-28}"|16|0|1|
|8. Filter to show only products for which the formula is "true" (use keyboard shortcut since hand is already on keyboard)|6|0|0|
|9. Deactivate "Hide Parent if Empty" on the "offers" table instance (to avoid hiding the product if there are no offers satisfying the constraint--needed if we want to be technically equivalent to the left join in the SQL query example)|2|0|1|
|Total Operators|60|24|4|
|Speed|40.0|||

**Task 9**. [Give me recent reviews in English for a specific product](/Benchmark/9.md)
> "For the product **waterskiing sharpness horseshoes** list the **20** more recent **reviews** in **English**".

| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
|1. Create and open a perspective from the "product" table|4|3|0|
|2. Open the filter popup and type "wat sha" (assume this makes the right product visible)|8|0|1|
|3. Select the "waterskiing sharpness horseshoes" product and close the filter popup|2|1|1|
|4. Make the "review" table instance visible and its relevant fields.|7|6|0|
|5. Filter "review.language" on "en"|4|3|0|
|6. Sort descending on "reviewDate" (there is no LIMIT to be specified; the user can simply look at the 20 topmost rows. Explicit limits could be supported by allowing the row_number() window aggregate function in formulas)|2|2|0|
|Total Operators|27|15|2||Speed|22.7|||

**Task 10**. [Get information about a reviewer](/Benchmark/10.md)
> "Get all available information about the author of **Review5481**".

| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
|1. Create and open a perspective from the "review" table|4|3|0|
|2. Show the "review.nr" and "review.person" fields, and all fields under "review.person"|10|9|0|
|3. Filter "nr" to show only Review5481 (use keyboard shortcuts)|10|0|1|
|Total Operators|24|12|1||Speed|18.4|||

**Task 11**. [Get offers for a given product which fulfill specific requirements](/Benchmark/11.md)
> "Look for the **cheapest** and still **valid** by **2008-06-15** **offer** for the product **waterskiing sharpness horseshoes** by a **US vendor** that is able to **deliver** within **3 days**".

| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
|1. Create and open a perspective from the "product" table|4|3|0|
|2. Open the filter popup and type "wat sha" (assume this makes the right product visible)|8|0|1|
|3. Select the "waterskiing sharpness horseshoes" product and close the filter popup|2|1|1|
|4. Make all the relevant fields visible|11|8|0|
|5. Filter "product.offer.vendor.country" to US only.|4|3|0|
|6. Insert a calculated column next to "offer.validto"|2|2|0|
|7. Key the cursor to the new calculated column and enter the formula "=[validTo]>{2008-06-15}"|16|0|1|
|8. Filter to show only products for which the formula is "true" (use keyboard shortcut since hand is already on keyboard)|6|0|0|
|9. Sort ascending on "product.offer.price"|2|2|0|
|10. Filter on "product.offer.deliveryDays" to include "1", "2", and "3"|6|5|0|
|Total Operators|61|24|3|
|Speed|39.8|||

**Task 12**. [Export the chosen offer into another information system which uses a different schema](/Benchmark/12.md)
> "Save in the local computer the information about the vendor for **Offer3499** and, if possible, restrict it to just label, homepage and country and map them to  **schema.org** terms name, url and nationality".

SIEUFERD does not yet have a data export feature, although results may be retrieved in a transformed schema; thus we rate SIEUFERD 50% on the "Capacity" scale for this task.

| Interaction Steps                                            |  K |  P |  H |
|--------------------------------------------------------------|----|----|----|
|1. Create and open a perspective from the "vendor" table|4|3|0|
|2. Show only the fields "label", "homepage", and "country", as well as "offer" and "offer.nr"|6|5|0|
|3. Filter "offer.nr" to show only Offer3499 (use keyboard shortcuts)|9|0|1|
|4. Hide "offer"|2|2|1|
|5. Key to the "label" column's heading and rename it to "name" (key right to the next column after editing).|7|0|0|
|6. Rename "homepage" to "url" (key right to the next column after editing)|4|0|0|
|7. Rename "country" to "nationality".|12|0|0|
|8. Export to CSV. (Assume this feature exists.)|4|4|0|
|Total Operators|48|14|2|
|Speed|25.8|||
