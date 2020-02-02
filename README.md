# BESDUI

Benchmark for End-User Structured Data User Interfaces (BESDUI) based on the [Berlin SPARQL Benchmark (BSBM)](http://wifo5-03.informatik.uni-mannheim.de/bizer/berlinsparqlbenchmark/) but intended for benchmarking the user experience while exploring a structured dataset, not the performance of the query engine. BSBM is just used to provide the data to be explored.

This is a cheap User Interface benchmark as it does not involve users but experts, who measure how many interaction steps are required to complete each of the benchmark tasks, if possible. This also facilitates comparing different tools without the bias that different end-user profiles might introduce. The way to measure this interaction steps and convert them to an estimate of the required time to complete a task is based on the [Keystroke-Level Model (KLM)](https://en.wikipedia.org/wiki/Keystroke-level_model)

Please, look at [CONTRIBUTING](CONTRIBUTING.md) and [LICENSE](LICENSE) to know how you can contribute to the benchmark by applying it to End-User Structured Data User Interfaces.

# Reference

> Roberto García, Rosa Gil, Juan Manuel Gimeno, Eirik Bakke, David R. Karger. (2016). BESDUI: A Benchmark for End-User
Structured Data User Interfaces. Available from: http://w3id.org/BESDUI

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

| Keystroke-Level Model (KLM) Operator                                                                                                                        | Time (seconds) |
|-------------------------------------------------------------------------------------------------------------------------------------|----------------|
| K: button press or keystroke, keys and not characters.                                                                              | 0.2            |
| P: pointing to a target on a display with a mouse. Time differs depending on distance and size of the target, but is held constant. | 1.1            |
| H: homing the hand(s) on the keyboard or other device, this includes movement between any two devices.                              | 0.4            |

Table 1. Interaction steps used to complete a benchmark task and their corresponding average time to be completed

## Results

Currently, the BESDUI has been applied to the following tools:

* **[Rhizomer](/Results/Rhizomer)**: a semantic data exploration tool.
* **[Virtuoso FCT](/Results/Virtuoso)**: the faceted browser for the Virtuoso RDF data store.
* **[Sieuferd](/Results/Sieuferd)**: a general-purpose user interface for relational databases.
* **[PepeSearch](/Results/PepeSearch)**: a search interface for querying SPARQL endpoints.

|Averages per Tool|Capability|K (0.2s)|P (1.1s)|H (0.4s)|Operator Count|  Time  |Task Efficiency|
|-----------------|----------|--------|--------|--------|--------------|--------|---------------|
|   RHIZOMER      |    58%   | 15.9   | 10.9   | 2.6    |   29.3       |  16.1  |    **2.2**    |
|   VIRTUOSO FCT  |    54%   | 20.4   | 12.7   | 3.0    |   36.1       |  19.3  |      1.7      |
|   SIEUFERD      |  **96%** | 48.7   | 19.75  | 2.92   |   71.3       |  32.63 |      1.8      |
|   PEPESEARCH    |    25%   | 12.7   |  5.3   | 5.3    | **23.3**     |**10.5**|      1.4      |

Table 2. Benchmark results for different End-User Structured Data User Interfaces. Showing the average for all completed benchmark tasks. Best results are in bold

## Acknowledgements

This project has been partially supported by the research project InDAGuS, Infrastructures for Sustainable Open Government Data with Geospatial Features (Spanish Government TIN2012-37826-C02), together with the Universitat de Lleida and the Massachusetts Institute of Technology.

<img src="http://www.eps.udl.cat/export/sites/Eps/UdL-EPS.jpg" height="60px" alt="Universitat de Lleida"/>&nbsp;&nbsp;&nbsp;<img src="https://cdn.www.getsmarter.com/uploads/partner/university_logo/15/mit-csail-logo-light-f40bf6d3c32d99046549389ec42ed1e4.jpg" height="60px" alt="Massachusetts Institute of Technology - Computer Science and Artificial Intelligence Laboratory"/>
