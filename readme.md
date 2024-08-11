# IFMA-VD: Boosting Vulnerability Detection with Inter-Function Multilateral Association Insights

We proposed the IFMA-VD framework, which innovatively uses hypergraphs to model multilateral behavior associations. This framework includes an Inter-Function Multilateral Association analysis component designed to enhance vulnerability detection performance.

## The latest experimental results.

|      Datasets       |           |  FFmpeg   |          |           |   Qemu    |          |           | Chrome+Debian |          |
|:-------------------:|:---------:|:---------:|:--------:|:---------:|:---------:|:--------:|:---------:|:-------------:|:--------:|
|     **Method**      |    F1     | Precision |  Recall  |    F1     | Precision |  Recall  |    F1     |   Precision   |  Recall  |
|  Devign(NIPS2019)   |   51.9    |   52.2    |   52.1   |   53.7    |   53.1    |   53.4   |   28.4    |     24.1      |   28.7   |
| CodeBERT(arXiv2020) |   53.0    |   54.9    |   51.2   |   54.1    |   55.2    |   52.3   |   25.4    |     23.7      |   27.4   |
|   IVDect(FSE2021)   |   65.5    |   50.8    |   64.6   |   57.9    |   52.5    |   64.6   |   38.8    |     38.1      |   39.5   |
|   Reveal(TSE2021)   |   62.6    |   50.6    |   82.4   |   49.3    |   45.2    |   54.0   |   26.3    |     24.4      |   28.6   |
|  VulCNN(ICSE2022)   |   54.2    |   51.2    |   57.7   |   55.1    |   52.3    |   58.2   |   31.5    |     22.8      |   51.0   |
|   VulBG(ICSE2023)   |   57.5    |   52.8    |   62.1   |   55.9    |   53.2    |   58.9   |   36.5    |     26.4      |   59.3   |
|  PDBert(ICSE2024)   |   52.4    |  =66.8=   |   43.2   |   62.4    |  =65.4=   |   59.8   |    47.9   |    =51.0=     |   45.4   |
|    IFMA-VD(ours)    |  =69.1=   |   54.1    |  =95.9=  |  =62.5=   |   53.8    |  =74.4=  |  =50.8=   |     37.5      |  =78.6=  |
|        W/T/L        |   7/0/0   |   5/0/2   |  7/0/0   |   7/0/0   |   5/0/2   |  7/0/0   |   7/0/0   |     5/0/2     |  7/0/0   |


<!-- ![image](https://github.com/user-attachments/assets/4c27a639-6a87-4818-8beb-e303ff3a8552) -->

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
