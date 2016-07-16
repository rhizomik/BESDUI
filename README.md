# SDEBM

Structured Data Exploration BenchMark (SDEBM) based on the [Berlin SPARQL Benchmark (BSBM)](http://wifo5-03.informatik.uni-mannheim.de/bizer/berlinsparqlbenchmark/) but intended for benchmarking the user experience while exploring a structured dataset, not the performance of the query engine.

> Roberto García, Rosa Gil, Juan Manuel Gimeno, Eirik Bakke, David R. Karger. (2016). Structured Data Exploration Benchmark (SDEBM). Available from: http://w3id.org/SDEBM

Please, look at [CONTRIBUTING](CONTRIBUTING.md) and [LICENSE](LICENSE) to know how you can contribute to the benchmark.

## Benchmarks

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

For the moment, three [Quality in Use metrics](http://www.jucs.org/jucs_19_8/using_SWET_QUM_to) have been used, one about effectiveness and two about efficiency:

* **Capacity** (effectiveness): what proportion of one task is completed. 0% if not possible to complete or 100% otherwise.
* **Operation Count** (efficiency): how many KLM Operators are required to complete the task.
* **Time** (efficiency): each KLM Operator has a corresponding average time to complete it as detailed in the table below. For a task, this metric is computed by multiplying, for each operator type, the time for each operator by the operator count. Then, summing them all together.

| KLM Operator                                                                                                                        | Time (seconds) |
|-------------------------------------------------------------------------------------------------------------------------------------|----------------|
| K: button press or keystroke, keys and not characters.                                                                              | 0.2            |
| P: pointing to a target on a display with a mouse. Time differs depending on distance and size of the target, but is held constant. | 1.1            |
| H: homing the hand(s) on the keyboard or other device, this includes movement between any two devices.                              | 0.4            |

## Results

Currently, the SDEBM has been applied to the following tools:

* **[Rhizomer](/Results/Rhizomer)**: a semantic data exploration tool.
* **[Virtuoso](/Results/Virtuoso)**: the faceted browser for the Virtuoso RDF data store.
* **[Sieuferd](/Results/Sieuferd)**: a general-purpose user interface for relational databases.
