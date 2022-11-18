# Location of Outgoing Links on Webpages — Does it Impact on Navigation of Informational Content?
_Prepared by Nils Hasselmark, Hugo Parent-Leduc, Nadia Hadjmbarek and Brahim Rejeb in the context the course CS-401 Applied Data Analytics given in 2022 by Robert West at École Polytechnique Fédérale de Lausanne (ÉPFL), Switzerland._

## Abstract
In website design, the layout of outgoing links within a webpage has major impacts on the user’s behavior. UI designers are fully aware of that, and try as much as possible to  track the user's journey both internally, with tagging plans, and externally, with third party cookies. The project aims to study the specific impact of the location of the outgoing link inside a webpage: 

> _**To what extent does the position of the link within an article have an effect on how often it gets clicked?**_

We investigate wether users always take the time to go through the whole article, cataloging all the links before finally choosing the one they think will bring them closer to their objective.

The premise of this line of questioning is **to evaluate whether there is a correlation between the position of the link on a page and its clickthrough rate**. 


## Research questions
Research questions our project aims to answer include:
-   _Does the position of the link on the page influence the click through rate (CTR)?_
    -   If so, is it possible to quantify this influence?
    
-  _Does the section in which a link is located influence the CTR?_

-   _Is there a relationship between the success or failure of a path with the locations of the links clicked?_
	In the context of the Wikispeedia game, that would mean: _are lazy players who only click on the top links doing a worse score in average?_

- _What is the average position of the links in the shortest paths compared to the average position of the links in the player's paths?_

## Methodology
The main idea is to conduct an analysis at two levels. We plan to compare both globally and locally the influence of the link positions on the CTR. By globally, we mean that we want to investigate wether the links with highest CTR are the ones which appear in average on top of the articles. By locally, it means that we will conduct this analysis at the scale of each source article, to have a higher precision. 

This tackles two different problems and the analysis will return different results and variances:
- The global vision helps understanding if we simply need to put the links going to a given page at the top if we want to increase overall clicks (no matter their source).

- The local vision helps to understand if, for a given page, we want to increase traffic toward a specific article, it helps to put the link on top or not.

### Data pre-processing

-  **Dataset wpcd:**
	For each article and for each outgoing links on the article: 
	- Calculate y-position of the link inside the HTML page, using XXX library
	
	- Determine the section in which the link is located, using XXX
	
	- Store the results in the extended table _links_
	
	- For each destination article, compute the average location of all the links going to this article. Results are stored in the extended _articles_ table.

- **Dataset paths_finished and paths_unfinished:**
For each article and for each outgoing links:
	- Calculate the number of clicks and impressions of the links at a page level, allowing to see from each page, which links are the most clicked on. Store the results in the extended _links_ table
	
	- Calculate the number of clicks and impressions of the links at the global level, allowing to see which articles are the most popular overall. Results are stored in the extended _articles_ table.
	
	- For both cases, compute the CTR as the number of clicks divided by the number of impressions.

### Data modeling
Linear regression will be run at the two levels of granularity.

### Data visualization
XXX


## Proposed timeline


Date 1
: xxx

Date 2
: yyy

Date 3
: zzz




## Organization within the team
### Project Management
- Team meetings are organized at least on a weekly basis. At each meeting, everyone discusses his progresses & difficulties, and the next steps are decided
- Notion is the software used for project follow up

### Split of Work
- Hugo:
- Nils:
- Nadia:
- Brehim:

_Note that this is subject to change._