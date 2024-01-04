# IBM Fairness 360

IBM Fairness 360 is an extensible open-source toolkit that can help you examine, report, and mitigate discrimination and bias in machine learning models throughout the AI application lifecycle. It contains fairness metrics for datasets and models, explanations for these metrics, and algorithms to mitigate bias in datasets and models.

## Features

- **Fairness Metrics**: Provides a comprehensive set of fairness metrics which are easy to understand and implement.
- **Bias Mitigation Algorithms**: Provides a wide range of bias mitigation algorithms that can be easily integrated into the machine learning workflow.
- **Explainability**: Provides detailed explanations for fairness metrics and bias mitigation to help understand the bias in the models.

## Installation

You can install IBM Fairness 360 using pip:

```bash
pip install aif360
```

## Usage

Here is a basic usage example:

```python
from aif360.datasets import BinaryLabelDataset
from aif360.metrics import BinaryLabelDatasetMetric
from aif360.algorithms.preprocessing import Reweighing

# Load dataset
dataset = BinaryLabelDataset(favorable_label=1, unfavorable_label=0, df=<your_dataframe>, label_names=['label'], protected_attribute_names=['protected_attribute'])

# Create metric object
metric = BinaryLabelDatasetMetric(dataset, unprivileged_groups=[{'protected_attribute': 0}], privileged_groups=[{'protected_attribute': 1}])

# Print out the metrics
print("Disparate Impact = %f" % metric.disparate_impact())
print("Statistical Parity Difference = %f" % metric.statistical_parity_difference())

# Apply reweighing
RW = Reweighing(unprivileged_groups=[{'protected_attribute': 0}], privileged_groups=[{'protected_attribute': 1}])
dataset_transf = RW.fit_transform(dataset)
```

For more detailed usage and examples, please refer to the [official IBM Fairness 360 documentation](https://aif360.readthedocs.io/).

## References

- [IBM Fairness 360 GitHub](https://github.com/IBM/AIF360)
- [IBM Fairness 360 Documentation](https://aif360.readthedocs.io/)
