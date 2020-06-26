---
layout: post
title: "Build a Lo-Fi Cannabis Strain Recommendation System with Python"
author: "Alex Pakalniskis"
categories: journal
tags: [cannabis, recommendation, strain, nearest neighbors, euclidean distance, jaccard index, data science, python, pandas, scipy, scikit-learn]
image: cannabis.jpg 

---

The suggestions for your next favorite playlist, bingeworthy show, or late-night e-commerce splurge are largely powered by recommendation systems<sup>[1](https://en.wikipedia.org/wiki/Recommender_system)</sup>. Tech companies like Google, Amazon, Twitter, and Netflix make use of recommendation systems to tailor content and product suggestions to the user<sup>[2](https://aisel.aisnet.org/cgi/viewcontent.cgi?article=1146&context=icis2004)</sup>, i.e. you and me. However, the ethics of recommendation systems remains a contentious topic<sup>[3](https://link.springer.com/chapter/10.1007/978-3-642-13226-1_10),[4](https://www.usenix.org/system/files/conference/soups2014/soups14-paper-zhang.pdf)</sup>. 

Despite on-going debates, innovations in recommendation algorithms remains a top research priority<sup>[5](https://link.springer.com/article/10.1007/s12652-018-0928-7),[6](https://www.sciencedirect.com/science/article/pii/S0167923618301970),[7](https://ieeexplore.ieee.org/abstract/document/8616805)</sup>. While more sophisticated methods are regularly developed, the k-Nearest Neighbors<sup>[8](https://en.wikipedia.org/wiki/K-nearest_neighbors_algorithm)</sup> algorithm remains a foundational machine learning technique which can be applied to drive a basic recommendation system<sup>[9](https://www.sciencedirect.com/science/article/pii/S221083271400026X)</sup>. The remainder of this post will describe how to build a k-Nearest Neighbors-powered Cannabis strain recommendation system using Python 3<sup>[10](https://en.wikipedia.org/wiki/Python_(programming_language))</sup>.

## Methods
### Cannabis Strain Data
![strain wheel](https://resize.mantisadnetwork.com/mantis-ad-network/image/fetch/w_500,q_75,c_limit,f_jpg/http://uploads.medicaljane.com/wp-content/uploads/2016/06/flavorwheel.png)
Medicinal and recreational cannabis legislation are slowly gaining approval across US states. While cannabis remains illegal (and punishable by imprisonment) at the federal-level, many state cannabis industries are booming<sup>[11](https://www.ocregister.com/2020/03/10/california-passes-1-billion-in-cannabis-tax-revenue-two-years-after-launching-legal-market/)</sup>. To meet the growing demand for consumers and retailers, cannabis tech companies such as Weedmaps<sup>[12](https://weedmaps.com/)</sup> and Leafly<sup>[13](https://www.leafly.com/)</sup> provide information services related to cannabis strains and products, and dispensary inventory. While many services are proprietary, much of this cannabis data is publically available through web APIs<sup>[14](https://en.wikipedia.org/wiki/Web_API)</sup>. For education purposes only, cannabis strain data were scraped from the Weedmaps Cannabis Strain API<sup>[15](https://api-g.weedmaps.com/wm/v1/strains)</sup> in early May 2020. The Weedmaps data set contains over 50 flavor and effect attributes (boolean features) for more than 300 cannabis strains. A helper class was written to facilitate the scraping process and another class for processing the API JSON data into a machine learning-friendly CSV format. Code to replicate the scraping and data cleaning process is available on GitHub<sup>[16](https://github.com/Build-Week-Med-Cabinet-2-MP/bw-med-cabinet-2-ml/tree/master/code)</sup>.

### Simulating User Preference Inputs
![user input](https://public-media.interaction-design.org/images/ux-daily/56e2cfdabdb9e.jpg)
User preference for cannabis strain flavors and effects were simulated using the numpy array manipulation library<sup>[17](https://numpy.org/)</sup>. A random seed was set for reproducibility. See `examples` for the full code implementation<sup>[18](https://github.com/alex-pakalniskis/NearestNeighbors/tree/master/examples)</sup>.

### k-Nearest Neighbors Algorithm
![knn](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e7/KnnClassification.svg/200px-KnnClassification.svg.png)

The k-Nearest Neighbor algorithm utilizes an analyst-supplied distance metrics to calculate the nearest (or most similar) data points to a given input. Distance is calculated in an n-dimensional hyperspace formed by the data attributes being analyzed. Furthermore, selection of a suitable distance metric often depends on the type of data under inspection. For this cannabis strain example, the k-Nearest Neighbors model will be used to return the k-most similar (nearest) strains to the simulated user preference inputs for flavor and effects.

A common choice for Nearest Neighbors metric is Euclidean distance, most suited for numeric attributes. Mathematically, the euclidean distance in n-dimensions for points p, q with i features is as follows:

$$d(\textbf{p,q}) = \sqrt{\sum_{i=1}^{n} (p_{i} - q_{i})^2}$$

The cannabis strain data is not optimally suited for euclidean distance as strain attributes are stored as booleans. A more appropriate distance metric for this example would be the Jaccard index. Mathematically, the Jaccard index for p, q is:

$$J(\textbf{p,q}) = \frac{\vert{p\cap{q}}\vert}{\vert{p}\vert + \vert{q}\vert - \vert{p\cap{q}}\vert}$$ 


## Results and Discussion
My implementation
Include code chunks

Scikit-learn implementation
Include code chunks

## Conclusion
Brief closing thoughts
