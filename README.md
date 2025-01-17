# HubAlign
The program HubAlign finds a global alignment between a pair of networks. Given two networks with N and M nodes, it returns min(N,M) pairs, which each pair indicates two aligned nodes from two networks. 

###########################

How to run HubAlign:

•	Suppose two input networks are named ‘Test1.tab’ and ‘Test2.tab’, which are tab separated files where each line contains an interaction. Number of nodes in the first network must be smaller than the Number of nodes in the second Network.

•	Run the HubAlign. Here is a sample invocation:

./HubAlign Test1.tab Test2.tab –l 0.1 –a 0.7 –d 10 –b similarityFile.txt

The options are as fallows:
 
-l : The parameter  λ that controls the importance of the edge weight relative to the node weight. Usually λ=0.1 yields a biologically more meaningful alignment. Default value is equal to 0.1.

-a :  the parameter α   that controls the contribution of sequence information relative to topological similarity. Default value for this parameter is equal to 0.7.  α=1 implies that only topological information is used.

-d : the parameter d that controls the number of nodes removed from network in the process of making the skeleton.

-b : similarity file that  includes the sequence information of proteins.  Here, we used Blast bitscores. The similarity file is a tab-separated file with three columns where each line is in form: 
<id1>		<id2> 		<bitscore>

<bitscore> is the bitscore between two proteins <id1> and <id2> . You don’t need this file if α=1. Here is a sample invocation when α=1:

./HubAlign Test1.tab Test2.tab –l 0.1 –a 1 

- i : input directory - path to a directory where networks files are located
- o : output directory - path to the directory where HubAlign should store the alignment result files

#############################

Analyze the output

For two input networks ‘Test1.tab’ and ‘Test2.tab’, HubAlign produces two output files:

1.	Test1-Test2.alignment
2.	Test1-Test2.eval

File ‘*.alignment’  is a tab separated file in which each line  indicates the matching pair of nodes from two networks. File ‘*.eval’ includes EC, S3 and LCCS (both node and edge) of the alignment.  

##############################
If you use HubAlign, please cite this paper:

Hashemifar, Somaye, and Jinbo Xu. "HubAlign: an accurate and efficient method for global alignment of protein–protein interaction networks." Bioinformatics 30.17 (2014): i438-i444.

If you have any questions or if you have found any problem in the software, please email Hashemifar@ttic.edu. For the latest updates, please visit http://ttic.uchicago.edu/~hashemifar/



