# Women's Name Analysis

> **[Article Summary (English)](SUMMARY.md)** — A comprehensive English summary of the original WeChat article, including key findings and visualizations.

Analysis of female naming patterns in imperial China using kinship network data, exploring how women were named, referenced, and remembered throughout Chinese history.

## Overview

This project analyzes naming conventions for women in imperial China:
- Character usage in female names
- Temporal trends in naming patterns
- Regional variations in naming customs
- Relationship between names and social status
- Kinship-based naming references

## Project Structure

```
womens-name-analysis/
├── main/           # Analysis scripts
│   ├── main.R                   # Main analysis pipeline
│   ├── kin_clean.R              # Kinship data cleaning
│   └── kin_plot.R               # Network visualization
├── plot/           # Generated visualizations
│   ├── song_tree2.png          # Song dynasty kinship tree
│   ├── tang_net.png            # Tang dynasty networks
│   ├── song_net.png            # Song dynasty networks
│   └── dynasty_*.png           # Dynasty-specific analyses
└── README.md       # This file
```

## Research Questions

1. **Naming Conventions**: What naming patterns were used for women?
2. **Character Analysis**: Which characters were commonly used in female names?
3. **Temporal Trends**: How did naming practices change across dynasties?
4. **Status Indicators**: Did names reflect social status?
5. **Kinship References**: How were women identified through family relationships?

## Background

In imperial China, women were often identified through:
- Maiden surname (e.g., Wang氏)
- Husband's surname (e.g., married to Li)
- Personal names (less common, especially in earlier periods)
- Kinship titles (daughter of, wife of, mother of)

This analysis explores these patterns using CBDB kinship data.

## Requirements

- R (>= 4.0)
- Required R packages:
  - `tidyverse`
  - `igraph` (for network analysis)
  - `ggraph` (for network visualization)
  - `ggplot2`
  - `stringr`

## Installation

```r
install.packages(c("tidyverse", "igraph", "ggraph", "ggplot2", "stringr"))
```

## Usage

### Running the Analysis

```r
# Clean kinship data
source("main/kin_clean.R")

# Run main analysis
source("main/main.R")

# Generate network visualizations
source("main/kin_plot.R")
```

## Analysis Components

### 1. Name Character Analysis
- Frequency of characters in female names
- Character meaning and connotations
- Temporal trends in character usage

### 2. Kinship Network Analysis
- Family relationship structures
- How women are positioned in kinship networks
- Network centrality and importance

### 3. Dynasty-Specific Patterns
- Tang Dynasty (618-907): Early patterns
- Song Dynasty (960-1279): Peak of literary culture
- Ming-Qing (1368-1912): Later developments

### 4. Visualization
- Kinship network graphs
- Character frequency distributions
- Timeline visualizations

## Key Visualizations

The project generates several network visualizations:
- **song_tree2.png**: Song dynasty kinship tree structure
- **tang_net.png**: Tang dynasty kinship networks
- **song_net.png**: Song dynasty network analysis
- **dynasty_*.png**: Dynasty-specific visualizations

## Related Projects

This analysis is closely related to:
- **cbdb-women-analysis**: Broader analysis of women in CBDB
- **womens-name-analysis**: Focuses specifically on naming patterns

## Data Source

Data derived from the **China Biographical Database (CBDB)**
- Kinship relationship records
- Biographical information
- Name records

## Author

**Liu, Felix**
Email: wfliu127@gmail.com

## Citation

```
Liu, F. (2026). Women's Name Analysis: Naming Patterns and Kinship
References in Imperial China.
```

## License

MIT License

## Acknowledgments

This research uses data from the China Biographical Database (CBDB), a collaborative project of Harvard University and Academia Sinica.

---

*Last updated: 2026-02-09*
