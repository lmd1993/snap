This directory is from https://github.com/phanein/deepwalk/tree/master/example_graphs
Usage of the directory:
python example_graphs/scoring.py --emb example_graphs/blogcatalog.embeddings
--network example_graphs/blogcatalog.mat
--num-shuffle 10 --all

where the embedding of blogcatalog can be got from node2vec stanford's directory.
File:
edges1 is from http://socialcomputing.asu.edu/datasets/BlogCatalog3 used for node2vec training
while the .bat is from http://leitang.net/social_dimension.html
Both is different forms of BlogCatalog data of 10,312 nodes, 333, 983 links, and 39 categories. 
