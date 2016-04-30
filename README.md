# SDEBM

Structured Data Exploration BenchMark (SDEBM) inspired by the Berlin SPARQL Benchmark (BSBM) but intended for benchmarking the user experience while exploring a structured dataset, not the performance of the query engine.

> Roberto García, Rosa Gil, Juan Manuel Gimeno, Eirik Bakke, David R. Karger. (2016). Structured Data Exploration Benchmark (SDEBM). Available from: http://w3id.org/SDEBM

## Benchmarks

**Task 1**. [Find products for a given set of features combined](Benchmarks/1.md)

**Task 2**. [Find products for a given set of alternative features](Benchmarks/2.md)

**Task 3**. [Retrieve basic information about a specific product for display purposes](Benchmarks/3.md)

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

## Metrics

For the moment, three [Quality in Use metrics](http://www.jucs.org/jucs_19_8/using_SWET_QUM_to) have been used, one about effectiveness and two about efficiency:

* **Capacity** (effectiveness): what proportion of one task is completed. 0% if not possible to complete or 100% otherwise.
* **Operation Count** (efficiency): how many KLM Operators are required to complete the task.
* **Speed** (efficiency): each KLM Operator has a corresponding average time to complete it as detailed in the table below. For a task, this metric is computed by multiplying, for each operator type, the time for each operator by the operator count. Then, summing them all together.

| KLM Operator                                                                                                                        | Time (seconds) |
|-------------------------------------------------------------------------------------------------------------------------------------|----------------|
| K: button press or keystroke, keys and not characters.                                                                              | 0.2            |
| P: pointing to a target on a display with a mouse. Time differs depending on distance and size of the target, but is held constant. | 1.1            |
| H: homing the hand(s) on the keyboard or other device, this includes movement between any two devices.                              | 0.4            |
