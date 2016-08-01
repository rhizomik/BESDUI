# Contributing to BESDUI

Please, to contribute to the Benchmark for End-User Structured Data User Interfaces (BESDUI), **FORK** this repository and, when your evaluation is completed, perform a **PULL REQUEST** to contribute your changes.

The data to be loaded to perform the evaluation is available from the [Datasets](Datasets) folder. The [bsbm-1000products.ttl.tgz](Datasets(bsbm-1000products.ttl.tgz) file contains the RDF version of the data.

To apply the benchmark, **perform each one of the tasks** with the evaluated tool and check if the expected results are obtained. If they are not, or it is **not possible** to complete the task, then report a **0% for the Capacity metric** for that task. **Otherwise**, the **Capacity is 100%**. In this case, also report how many **KLM operators** are required to complete the task. The operators are the basic user interactions:

* **K**: button press or keystroke, **keys** and not characters.
* **P**: pointing to a target on a display with a **mouse**. Time differs depending on distance and size of the target, but KVM simplifies this and makes it constant.
* **H**: homing the hand(s) on the keyboard or other device, this **includes** movement between any two devices.
 
When all tasks have been checked, you can **compute the BESDUI metrics** using the [BESDUI Spreadsheet](Results/BESDUI.xls).

To **contribute results**, please, use the [Evaluation Template](Results/EvaluationTemplate.md). Create a folder in [Results](Results) named after the evaluated tool and copy there the [EvaluationTemplate.md](Results/EvaluationTemplate.md). Then, rename it to **README.md** and fill it to report the results. You can also place in the same folder all other relevant files (images, spreadsheets,...). 

Finally, commit all changes to your fork and perform a **PULL REQUEST** to get your results published.
