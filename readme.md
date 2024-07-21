# IFMA-VD: Boosting Vulnerability Detection with Inter-Function Multilateral Association Insights

We proposed the IFMA-VD framework, which innovatively uses hypergraphs to model multilateral behavior associations. This framework includes an Inter-Function Multilateral Association analysis component designed to enhance vulnerability detection performance.

![image](![image](https://github.com/user-attachments/assets/e88778df-351c-4c87-a9b2-945648c14abe))


## Dataset

We conducted experiments using three widely recognized datasets in vulnerability detection research. The statistical data for these datasets are as follows:

|     Datasets     |  #Samples  |  #Vul   |  #Non-vul  |  Vul Ratio  |
|:----------------:|:----------:|:-------:|:----------:|:-----------:|
|      FFmpeg      |   9,768    |  4,981  |   4,788    |   51.10%    |
|       Qemu       |   17,549   |  7,479  |   10,070   |   42.62%    |
|  Chrome+Debian   |   22,734   |  2,240  |   20,494   |    9.85%    |

These three datasets are saved in `./data/`.

## Implementation

The framework includes three main stages:
1. **Parsing functions into code property graphs (CPG) and generating intra-function features.**
2. **Constructing a code behavior hypergraph and extracting inter-function multilateral association features.**
3. **Applying classification techniques to detect the presence of vulnerabilities.**

### Intra-Function Features Generation
- Parse data into CPG and PDG using [Joern](https://github.com/joernio/joern):
- Train intra-function feature extraction module from CPG.

### Inter-Function Features Generation
- Extract function behavior slices.
- Construct code behavior hypergraph.

### Vulnerability Detection
- Extract multilateral association features for vulnerability detection: `./IFMA-VD.py`

We provide pre-generated intra-function features and code behavior hypergraphs, available for download at [Processed dataset](https://drive.google.com/file/d/1e2QyEppFSOpOOWaXXFbTkIPYj3f4hDVK/view?usp=drive_link). After downloading, run `./IFMA-VD.py`.

## Checking Experimental Results

- Please check the folders `./results` for the experimental results.
