# Article Summary: The Women's Names in Ancient China

> **Original article (in Chinese):** [WeChat Article](https://mp.weixin.qq.com/s/RdEKaUdwB51W1mP4QlPahg)
> **Author:** Liu, Felix | **Impact:** 70,000+ reads, 6,000+ likes by Dec 2023

## Overview

This article presents a data-driven investigation into the naming patterns of women in imperial China, based on extensive analysis of the **China Biographical Database (CBDB)** — a collaborative project between Harvard University and Academia Sinica containing over 500,000 biographical records of historical Chinese figures. After considerable data cleaning of non-standardized and messy raw records, the author uncovered revealing patterns about how women were named, identified, and remembered (or forgotten) across Chinese history.

## Key Findings

### 1. Very Few Women's Names Were Preserved

The most striking finding is the **extreme scarcity of preserved female names** in the historical record. While CBDB contains hundreds of thousands of biographical entries, the vast majority of female figures are recorded without personal names. Instead, women were typically documented only through relational identifiers:

- **Maiden surname** (e.g., "Wang-shi" / 王氏 — "woman of the Wang clan")
- **Husband's surname** (identified through marriage)
- **Kinship titles** (e.g., "daughter of X," "wife of Y," "mother of Z")
- **Numbered designations** (e.g., "Zhao Ji's daughter #3")

In the data cleaning process, entries where names were recorded as "某" (someone), "某某" (so-and-so), or "氏" (clan woman) were flagged as effectively unnamed — revealing that a large proportion of women in the database had no personal name on record at all.

### 2. Women's Names Reflect Male Expectations of Their Era

The specific connotations embedded in women's names across different historical periods mirror what the male-dominated society valued and expected from women at the time. Naming patterns shifted with cultural and political changes across dynasties:

- **Han Dynasty (206 BCE–220 CE):** Female names were relatively gender-neutral, often indistinguishable from male names. The character "君" (lord/gentleman) was popular for women.
- **Tang Dynasty (618–907):** Naming became more expressive and individualistic. Reduplicated characters (叠字) were fashionable. Buddhist influence led to multi-character and unconventional names.
- **Song Dynasty (960–1279):** The tradition of reduplication continued, but official historical records dramatically reduced the documentation of women's personal names. From the late Tang onward, as chastity ideology intensified, women increasingly appeared in records only as "so-and-so-shi" (某氏).
- **Ming-Qing (1368–1912):** A clear class divide emerged — educated women (才女) bore elegant, literary names devoid of feminine stereotypes, while names of concubines and servants remained stereotypically feminine.

### 3. Kinship Networks Reveal Systemic Erasure

Through network analysis of imperial family trees, the article visualizes how women appear (or fail to appear) in kinship structures. The visualizations use **blue nodes for males** and **pink/red nodes for females**, with solid lines for generational relationships and dashed lines for marriage connections.

## Key Visualizations

### Song Dynasty Imperial Kinship Network

The network graph of the Song Dynasty imperial family, centered on founder **Zhao Kuangyin (趙匡胤)**, illustrates the overwhelming dominance of male nodes (blue) versus the sparse scattering of female nodes (pink). Women appear primarily at the periphery, connected through marriage rather than descent.

![Song Dynasty Kinship Network](plot/song_net.png)

### Emperor Huizong's Daughters — Named by Number, Not by Name

One of the most powerful visualizations shows the daughters of **Song Emperor Huizong (趙佶)**. He had at least 34 daughters — yet not a single one is recorded with a personal name. Every daughter is labeled only as "趙氏(趙佶女N)" — meaning "Zhao clan woman (Zhao Ji's daughter #N)." They are literally identified by number, not by name.

![Song Emperor Huizong's Daughters](plot/song_ji_circle.png)

### Tang Dynasty Network with Wu Zetian

The Tang Dynasty kinship network highlights **Wu Zetian (武曌/武則天)** — China's only female emperor — as a notable red node in a sea of blue. Her prominence in the network is exceptional and underscores how rare it was for a woman to achieve independent historical recognition.

![Tang Dynasty Network — Wu Zetian Highlighted](plot/tang_wzt.png)

### Lanling Xiao Family Tree

The tree-structured visualization of the **Lanling Xiao (蘭陵蕭)** family from the Northern and Southern Dynasties period shows a multi-generational lineage. The near-total absence of pink nodes across the family tree visually demonstrates how thoroughly women were excluded from genealogical records — labeled only with named female family members appearing as rare exceptions.

![Lanling Xiao Family Tree](plot/family_xiao.png)

### Song Dynasty Full Family Tree

The full tree visualization of the Song imperial family spans many generations, from ancestor **Zhao Tiao (趙朓)** through the dynasty's entire lineage. The sheer scale of blue-dominated branches, with pink nodes appearing only as marriage connections at the edges, makes the gender imbalance in historical documentation viscerally apparent.

![Song Dynasty Full Family Tree](plot/song_tree2.png)

## Methodology

The analysis was built using **R** and the following pipeline:

1. **Data extraction** from the CBDB SQLite database (tables: `BIOG_MAIN`, `KIN_DATA`, `KINSHIP_CODES`, `DYNASTIES`, etc.)
2. **Data cleaning** — removing parenthetical annotations, filtering out placeholder names ("某", "氏"), and classifying records by gender (`c_female` field) and dynasty
3. **Kinship network construction** — traversing descendant (dwnstep), marriage (marstep), and collateral (colstep) relationships to build complete family graphs
4. **Network visualization** — using `igraph` and `ggraph` with the Kamada-Kawai (KK) layout for network graphs and tree algorithms for hierarchical views

Specific imperial families analyzed include:
- **Zhao (趙)** — Song Dynasty imperial line (Zhao Kuangyin)
- **Li (李)** — Tang Dynasty imperial line
- **Xiao (蕭)** — Lanling Xiao family (Northern/Southern Dynasties)
- **Wang (王)** — Langya Wang family (Tang Dynasty nobility)
- **Zhu (朱)** — Ming Dynasty imperial line (Zhu Yuanzhang)

## Reader Impact

The article resonated deeply with readers. In the comments section, many shared that they had **never thought to ask about their own grandmothers' names** before reading this piece. One particularly memorable comment told the story of a grandmother who was never given a name as a child. When the People's Republic of China was established and household registration required personal names, her father wanted to name her **"Shuxing" (淑行, meaning "dutiful behavior")** — but the grandmother, despite limited education, insisted on naming herself **"Peiying" (佩英, meaning "heroic")**.

These personal stories made the extensive and tedious data cleaning process feel worthwhile to the author.

## Data Source

**China Biographical Database (CBDB)** — a freely accessible relational database maintained by Harvard University's Fairbank Center for Chinese Studies and Academia Sinica, containing biographical information on over 500,000 individuals from the 7th through 19th centuries.

---

*Based on the original WeChat article by Liu, Felix — [Read the full article in Chinese](https://mp.weixin.qq.com/s/RdEKaUdwB51W1mP4QlPahg)*
