# Identification and Impact of Sockpuppets in Wikipedia
This repository contains the code and data-processing pipeline for a research project investigating sockpuppets in Wikipedia discussions through graph-based analysis.

The project focuses on Hebrew Wikipedia and examines whether discussions involving sockpuppets exhibit structural or behavioral differences from discussions without sockpuppets.

## Overview
Wikipedia discussions can be represented as interaction networks, where:

* Nodes represent Wikipedia users.
* Directed edges represent replies between users.
* Edge weights can represent the number or strength of interactions between users.

Using these graphs, we calculate a variety of network metrics and investigate whether they differ between discussions containing different types of users.
The project considers three primary user categories:

* Regular users
* Puppet masters — users associated with operating sockpuppet accounts
* Sockpuppets — accounts identified as sockpuppets

The analysis is intended to explore whether the presence and behavior of these users can be reflected in the structure of Wikipedia discussion networks.

## Research Questions
The project investigates questions such as:

* Can discussions containing sockpuppets be distinguished from ordinary discussions based on their graph structure?
* Do puppet masters and sockpuppets exhibit different interaction patterns from regular users?
* Which network characteristics are most strongly associated with discussions involving sockpuppets?
* How do users from different user groups behave differently within discussion networks?

## Data Collection
The data was collected from Hebrew Wikipedia using the MediaWiki API and HTML parsing via BeautifulSoup.

The data was gathered by parsing an established table provided by the Hebrew Wikipedia that contains a list of identified puppet masters and their documented sockpuppets.
We used this information to collect discussions using the MediaWiki API from the relevant accounts and to classify users as puppet masters, sockpuppets, and regular users.

## Graph Construction
Each discussion is represented as a directed graph.
For example, if user A replies to user B, the interaction can be represented as:

A → B

The resulting graphs are analyzed using NetworkX.

Depending on the analysis, graphs may also be transformed or reversed so that particular graph-theoretic and probabilistic measures can be calculated relative to the discussion structure.

## Network Metrics
The project investigates a range of graph-based metrics, including:

* PageRank
* Degree and degree centrality
* Betweenness centrality
* Closeness centrality
* Reciprocity
* Density
* Diameter
* Clustering coefficient
* Eigenvector centrality
* Higher-order Markov-chain-based measures

These metrics are used to characterize both entire discussion graphs and individual users within those graphs.

## Statistical Analysis
The extracted network metrics are compared between different user and discussion groups.

The statistical analysis makes use of:

* Mann–Whitney U tests for comparing distributions between groups
* Cohen's d for measuring effect sizes
* Visualizations such as violin plots and ECDF plots created using Matplotlib and Seaborn

Because individual users may appear in multiple discussion graphs, user-level analyses can aggregate a user's metric values across their appearances before comparing groups. This helps ensure that users who appear more frequently do not disproportionately influence the analysis.

## Technologies
* Python
* Google Colab
* MediaWiki API
* NetworkX
* BeautifulSoup
* SciPy
* Matplotlib and Seaborn - for visualizations

## Results
The raw results of the project are contained within the `.ipynb` project notebook. Our conclusions and analysis are contained within our project report document. It will be uploaded with the approval of the project supervisor.

## LLM Assistance
We used ChatGPT, Gemini, and Claude to assist with generating parts of the code. All generated code was reviewed, modified where necessary, and implemented by the authors.

## Authors
Lidor Lutati - [GitHub: LL37477](https://github.com/LL37477)
Haim Bortman - [GitHub: hb9111](https://github.com/hb9111)
