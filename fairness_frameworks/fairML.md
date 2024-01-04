# FairML

FairML is a python toolbox auditing the machine learning models for bias. It allows the user to understand the impact of each feature in the model prediction. It's a valuable tool for inspecting black box models and ensuring fairness.

## Features

- **Feature Importance**: Provides a detailed report on the importance of each feature in the model.
- **Bias Detection**: Helps in detecting any bias in the model towards any particular feature.
- **Black Box Inspection**: Allows inspection of black box models.

## Installation

You can install FairML using pip:

```bash
pip install fairml
```

## Usage

Here is a basic usage example:

```python
from fairml import audit_model
from fairml import plot_dependencies

# Load your model
# model = ...

# Load your data
# ProPublica_data = ...

# Call audit model with model
total, _ = audit_model(model.predict, ProPublica_data)

# Print feature importance
print(total)

# Plot feature dependence
plot_dependencies(
    total.median(),
    reverse_values=False,
    title="FairML feature dependence"
)
```

For more detailed usage and examples, please refer to the [official FairML documentation](https://fairml.readthedocs.io/).

## References

- [FairML GitHub](https://github.com/adebayoj/fairml)
- [FairML Documentation](https://fairml.readthedocs.io/)
