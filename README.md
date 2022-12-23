
# Understanding what makes a link popular within an article

_Prepared by Nils Hasselmark, Hugo Parent-Leduc, Nadia Hadjmbarek and Brahim Rejeb in the context the course CS-401 Applied Data Analysis given in 2022 by Robert West at École Polytechnique Fédérale de Lausanne (EPFL), Switzerland._

  

The notebook is available [here](https://github.com/epfl-ada/ada-2022-project-adaandthelovelaces/blob/main/notebook.ipynb).

  

## Abstract

In website design, the layout of outgoing links within a webpage has major impacts on the user’s behavior. UI designers try as much as possible to track the user's journey both internally, with tagging plans, and externally, with third party cookies, in order to optimize the overall layout. The project aims to understand the role of some factors on the popularity of an article, measured both in terms of number of clicks and of click-through rate.

We investigate whether users always take the time to go through the whole article, cataloging all the links before finally choosing the one they think will bring them closer to their objective. We also analyse if users prefer to target broad articles, or more specific ones with smaller content.

  
  

## Research questions

Research questions our project aims to answer include:

-  _How to best represent the popularity of a link?_

-  _Does the position of the link on the page influence the click through rate (CTR)?_

	- If so, is it possible to quantify this influence?


-  _Do players prefer to target articles covering a general topic or a very specific one?_

 - _Do players prefer to target long or short articles?_


## Additional datasets

No additional datasets were used to perform the analysis.


## Methodology

The main idea is to conduct an analysis at two levels. We plan to compare both globally and locally the influence of the factors on CTR and clicks. For example, by globally, we mean that we want to investigate whether the links with highest CTR are the ones which appear in average on top of the articles. By locally, it means that we will conduct this analysis at the scale of each source article, to have a higher precision.

The factors of interest are:
- the **position** of the link inside a the source article: we try to understand if players take the time to go through the entire article before clicking

- the **outdegree** of the destination article: we try to understand wether players prefer to click on articles which will propose to them many new links opportunities

- the **section** in which the link is located inside the source article. Only a few sections will be considered (for instance the 10 most popular, the last one being: _other_).

- the **length** of the destination article: we try to understand if players prefer to target short or long articles

- the **indegree** of the destination article: we might expect that the most popular articles are the ones which have the higher number of links pointing toward them. By adding this variable in our analysis, we remove a source of bias for the analysis of the other features.

  
  

### Data pre-processing

  

**Dataset links.tsv:**

For each article, compute its ingoing and outgoing degree: the number of links going to the article, or the number of links present in the article.

  

**Dataset wpcd:**

For each article and for each outgoing links on the article:

- Calculate y-position of the link inside the HTML page, using the **Selenium** Python library. 

- For each destination article, compute the average location of all the links going to this article. 

- For each article, compute their degree and the content size (length).

- Calculate the semantic textual similarity between each article and the links that it contains.

  
  

**Dataset paths_finished and paths_unfinished:**

For each article and for each outgoing links:

- Calculate the number of clicks and impressions of the links at a page level, allowing to see from each page, which links are the most clicked on. Store the results in the extended _links_ table. (in progress)


- Calculate the number of clicks and impressions on links at the section level, allowing to see for each section, how many clicks have been generated. 

- Calculate the number of clicks and impressions of the links at the global level, allowing to see which articles are the most popular overall. Results are stored in the extended _articles_ table. 

- For all cases, compute the CTR as the number of clicks divided by the number of impressions. 

  

### Data visualization

Heatmaps are used to highlight the links density, high CTR regions, players' choices.

Histogram plots are used to highlight the distribution of the source articles features: length and semantic similarity score.

### Matched studies

Pair up articles/links based on observed covariates to draw valid conclusions from data. Initial exploration of observed covariates has been conducted in the following PDF: [here](/obs_data_P2.pdf)

From milestone P2, major modifications were brought. Advanced exploration of observed covariates has been exposed in the followng PDF: [here](/obs_data_P3.pdf)


### Data analysis

  

Understand the way players choose the links they click:

- Investigate causation between the position of the link and its clickthrough rate (CTR), case study and draw conclusions. 

- Investigate the most popular sections containing the most clicked links. 

- Investigate whether the most popular articles are the ones with the highest degrees, or not. This will make us understand if players use a strategy to target very broad articles, or very specific ones. (To do)


- Conduct regression analysis on all factors to determine what most influences the clicks and CTR

  

Propose a guideline on how links should be used in Wikipedia.

## Proposed timeline

  

- First two weeks : Preprocess, matching, modeling data

- Third week : Correlate, investigate causation, case study

- Last two weeks : Create data story, visualizations and draw conclusions

  
  

### Organization within the team

- Nils: Wikispeedia network exploration through graphs, Data distribution analysis, Data story

- Brahim: Textual semantic similarity, data visualization, linear regression, Data story

- Hugo: Data pre-processing, CTR computation, Data story

- Nadia: Link position and article length computation, observational study and matching, Data story
### Project Management

- Team meetings are organized at least on a weekly basis. At each meeting, everyone discusses his progresses & difficulties, and the next steps are decided

- Notion is the software used for project follow up


  
