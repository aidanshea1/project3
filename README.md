# Large Scale Data Processing: Project 3
# Aidan Shea
# Results
### Running Verify MIS locally
|        Graph file       |           MIS file           | Is an MIS? |
| ----------------------- | ---------------------------- | ---------- |
| small_edges.csv         | small_edges_MIS.csv          | Yes        |
| small_edges.csv         | small_edges_non_MIS.csv      | No         |
| line_100_edges.csv      | line_100_MIS_test_1.csv      | Yes        |
| line_100_edges.csv      | line_100_MIS_test_2.csv      | No         |
| twitter_10000_edges.csv | twitter_10000_MIS_test_1.csv | Yes        |
| twitter_10000_edges.csv | twitter_10000_MIS_test_2.csv | Yes        |
### Running LubyMIS locally
|        Graph file       | Iterations | Runtime |
| ----------------------- | ---------- | ------- |
| small_edges.csv         |    1       |    2s   |
| line_100_edges.csv      |    3       |    5s   |
| twitter_100_edges.csv   |    2       |    2s   |
| twitter_10000_edges.csv |    2       |    2s   |
| twitter_10000_edges.csv |    3       |    3s   |

### Running LubyMIS on GCP
##### 3x4 Cores on twitter_original_edges.csv
|        Graph file          | Iterations | Remaining Vertices After Each Iteration | Runtime |
| -------------------------- | ---------- | --------------------------------------- | ------- |
| twitter_original_edges.csv |     5      | 6793623, 39692, 558, 3, 0               | 167s    |

##### 4x2 Cores on twitter_original_edges.csv
|        Graph file          | Iterations | Remaining Vertices After Each Iteration | Runtime |
| -------------------------- | ---------- | --------------------------------------- | ------- |
| twitter_original_edges.csv |     4      | 6972866, 35697, 395, 0                  | 117s    |

##### 2x2 Cores on twitter_original_edges.csv
|        Graph file          | Iterations | Remaining Vertices After Each Iteration | Runtime |
| -------------------------- | ---------- | --------------------------------------- | ------- |
| twitter_original_edges.csv |     5      | 7135362, 42013, 633, 4, 0               | 402s    |

###### From the data it appears that lowering the number of worker nodes and lowering the cores for each worker node increases the amount of time it takes for the algorithm to run. The configuration with 4 worker nodes with 2 cores each had a shorter runtime than the configuration with 3 worker nodes with 4 cores each which perhaps suggests that the amount of worker nodes makes a larger impact on the runtime than the amount of cores for each worker node.
