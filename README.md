# GSE70394 differential expression in Python

Learning project — not a discovery.

**Dataset:** GSE70394 (NCBI GEO): AGS stomach cells co-cultured with H. pylori
(strain ATCC49503) vs uninfected controls, 3 samples per group.

**Question:** Which genes change activity when stomach cells meet H. pylori?

**Method:** Plain Welch t-test per probe + Benjamini-Hochberg correction
(Python: pandas, scipy, statsmodels). No limma — that is the point of
this project.

**What I found:** Zero significant genes (padj < 0.05 and |log2FC| > 1)
out of 29,009 probes tested. But the pipeline reproduced my earlier R
results in direction and size: IL24 up ~54x, BIRC3 up ~10x, MUC4 up ~5x,
FGA/FGG down ~9-13x — all uncertified by BH at n=3 per group. The lesson:
with 3 vs 3 samples, a plain t-test cannot certify even a 54x jump.
That is why limma exists.

**Files:**
- `Week1_GSE70394_DEG.ipynb` — the notebook
- `week1_deg_results_named.csv` — full DEG table with gene symbols
- `week1_volcano.png` — volcano plot (empty top corners = the result)
- `week1_heatmap.png` — heatmap of the top 25 genes by padj

Learning bioinformatics from scratch, with AI as my teacher. — Week 1.
