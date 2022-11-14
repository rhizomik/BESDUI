# BESDUI

Benchmark for End-User Structured Data User Interfaces (BESDUI) based on the [Berlin SPARQL Benchmark (BSBM)](http://wifo5-03.informatik.uni-mannheim.de/bizer/berlinsparqlbenchmark/) but intended for benchmarking the user experience while exploring a structured dataset, not the performance of the query engine. BSBM is just used to provide the data to be explored.

This is a cheap User Interface benchmark as it does not involve users but experts, who measure how many interaction steps are required to complete each of the benchmark tasks, if possible. This also facilitates comparing different tools without the bias that different end-user profiles might introduce. The way to measure this interaction steps and convert them to an estimate of the required time to complete a task is based on the [Keystroke-Level Model (KLM)](https://en.wikipedia.org/wiki/Keystroke-level_model)

Reference

> García, Roberto; Gil, Rosa María; Bakke, Eirik; Karger, David R. (2020). A benchmark for end-user structured data exploration and search user interfaces. Journal of Web Semantics, 2020, vol. 65, p. 100610. DOI: [10.1016/j.websem.2020.100610](https://doi.org/10.1016/j.websem.2020.100610). Preprint: [10459.1/69484](http://hdl.handle.net/10459.1/69484)

## Benchmark Tasks

**Task 1**. [Find products for a given set of features combined](Benchmark/1.md)

**Task 2**. [Find products for a given set of alternative features](Benchmark/2.md)

**Task 3**. [Retrieve basic information about a specific product for display purposes](Benchmark/3.md)

**Task 4**. [Find products having some specific features and not having one feature](Benchmark/4.md)

**Task 5**. [Find products matching two different sets of features](Benchmark/5.md)

**Task 6**. [Find products that are similar to a given product](Benchmark/6.md)

**Task 7**. [Find products having a name that contains some text](Benchmark/7.md)

**Task 8**. [Retrieve in-depth information about a specific product including offers and reviews](Benchmark/8.md)

**Task 9**. [Give me recent reviews in English for a specific product](Benchmark/9.md)

**Task 10**. [Get information about a reviewer](Benchmark/10.md)

**Task 11**. [Get offers for a given product which fulfill specific requirements](Benchmark/11.md)

**Task 12**. [Export the chosen offer into another information system which uses a different schema](Benchmark/12.md)

## Metrics

Based on benchmark, three [Quality in Use metrics](http://www.jucs.org/jucs_19_8/using_SWET_QUM_to) have been proposed, one about effectiveness and two about efficiency:

* **Capability (C)** (effectiveness): what proportion of one task is completed (0% if not possible to complete or 100% otherwise) or, for the whole benchmark, the percentage of all 12 tasks completed.
* **Operator Count (OC)** (efficiency): how many KLM Operators, from Table 1, are required to complete a task or the average count just for completed tasks.
* **Time (T)** (efficiency): each KLM Operator has a corresponding average time to complete it as detailed in Table 1. For a task, this metric is computed by multiplying, for each operator type, the time for each operator by the operator count. Then, summing them all together. For the whole benchmark, it is the average time considering just the completed tasks.

Additionally, there is a combined effectiveness/efficiency metric:

* **Task Efficiency (TE)** (effectiveness/efficiency): measured as the ratio of **Capability** to **Time**, "goals per second". For the whole benchmark it is computed using the percentage of all 12 tasks completed divided by the average time for the completed tasks.

| Keystroke-Level Model (KLM) Operator                                                                                                | Time (seconds) |
|-------------------------------------------------------------------------------------------------------------------------------------|----------------|
| K: button press or keystroke, keys and not characters.                                                                              | 0.2            |
| P: pointing to a target on a display with a mouse. Time differs depending on distance and size of the target, but is held constant. | 1.1            |
| H: homing the hand(s) on the keyboard or other device, this includes movement between any two devices.                              | 0.4            |

Table 1. Interaction steps used to complete a benchmark task and their corresponding average time to be completed

## Results

Currently, the BESDUI has been applied to the following tools:

* **[Rhizomer](/Results/Rhizomer)**: the old version of RhizomerEye, a semantic data exploration tool.
* **[RhizomerEye](/Results/RhizomerEye)**: the current version of Rhizomer, a semantic data exploration tool.
* **[Virtuoso FCT](/Results/Virtuoso)**: the faceted browser for the Virtuoso RDF data store.
* **[Sieuferd](/Results/Sieuferd)**: a general-purpose user interface for relational databases.
* **[PepeSearch](/Results/PepeSearch)**: a search interface for querying SPARQL endpoints.

| Averages per Tool | Capability | K (0.2s) | P (1.1s) | H (0.4s) | Operator Count | Time     | Task Efficiency |
|-------------------|------------|----------|----------|----------|----------------|----------|-----------------|
| RHIZOMER          | 58%        | 16.4     | 11.0     | 2.9      | 30.3           | 16.5     | 2.1             |
| RHIZOMEREYE       | 58%        | 13.0     | 8.7      | 2.7      | 24.4           | 13.3     | **2.6**         |
| VIRTUOSO FCT      | 46%        | 23.5     | 14.5     | 3.5      | 41.5           | 22.1     | 1.2             |
| SIEUFERD          | **96%**    | 48.7     | 19.8     | 2.9      | 71.3           | 32.63    | 1.8             |
| PEPESEARCH        | 25%        | 12.7     | 5.3      | 5.3      | **23.3**       | **10.5** | 1.4             |

Table 2. Benchmark results for different End-User Structured Data User Interfaces. Showing the average for all completed benchmark tasks. Best results are in bold

## Contributing

BESDUI is available under a Creative Commons Attribution-ShareAlike 4.0 International [LICENSE](LICENSE). To contribute to the Benchmark for End-User Structured Data User Interfaces (BESDUI), **FORK** the [BESDUI GitHub repository](https://github.com/rhizomik/BESDUI) and, when your evaluation is completed, perform a **PULL REQUEST** to propose your changes. Alternatively, you can download all the required data to prepare your contribution from http://hdl.handle.net/10459.1/69484

The data to be loaded to perform the evaluation is available from the [Datasets](Datasets) folder. The [bsbm-1000products.ttl.tgz](Datasets/bsbm-1000products.ttl.tgz) file contains the RDF version of the test data.

To apply the benchmark, **perform each one of the tasks** with the evaluated tool and check if the expected results are obtained. If they are not, or it is **not possible** to complete the task, then report a **0% for the Capability metric** for that task. **Otherwise**, the **Capability is 100%**. In this case, also report how many **KLM operators** are required to complete the task. The operators are the basic user interactions:

* **K**: button press or keystroke, **keys** and not characters.
* **P**: pointing to a target on a display with a **mouse**. Time differs depending on distance and size of the target, but KVM simplifies this and makes it constant.
* **H**: homing the hand(s) on the keyboard or other device, this **includes** movement between any two devices.

When all tasks have been checked, you can **compute the BESDUI metrics** using the [BESDUI Spreadsheet](Results/BESDUI.xls).

To **contribute results**, please, use the [Evaluation Template](Results/EvaluationTemplate.md). Create a folder in [Results](Results) named after the evaluated tool and copy there the [EvaluationTemplate.md](Results/EvaluationTemplate.md). Then, rename it to **README.md** and fill it to report the results. You can also place in the same folder all other relevant files (images, spreadsheets,...). 

Finally, commit all changes to your fork and perform a **PULL REQUEST** to get your results published. Alternatively, you can just send the file with your results to roberto.garcia@udl.cat 

## Acknowledgements

This project has been partially supported by the research project InDAGuS, Infrastructures for Sustainable Open Government Data with Geospatial Features (Spanish Government TIN2012-37826-C02), together with the Universitat de Lleida and the Massachusetts Institute of Technology.

<img src="https://rhizomik.net/html/images/Logo_UdL.svg" height="60px" alt="Universitat de Lleida"/>&nbsp;&nbsp;&nbsp;<img src="https://hcie.csail.mit.edu/fabpub/logo/csail.svg" height="60px" alt="Massachusetts Institute of Technology - Computer Science and Artificial Intelligence Laboratory"/>
