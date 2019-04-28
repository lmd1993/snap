GET EMBEDDING:
-------------
To get embedding. Compile with make command.
To use different boosting vector, edit the file /snap/snap-adv/word2vec.cpp comment by mingda.
 // mingda threshold 3
        if (Label == 0){
          Grad = Grad * 1; // no boosting factor
//          Grad = Grad * 3; // boosting factor 3
        }
Then, make clean. make. 
You will get the node2vec executable file. snap/examples/node2vec/node2vec

To run the embedding, command:
./node2vec -i:edges1 -o:embedding -l:3 -d:24 -p:0.3 -dr -v
./node2vecNoBoost -i:edges1 -o:embeddingNoBoost -l:3 -d:24 -p:0.3 -dr -v
./node2vecBoost3 -i:edges1 -o:embeddingBoost3 -l:3 -d:24 -p:0.3 -dr -v




AFTER GETTING THE EMBEDDING:
---------------------------
This directory is from https://github.com/phanein/deepwalk/tree/master/example_graphs
Usage of the directory:
python example_graphs/scoring.py --emb example_graphs/blogcatalog.embeddings
--network example_graphs/blogcatalog.mat
--num-shuffle 10 --all

where the embedding of blogcatalog can be got from node2vec stanford's directory.
File:
edges1 is from http://socialcomputing.asu.edu/datasets/BlogCatalog3 used for node2vec training
while the .mat is from http://leitang.net/social_dimension.html
Both is different forms of BlogCatalog data of 10,312 nodes, 333, 983 links, and 39 categories. 


if you want to get the edge from the matlab file .mat, you can try:
from scipy.io import loadmat
matfile = "blogcatalog.mat"
mat = loadmat(matfile)
A = mat['network']
labels_matrix = mat['group']
print(A)
print(labels_matrix)

You will find A is the edge list (-1 for each node number and similar to the label)
