# COVID19-CovSyn-Data-Taiwan-Country-AdjustedSecondaryAttackRate-9-1
Repository for synthetic data generated using CovSyn Taiwan with adjusted secondary attack rate, multiplied by 9, 100 simulations.

# case_edge_list/

## 📌 Description

This folder contains transmission edges for each simulated outbreak seed.  
Each file represents **one complete transmission network**.

Files are named:case_edge_list_<seed>.npy

Each file contains a NumPy array of tuples with shape:
(source_case_id, infectee_case_id, infection_day, contact_layer)


### ✔ Meaning of Each Field

| Field | Description |
|-------|-------------|
| `source_case_id` | The ID of the individual who caused the infection |
| `infectee_case_id` | The newly infected individual's case ID |
| `infection_day` | Simulation day when infection occurred |
| `contact_layer` | One of: `household`, `school`, `workplace`, `health_care`, `municipality` |

### ✔ How to Use

These networks allow:

- Computing ground-truth R₀  
- Identifying superspreaders  
- Reconstructing transmission trees  
- Analyzing network degree distributions  
- Benchmarking statistical R₀ estimators (SeqB, WP, ID/IDEA, EG…)  

### ✔ Example Loader

```python
import numpy as np

edges = np.load("case_edge_list_0.npy", allow_pickle=True)




