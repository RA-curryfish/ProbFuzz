# ProbFuzz
Data and code for the Probabilistic Analysis of GB Fuzzing

## Data
The data folder contains for various benchmarks indicated by their file names. This data contains information for each new libFuzzer discovery. An example and the format is as follows:

```
1901, 4
1901, 5, 5, 5, 5, 5, 5, 5, 5, 5, 4, 
1901, 8
1901, 1129
1901, 28062
1901, 205
1901, 46
1901, 12773
```
- each data point (discovery) has information 8 lines long
- 1901 indicates that there has been 1901 total mutations so far in the campaign. this exists in every line and only the values after it are described from here on
- Line 1: 4 indicates that a single seed was fuzzed for 4 times to discover a new feature
- Line 2: each value indicates number of times other seeds apart from the one above was fuzzed for without discovering anything after the previous discovery
- Line 3: number of features (coverage elements) discovered in this discovery
- Line 4: Mean Local Laplace estimate for number of trials required for next discovery
- Line 5: Mean Local Good-Turing estimate for number of trials required for next discovery
- Line 6: Maximum value of trials of forked attempts (10) for a new discovery
- Line 7: Average value of trials of forked attempts (10) for a new discovery
- Line 8: Rate of execution of the fuzzer in inputs per second at that point in time
