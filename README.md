# OAG-Bench-Code

OAG-Bench is a __comprehensive and fine-grained__ human-curated benchmark based on the Open Academic Graph to cover the full life cycle of academic graph mining.
OAG-Bench currently includes 10 tasks. Each task consists of five parts: problem definition, datasets, evaluation metrics, comparison methods, and experimental results (leaderboard).

The tasks in OAG-Bench fall into two categories: academic graph construction and academic graph application. The former comprises 5 tasks, namely entity alignment, scholar profiling, author name disambiguation, entity tagging, and concept taxonomy completion. The latter also includes 5 tasks, i.e., paper recommendation, reviewer recommendation, academic question answering, paper source tracing, and academic influence prediction.

This repository offers basic dataset descriptions and code implementations for all tasks.
Please go to each directory for detailed environment setup and running steps.

For example,

```bash
git clone https://github.com/zfjsail/OAG-Bench.git
git submodule init
git submodule update --remote academic-influence-prediction/tot-prediction
```

## Data Description

### Entity Alignment
We provide three datasets to align the same real-world entity across different academic graphs. The venue dataset includes 1200 candidate pairs to align with ground-truths. Similarly, the affiliation dataset includes 5000 pairs, and the author dataset contains 10000 pairs.

### Scholar Profiling
CCKS2021-En comes from AMiner, which is an English subset of CCKS 2021 scholar profiling track. This dataset includes 9921 scholars.ScholarXL comes from the text description of the scholar's official homepage, and each attribute is manually marked with its starting and ending position in the text. This dataset is for long text extraction.

### Author Name Disambiguation
WhoIsWho is the world’s largest manually-labeled benchmark with over 1,000,000 papers built using an interactive annotation process and a regular leaderboard with comprehensive tasks, i.e., From-scratch Name Disambiguation, Real-time Name Disambiguation, and Incorrect Assignment Detection. The historical contests of WhoIsWho have already attracted more than 3,000 researchers.

### Entity Tagging
OPEDAC-2017: This dataset includes manually labeled research interest labels of 11357 scholars and their papers. Data from 6000 scholars are used for training, and the remaining data are used for a test set. DBLP-Paper-Topic: This dataset is based on the DBLP paper citation network. The topic of each paper is determined by its venue. There are 9 topics in total.

### Concept Taxonomy Completion
Given an existing concept hierarchy tree (Taxonomy) 𝑇0 and a set of new concepts 𝐶, the goal is to predict its hypernym pa(𝑐) ∈ 𝑇0 for each new concept 𝑐 ∈ 𝐶 to expand the existing concept hierarchy tree. We provide three concept taxonomy datasets here.

### Paper Recommendation
We provide user-paper interactions on AMiner.This dataset collects users' behavior on AMiner from Aug. 2021 to Nov. 2021. We filtered the most sparse records and kept users who at least clicked more than 10 papers. The partition of the train/validation/test file has been made and kept the ratio as 8:1:1. For each line in each file, the first number is the user ID, and the rest numbers are the paper IDs that this user clicked.

### Reviewer Recommendation
This dataset collects real paper-submission matching relations from Frontiers. In this dataset, we collect 210,069 reviewers and 225,478 papers.

### Academic Question Answering
We construct an academic QA dataset from real questions from Question-and-Answers (Q&A) forums. We retrieve question posts from StackExchange and Zhihu and extract the paper URLs cited by users in their answers. The paper is aligned with OAG and Semantic Scholar. The dataset contains 17,948 question-paper pairs, and we divide the question-paper pairs into 22 disciplines and 87 topics respectively, and has a two-level hierarchical structure where each topic is under a specific discipline.

### Paper Source Tracing
Given a paper 𝑝 (including the full text of the paper) and its references, the goal is to find the most important references (called ref-source) from the references. Ref-source largely inspired the paper 𝑝 in terms of ideas or methods. A paper can have one or more important references. For each reference in the paper 𝑝, an importance score in the range [0, 1] is calculated. Since the labeling of paper source tracing requires strong expertise, dozens of graduate students in the computer science field were hired to let them mark the source of papers in their familiar fields. After collection and preprocessing, the labeled data of 1120 papers in the computer science field were obtained.

### Academic Influence Prediction
OAG-Paper-TOT: This dataset collates Test-of-Time paper award data for selected conferences and journals in computer science. The meaning given to a paper by the Test-of-Time Award is: that the paper has produced a huge theoretical or applied influence several years after its publication. Awards with similar meanings include the Most Influential Award, Hall of Fame Award, etc. At present, a total of 1063 papers in the computer science field that are awarded by 2022 have been collected.AuthPred-2017 and AuthPred-2022 are to predict the citation number of authors in the future. Given the collection of papers published no later than 𝑦𝑟 (𝑦𝑟 is a year) and the citation relationship between papers, each paper contains attributes such as title, author, published conference or journal, year, etc. The goal is to predict the author's citations in 𝑦𝑟 + 𝛥𝑦𝑟 year.

## References
🌟 If you find our work helpful, please leave us a star and cite our paper.
```
@inproceedings{zhang2024oag,
  title={OAG-bench: a human-curated benchmark for academic graph mining},
  author={Fanjin Zhang and Shijie Shi and Yifan Zhu and Bo Chen and Yukuo Cen and Jifan Yu and Yelin Chen and Lulu Wang and Qingfei Zhao and Yuqing Cheng and Tianyi Han and Yuwei An and Dan Zhang and Weng Lam Tam and Kun Cao and Yunhe Pang and Xinyu Guan and Huihui Yuan and Jian Song and Xiaoyan Li and Yuxiao Dong and Jie Tang},
  booktitle={Proceedings of the 30th ACM SIGKDD Conference on Knowledge Discovery and Data Mining},
  pages={6214--6225},
  year={2024}
}
```
