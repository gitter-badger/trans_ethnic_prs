# trans_ethnic_prs

[![Join the chat at https://gitter.im/trans_ethnic_prs/community](https://badges.gitter.im/trans_ethnic_prs/community.svg)](https://gitter.im/trans_ethnic_prs/community?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

I plan to store the data in the `MatrixTable` from [Hail](https://hail.is/docs/0.2/overview/matrix_table.html?highlight=matrix%20table) which is a type of Genomic Dataframes. They support different type of data like VCF, Plink files,...

The main components are:

1. `datasets` (/transprs/datasets/)

In this component, each file will be an dataset and could be call by:

```python
from transprs.datasets import datasets_template
```

It should return a dataset file (hail.MatrixTable or pandas.DataFrame).

2. `methods` (/transprs/methods/)

In this component, each file will perform an method. It can run in any language or software but we will try wrap it in Python.

```python
from transprs.datasets import datasets_template
from transprs.methods import methods_template

# Perform a method
methods_template(datasets_template)
```

At the end, it should return a predicted results (hail.MatrixTable or pandas.DataFrame).

3. `metrics` (/transprs/metrics/)

In this component, each file will calculate a metric.

```python
from transprs.datasets import datasets_template
from transprs.methods import methods_template
from transprs.metrics import metrics_template

# Calculate metric
result = metrics_template(methods_template(datasets_template))
```

`result` will contain the metric result to compare with other methods.
