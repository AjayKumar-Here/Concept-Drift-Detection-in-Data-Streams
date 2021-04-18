## Concept Drift Detection in Data Streams Using ADWIND and Naive Bayes classifier

## AdWin:  ADaptive sliding WINdow algorithm

Based on paper: 

*Bifet and R. Gavalda. 2007. Learning from Time-Changing Data with Adaptive Windowing*

```python
class concept_drift.adwin.AdWin(
    delta=0.002, max_buckets=5, min_clock=32, min_win_len=10, min_sub_win_len=5
)
```

| Parameters | |
| ------------- | ------------- |
| delta |Confidence value |
| max_buckets | Max number of buckets within one bucket row |
| min_clock | Min number of new data for starting to reduce window and detect change |
| min\_window\_len | Min window length for starting to reduce window and detect change |
| min\_sub\_window\_len | Min sub-window length, which is split from whole window |

**Methods**

```python
set_input(value)
```
> Set input value to the drift detector - ADWIN.

|Type| Input - Output |
|---|----|
| Parameters | **value**: Input value |
| Return | Boolean: Whether has drift  |

**Example**

```python
from concept_drift.adwin import AdWin

adwin = AdWin()
for i in range(1000):
    if adwin.set_input(i):
        print("Here is a drift")
```
GaussianNB:
Mean acc within the window 300: 73.22457902031908

AdWin:
Drift detection: 168
Mean acc within the window 300: 74.65794479341767
```


