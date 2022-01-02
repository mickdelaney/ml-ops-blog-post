# ML Ops Blog Post

## MLFlow Classifier

```bash
docker build -t ml-ops-blog-post-mlflow-classifier -f Dockerfile .

mlflow run . -P alpha=0.5.

```

### Register Model

```python
import mlflow
logged_model = 'runs:/dbd684db1ee6455d8b0c42bc3af6cd53/model'

# Load model as a PyFuncModel.
loaded_model = mlflow.pyfunc.load_model(logged_model)

# Predict on a Pandas DataFrame.
import pandas as pd
loaded_model.predict(pd.DataFrame(data))
```