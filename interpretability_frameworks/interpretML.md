# InterpretML

InterpretML is an open-source library for training interpretable machine learning models and explaining black box systems. It is developed by Microsoft Research.

## Overview

InterpretML is a machine learning interpretability package for training interpretable models and explaining black box systems. It exposes a consistent API for both methods, and it also includes functionality for visualizing the interpretability of models.

## Features

- **Interpretable Models:** InterpretML includes several interpretable models, such as Explainable Boosting Machine (EBM), which is a glassbox model that has accuracy comparable to state-of-the-art methods like XGBoost and Random Forests, but is more interpretable.
- **Model Explanations:** InterpretML can explain black box models with techniques like SHAP, LIME, and others.
- **Visualization:** InterpretML includes functionality for visualizing the interpretability of models.

## Installation

You can install InterpretML using pip:

```bash
pip install interpret
```

## Usage

Here is a basic example of using InterpretML to train an interpretable model and explain it:

```python
from interpret.glassbox import ExplainableBoostingClassifier
from interpret import show

# Initialize the model
ebm = ExplainableBoostingClassifier()

# Fit the model
ebm.fit(X_train, y_train)

# Explain the model
ebm_global = ebm.explain_global()
show(ebm_global)
```

## Resources

For more information about InterpretML, you can visit the [official documentation](https://interpret.ml/).
