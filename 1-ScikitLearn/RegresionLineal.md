## Boston

```python
from sklearn.datasets import load_boston
boston = load_boston()
print(boston.data.shape)
boston.keys()

boston.feature_names

boston_data = pd.DataFrame(boston['data'], columns=boston.feature_names)
boston_target = pd.DataFrame(boston['target'], columns={'Target'})
print(boston_data.head(2))
print(boston_target.head(2))
```
