# Assessing the Reliability of Shape and Color Features for Swedish Tree Leaf Species Characterization

Final project for STA 160 (Practice in Data Science) at UC Davis, prepared for Dr. Hsieh, June 2026.

## Research Question
To what degree do shape and color features extracted from scanned leaf images capture consistent within-species visual identity across Swedish tree species, and what do patterns of within-species consistency and between-species distance reveal about the reliability of image-based leaf characterization?

## Data
[Swedish Leaf Dataset](https://www.cvl.isy.liu.se/en/research/datasets/swedish-leaf/) (Söderkvist, 2001), Computer Vision Laboratory, Linköping University: 1,125 scanned leaf images across 15 species. This analysis uses **10 species × 10 images = 100 images**.

## Methods
- **Preprocessing:** background removal and binary segmentation of scanned leaf images
- **Shape features:** size, compactness, aspect ratio, margin complexity, and symmetry extracted from leaf outlines
- **Color features:** mean and standard deviation of RGB and HSV channels on the leaf surface
- **Evaluation:** within-species consistency (standard deviations), feature effectiveness (coefficient of variation), and pairwise between-species distances

## Key Findings
- **Compactness (CV 130.51%)**, **aspect ratio (CV 56.13%)**, and **Mean Blue channel (CV 42.28%)** were the most discriminating features
- *Betula pubescens*, *Populus tremula*, and *Sorbus aucuparia* were the most reliably characterized species
- *Ulmus glabra* and *Quercus* were the most separable pair; *Alnus incana* and *Salix aurita* were the least separable
- Mean Hue and Mean Saturation were the least discriminating features, consistent with color's sensitivity to imaging conditions

## Limitations & Next Steps
Threshold selection by visual inspection (Otsu's method could improve consistency), symmetry approximated by bounding-box midpoint, 10 of 75 images per species used, and no vein-structure features. Vein analysis is the most promising way to separate the closest species pairs.

## Tools
R (EBImage, magick, ggplot2, fmsb, kableExtra), R Markdown

## Files
- `leaf_species_characterization.Rmd`: full analysis code
- `leaf_species_characterization.pdf`: final report with all figures

## Author
Oscar Abarca · [LinkedIn](https://www.linkedin.com/in/oscar-abarca-09a384279)
