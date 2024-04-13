# 9/11 HIJACKERS - Social Network Analysis

This study aims to explore and analyze the dataset of the terrorists involved in the 9/11 bombing of the World Trade Centres in 2001 [provided by UCINET Software](https://sites.google.com/site/ucinetsoftware/datasets/covert-networks/911-hijackers?authuser=0) in order to unravel any relational patterns and information on the subjects present in the dataset itself.

<h3>Preprocessing</h3>
First of all, the two main datasets, the 1-mode matrix 61 x 61 of associates and the list of attributes, were merged together in order to have a single useful dataset with all the associates and the relevant attributes for our work. We then noticed that some more organization and filtering on the dataset was needed, in particular:

- double quotes were removed from a contact as they did not allow correct execution;
- a contact was found with an arc retracting on itself which was not correct, so the arc was changed (he was basically an associate of himself);
- there was a contact, Tarek Maroufi, with a duplicate entry in the dataset so one occurrence was removed;
- since we have an undirected graph, we need to have a mirrored (adjacency) matrix across the diagonal (symmetric adjacency matrix). The nodes in the dataset that had arcs to other nodes but did not have the corresponding reversed arc were corrected through the use of a function.

<h3>Applied measures</h3>
The main purpose of our work is to highlight any possible relationship along with the importance and the role of each individual. To do this we have used several centrality measures along with other metrics useful to understand communities and interesting group of nodes. These measures revealed as expected a strictly connected network and serve to identify key actors based on their influence, connectivity, and bridging roles. We can also uncover potential functional roles of isolated subgroups. The metrics and social network analysis measures we employed in this study are:

- Degree centrality;
- Closeness centrality;
- Betweenness centrality;
- Eigenvector centrality;
- Assortativity;
- Modularity and communities;
- Group of nodes (K-components Cliques).

<h3>Results analysis</h3>
First of all we built an undirected and unweighted graph in which each edge between two nodes represents a relationship ranging from "at school with" to "lived together". Since using the full names of the subjects as the label of each node was inconvenient given their excessive length, we replaced them with an acronym made up of the initials of the name (plus middle name if present) and surname (see Appendix). 


![graph](https://github.com/LucaSpadoni/9-11-Hijackers-Social-Network-Analysis/blob/main/imgs/graph.png)

<h4>Degree centrality</h4>

![degree](https://github.com/LucaSpadoni/9-11-Hijackers-Social-Network-Analysis/blob/main/imgs/degree.png)

The two nodes with the highest value are Mohamed Atta (MA1) and Marwan Al- Shehhi (MAS), suggesting that they had an important role in attack. Comparing the results with official sources we know that both were central in the hijackings being two of the four pilots in the incidents: Mohamed Atta in particular, was also recognized to be the leader of the 19 hijackers involved in the attack. They both participated in the logistical planning of the attacks through numerous meetings with other members of Al-Qaida, in the United States and Spain.

<h4>Closeness centrality</h4>

![closeness](https://github.com/LucaSpadoni/9-11-Hijackers-Social-Network-Analysis/blob/main/imgs/closeness.png)

Observing the top 5 nodes by closeness centrality, we immediately recognized the first two, MA1 and MAS, already mentioned before and which we know them to be two pilots and central figures. We then have Ziad Jarrah (ZJ) who we know to be the third pilot and one of MA1’s right-hand men. The last two notable nodes we considered, Lofti Raissi (LR) and Ramzi Bin al-Shibh (RBAS), do not belong to the pilot group but still hada relevant position and role among the network.

<h4>Betweenness centrality</h4>

![betweenness](https://github.com/LucaSpadoni/9-11-Hijackers-Social-Network-Analysis/blob/main/imgs/betweenness.png)

We can then say that MA1 acts as critical intermediary, playing a key role as a gateway or a bridge between different clusters or groups within the network, facilitating communication and influencing the overall dynamics of the network. It is interesting to see that the second node wrt betweenness centrality is Essid Sami Ben Khemail (ESBK). We can in fact observe in teh first graph that he acts as a bridge between Mohamed Atta (and all the central part of the graph connected to it) and a pretty much isolated subgroup of nodes. As a matter of fact ESBK was the head of al-Qaeda’s Italian cell (Italian branch of the Tunisian Combatant Group) until his arrest outside Milan in April 2001. He is believed to be the founder of the Tunisian Combatant Group (TGC) along with Seifallah Ben Hassine (SBH) and Tarek Maaroufi (TM), leader of the belgian branch of the group. TCG is believed to have had terrorist cells in France, Italy, Belgium, Luxembourg, the Netherlands and in the United Kingdom. The last individual we would like to analyse is Zakariyya Musawi (ZM), which has the fourth highest value of betweenness centrality. As we can see from our network graph he acts as a bridge between the network core (Mohamed Atta and Ramzi Bin al-Shibh) and an isolated subgroup. He was in fact the head of an European cell. This group was organizing bomb attacks in Europe in 2001: in particular Djamel Beghal (DB), Kamel Daoudi (KD), Jérôme Courtailler (JC) and Nizar Trabelsi (NT), the leader of an Al-Qaida cell in Brussels, planned to detonate a bomb along with them in the U.S. Embassy in Paris. During his trial Beghal also said that Abu Zubaydah (AZ), a close associate of Osama bin Laden, had ordered the attack. Courtailler was arrested and held in the Netherlands and earlier stayed at Musawi’s apartment.

<h4>Eigenvector centrality</h4>

![eigenvector](https://github.com/LucaSpadoni/9-11-Hijackers-Social-Network-Analysis/blob/main/imgs/eigenvector.png)

Analyzing the chart it is interesting to highlight that among the 10 terrorists displayed, we can find all the members of the so called "Hamburg cell", in order: the leader Mohamed Atta (MA1), the two pilots and right-hand men Marwan al-Shehhi (MAS) and Ziad Jarrah (ZJ), Ramzi bin al-Shibh (RBAS) who conspired with the other three members but was unable to enter the United States, Sa’id Bahaji (SB) who was an electrical engineer who provided money and material support to the hijackers, Zakariya Essabar (ZE) and Munir al-Mutasaddiq (MEM). The only member who is not present in the chart and also in the dataset is Abd al-Ghani Mzudi (Muzawdi) but it could be possible that it was reported with a false ID. Notably all of them are at the center of the network graph.

<h4>Assortativity</h4>

In this case we got an assortativity value of -0.14114486162935388. The close-to-zero and negative degree assortativity coefficient suggests a relatively weak or moderate disassortative mixing pattern based on node degree in the 9/11 hijackers network. In other words, the coefficient indicates that while there is a disassortative tendency based on node degree, it is not extremely pronounced. Nodes with different degrees are somewhat more likely to connect (heterophily), but the effect is not overwhelmingly strong (creating star-like features in the network which are not readily visible).

<h4>Modularity and communities</h4>

![communities](https://github.com/LucaSpadoni/9-11-Hijackers-Social-Network-Analysis/blob/main/imgs/communities.png)

At first glance, we immediately recognized two known clusters: the red one which, as said while talking about betweenness centrality, is made up of the nodes that are part of the al- Qaeda’s Italian and European cell (Tunisian Combatant Group) led by ESBK and the yellow one which is the other European cell led by ZM. We then took a look at the pink community at the center of the graph where we found all the members of the already mentioned Hamburg cell and other subjects who were very close to the latter.

<h4>K-Components and N-Cliques</h4>

- With k = 3, we found 4 distinct components within our network (subgraphs in which every pair of nodes is connected by at least 3 node-independent paths). The first notable component and definitely the most important one is the core of the network (light blue) which we already noted to be formed by all the members of the "Hamburg cell". Another component of individuals we have already seen before is the bottom left one (light-brown). That is in fact the European cell commanded by Zakariyya Musawi (ZM) who was planning bomb attacks in Europe throughout 2001. A group of associates we have not analyzed yet is the top right component (water green). This group is mainly composed of Abdussattar Shaikh (AS), Khalid al-Mihdhar (KAM) and Nawaf Alhazmi (NA). What makes this component interesting is the fact that AS was a FBI collaborator from 1994 to 2003 and has always been called "The FBI’s Best Chance to Uncover September 11th Before it Happened". The last interesting component of terrorists we have never seen yet is the top one (purple). This small subgroup is formed by Hamza al-Ghamdi (HA), Saeed al-Ghamdi (SA2*) and Ahmed al-Nami (AA1). HA (brother of Ahmed al-Ghamdi (AA2)) and SA2* were both from the Al-Bahah Province in Saudi Arabia. Ahmed al-Nami (AA1) was from the ’Asir Province, a nearby province. While in the United Arab Emirates in late 2000, al-Nami and the two al-Ghamdi (plus some other Saudi terrorists) purchased traveler’s cheques to enter the US in the following year. During the attacks HA was one of the hijackers of the United Airlines flight #175, while SA2* and AA1 were inside the United Airlines flight #93.

![components3](https://github.com/LucaSpadoni/9-11-Hijackers-Social-Network-Analysis/blob/main/imgs/components3.png)

- With k = 5, one single distinct component was found. Again we see that it is equal to the Hamburg cell.

![components5](https://github.com/LucaSpadoni/9-11-Hijackers-Social-Network-Analysis/blob/main/imgs/components5.png)

Analyzing the cliques in our network it is interesting to see that the maximum clique we found is of size n = 6, which is pretty small compared to the rest of the 60-members network. Once again we see that this group of individuals is composed of members of the Hamburg cell, like MA1, MAS, ZJ, RBAS, SB and ZE. This is another proof of the centrality of the cell since the occurrence of a clique in an otherwise sparsely connected network is normally an indication of a highly cohesive subgroup.

<h4>Las Vegas meeting attendance analysis</h4>

![lasvegas](https://github.com/LucaSpadoni/9-11-Hijackers-Social-Network-Analysis/blob/main/imgs/lasvegas.png)

Even nowadays investigators can’t still explain with certainty why several of the terrorists visited Las Vegas before the attacks. It is thought that “most crucial planning” could have taken during this meeting. Another theory supposes that the terrorists came to Las Vegas to scout potential targets, including the Hoover Dam.  Observing the graph above, we noticed that only 6 subjects attended the meeting. We discovered that that all 4 pilots of the hijackings are present: Mohamed Atta (MA1), Marwan Al-Shehhi (MAS), Ziad Jarrah (ZJ) and Hani Hanjour (HH). The last two terrorists present, Nawaf Alhazmi (NA) and Salem Alhazmi (SA1*) were brothers and also hijackers. 

<h3>Appendix</h3>

![mapping](https://github.com/LucaSpadoni/9-11-Hijackers-Social-Network-Analysis/blob/main/imgs/mapping.png)

