# Aequitas

Aequitas is an open-source bias audit toolkit for machine learning developers, analysts, and policy makers to audit machine learning models for discrimination and bias, and to make informed and equitable decisions around developing and deploying predictive risk-assessment tools.

## Features

- **Bias Report**: Provides a detailed bias report across multiple protected classes.
- **Bias Metrics**: Provides a wide range of bias metrics like disparate impact, false positive rate disparity, etc.
- **Visualizations**: Provides visualizations to help understand the bias in the models.

## Installation

You can install Aequitas using pip:

```bash
pip install aequitas
```

## Usage

Here is a basic usage example:

```python
from aequitas.preprocessing import preprocess_input_df
from aequitas.group import Group
from aequitas.bias import Bias
from aequitas.fairness import Fairness

# Preprocess input data
df, _ = preprocess_input_df(<your_dataframe>)

# Define group class
g = Group()
xtab, _ = g.get_crosstabs(df)

# Define bias class
b = Bias()
bdf = b.get_disparity_predefined_groups(xtab, original_df=df, ref_groups_dict={'race':'Caucasian', 'sex':'Male', 'age':'25 - 45'})

# Define fairness class
f = Fairness()
fdf = f.get_group_value_fairness(bdf)
```

For more detailed usage and examples, please refer to the [official Aequitas documentation](https://github.com/dssg/aequitas).

## References

- [Aequitas GitHub](https://github.com/dssg/aequitas)
- [Aequitas Documentation](http://docs.dssg.io/aequitas/)
