##### Lecture 1.3

###### Connectivity

Undirected graph:

- disconnected graph is made of two or more connected components
- adjacency matrix is block-diagonal

Directed Graphs

- strong
  - connectivuty from each node to every other node and vice-versa( from A to B and B to A as well)
- weakly connected 
  -  is connected if we disregard the edge directions

Strongly Connected Components

- every node can be reached from every other node

- Nodes out side the SCC cannot be reached the from the nodes within the SCC

  

##### Lecture 2.1

###### Machine Learning Tasks

- Node level predictions tasks
- link level prediction task
- graph level prediction task

##### Traditional ML Pipeline

Designing proper features for nodes/links/graphs

**Two types of features:**

- Assuming nodes have some sort of attributes associated with them for eg if it is a protein-protein interaction network then proteins have different chemical properties, different structures etc then this can be as the attributes attached to the nodes of the network

- Additional features how this particular node is positioned within the network and what is its local network structure. This additional features that describe the topology of the graph will allow for more accurate predictions.

in summary i. structural features and ii. feature describing the attributes and properties of the nodes

 **Two steps in Traditinal ML pipelines:**

- Take data points i.e. nodes/links/graphs and represent them with vectors of features
- then train a classical ML model like SVM, Random Forest, NN etc
- Apply  the model to a new node/link/graph's feature s to make a prediction

##### Feature Design

