# 9/11 HIJACKERS - Social Network Analysis

This study aims to explore and analyze the dataset of the terrorists involved in the 9/11 bombing of the World Trade Centres in 2001 [provided by UCINET Software](https://sites.google.com/site/ucinetsoftware/datasets/covert-networks/911-hijackers?authuser=0), in order to unravel any relational patterns and information on the subjects present in the dataset itself.

<h3>Preprocessing</h3>
First of all, the two main datasets, the 1-mode matrix 61 x 61 of associates and the list of attributes, were merged together in order to have a single useful dataset with all the associates and the relevant attributes for our work. We then noticed that some more organization and filtering on the dataset was needed, in particular:

- double quotes were removed from a contact as they did not allow correct execution;
- a contact was found with an arc retracting on itself which was not correct, so the arc was changed (he was basically an associate of himself);
- there was a contact, Tarek Maroufi, with a duplicate entry in the dataset so one occurrence was removed;
- since we have an undirected graph, we need to have a mirrored (adjacency) matrix across the diagonal (symmetric adjacency matrix). The nodes in the dataset that had arcs to other nodes but did not have the corresponding reversed arc were corrected through the use of a function.

<h3>Applied measures</h3>
The main purpose of our work is to highlight any possible relationship along with the importance and the role of each individual. To do this we have used several centrality measures along with other metrics useful to understand communities and interesting group of nodes. These measures revealed as expected a strictly connected network and serve to identify key actors based on their influence, connectivity, and bridging roles. We can also uncover potential functional roles of isolated subgroups. The metrics and social network analysis measures we employed in this study are:
Degree centrality;
- Closeness centrality;
- Betweenness centrality;
- Eigenvector centrality;
- Assortativity;
- Modularity and communities;
- Group of nodes (K-components Cliques).
