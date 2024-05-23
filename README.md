This is the official code of paper 'DeMamba: AI-Generated Video Detection on Million-Scale GenVideo Benchmark'.

## Dataset download
![](figs/tab_fig.jpg)
Our GenVideo will be public at https://github.com/ant-research/Gen-Video.

Statistics of real and generated videos in the GenVideo dataset:

## Detail Mamba (DeMamba)

![](figs/logo.png)
<p align="center"><em>In memory of Kobe Bryant (generated by GPT-4o)</em></p>

> "Determination wins games, but Detail wins championships." — *Kobe Bryant, in his Show Detail, 2018*


## Leaderboard

### Many-to-many generalization task
| Model         | Detection Level | Metric | Sora  | Morph | Gen2  | HotShot | Lavie | Show-1 | Moon  | Crafter | Model Scope | Wild Scrape | Real  | Avg.   |
|---------------|-----------------|--------|-------|-------|-------|---------|-------|--------|-------|---------|-------------|-------------|-------|--------|
| F3Net         | Image           | ACC    | 83.93 | 99.71 | 98.62 | 77.57   | 57.00 | 36.57  | 99.52 | 99.71   | 89.43       | 76.78       | 99.14 | 83.45  |
|               |                 | AP     | 68.27 | 99.89 | 99.67 | 89.35   | 85.24 | 63.17  | 99.58 | 99.89   | 93.80       | 88.41       | -     | 88.73  |
| NPR           | Image           | ACC    | 91.07 | 99.57 | 99.49 | 24.29   | 89.64 | 57.71  | 97.12 | 99.86   | 94.29       | 87.80       | 97.46 | 85.30  |
|               |                 | AP     | 67.17 | 99.14 | 99.20 | 22.76   | 93.91 | 61.76  | 96.33 | 99.72   | 94.15       | 90.40       | -     | 82.45  |
| STIL          | Video           | ACC    | 78.57 | 98.14 | 98.04 | 76.00   | 61.79 | 53.29  | 99.36 | 97.36   | 94.57       | 65.01       | 98.72 | 83.71  |
|               |                 | AP     | 57.21 | 99.08 | 99.32 | 86.19   | 82.24 | 70.43  | 99.25 | 98.96   | 97.18       | 81.32       | -     | 87.12  |
| VideoMAE-B    | Video           | ACC    | 67.86 | 96.00 | 98.41 | 96.14   | 77.14 | 80.43  | 97.44 | 96.93   | 96.29       | 68.36       | 99.71 | 88.61  |
|               |                 | AP     | 66.49 | 98.85 | 99.77 | 99.27   | 96.55 | 95.31  | 99.49 | 99.69   | 99.27       | 90.74       | -     | 94.54  |
| CLIP-B-PT     | Image           | ACC    | 85.71 | 82.43 | 90.36 | 71.00   | 79.29 | 75.43  | 89.62 | 86.29   | 82.14       | 75.16       | 57.22 | 79.67  |
|               |                 | AP     | 6.78  | 43.56 | 70.88 | 29.97   | 52.97 | 35.36  | 55.52 | 66.03   | 44.23       | 42.99       | -     | 44.83  |
| DeMamba-CLIP-PT| Video          | ACC    | 58.93 | 96.43 | 93.12 | 68.00   | 69.36 | 69.00  | 89.14 | 91.86   | 96.14       | 56.59       | 98.06 | $80.60_{\textcolor[RGB]{116,0,0}{+0.93}}$ |
|               |                 | AP     | 25.87 | 95.14 | 96.23 | 73.43   | 83.31 | 75.49  | 90.17 | 95.06   | 95.05       | 69.95       | -     | $79.97_{\textcolor[RGB]{116,0,0}{+35.14}}$ |
| CLIP-B-FT     | Image           | ACC    | 94.64 | 99.86 | 91.38 | 77.29   | 88.14 | 86.00  | 99.68 | 99.79   | 84.29       | 84.67       | 97.38 | 91.19  |
|               |                 | AP     | 80.67 | 99.67 | 95.24 | 82.20   | 93.48 | 88.62  | 99.55 | 99.79   | 86.93       | 89.08       | -     | 91.52  |
| DeMamba-CLIP-FT| Video          | ACC    | 95.71 | 100.00| 98.70 | 69.14   | 92.43 | 93.29  | 100.00| 100.00  | 83.57       | 82.94       | 99.44 | $92.29_{\textcolor[RGB]{116,0,0}{+1.10}}$ |
|               |                 | AP     | 85.50 | 100.00| 99.59 | 76.15   | 96.78 | 96.99  | 99.97 | 100.00  | 89.80       | 89.72       | -     | $93.45_{\textcolor[RGB]{116,0,0}{+1.93}}$ |
| XCLIP-B-PT    | Video           | ACC    | 81.34 | 82.15 | 83.35 | 80.98   | 81.82 | 81.55  | 82.14 | 82.98   | 81.93       | 81.10       | 81.37 | 81.88  |
|               |                 | AP     | 16.39 | 72.16 | 87.77 | 39.86   | 65.57 | 54.26  | 75.23 | 84.80   | 61.60       | 55.28       | -     | 61.29  |
| DeMamba-XCLIP-PT| Video         | ACC    | 66.07 | 95.86 | 94.64 | 77.86   | 75.36 | 80.29  | 90.89 | 92.50   | 96.00       | 66.41       | 95.12 | $84.64_{\textcolor[RGB]{116,0,0}{+2.76}}$ |
|               |                 | AP     | 18.26 | 93.50 | 94.72 | 69.94   | 78.08 | 71.50  | 83.95 | 92.23   | 93.54       | 68.10       | -     | $76.38_{\textcolor[RGB]{116,0,0}{+15.09}}$ |
| XCLIP-B-FT    | Video           | ACC    | 82.14 | 99.57 | 93.62 | 61.29   | 79.36 | 69.71  | 97.92 | 99.79   | 77.14       | 83.59       | 98.14 | 85.66  |
|               |                 | AP     | 64.42 | 99.73 | 96.78 | 70.98   | 90.35 | 77.28  | 97.34 | 99.84   | 82.01       | 88.97       | -     | 86.77  |
| DeMamba-XCLIP-FT| Video         | ACC    | 98.21 | 100.00| 99.86 | 65.43   | 94.86 | 98.86  | 100.00| 100.00  | 92.86       | 89.09       | 99.42 | $\textbf{94.42}_{\textcolor[RGB]{116,0,0}{+8.76}}$ |
|               |                 | AP     | 93.32 | 100.00| 99.97 | 85.55   | 98.97 | 99.60  | 99.98 | 100.00  | 97.77       | 95.75       | -     | $\textbf{97.10}_{\textcolor[RGB]{116,0,0}{+10.43}}$|



### One-to-many generalization task



## Contact
