# 9/11 HIJACKERS - Social Network Analysis

This study aims to explore and analyze the dataset of the terrorists involved in the 9/11 bombing of the World Trade Centres in 2001 [provided by UCINET Software](https://sites.google.com/site/ucinetsoftware/datasets/covert-networks/911-hijackers?authuser=0), in order to unravel any relational patterns and information on the subjects present in the dataset itself.

<h3>Preprocessing</h3>
First of all, the two main datasets, the 1-mode matrix 61 x 61 of associates and the list of attributes, were merged together in order to have a single useful dataset with all the associates and the relevant attributes for our work. We then noticed that some more organization and filtering on the dataset was needed, in particular:

• double quotes were removed from a contact as they did not allow correct execution;

• a contact was found with an arc retracting on itself which was not correct, so the arc was changed (he was basically an associate of himself);

• there was a contact, Tarek Maroufi, with a duplicate entry in the dataset so one occurrence was removed;

• since we have an undirected graph, we need to have a mirrored (adjacency) matrix across the diagonal (symmetric adjacency matrix). The nodes in the dataset that had arcs to other nodes but did not have the corresponding reversed arc were corrected through the use of a function.
