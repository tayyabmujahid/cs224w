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

  

### Lecture 2.1

#### Machine Learning Tasks

- Node level predictions tasks
- link level prediction task
- graph level prediction task

#### Traditional ML Pipeline



 ##### Steps in Traditional ML pipelines

**A. Feature Design**

- Take data points i.e. nodes/links/graphs and represent them with vectors of features

Designing proper features for nodes/links/graphs

**Two types of features:**

- Assuming nodes have some sort of attributes associated with them for eg if it is a protein-protein interaction network then proteins have different chemical properties, different structures etc then this can be as the attributes attached to the nodes of the network

- Additional features how this particular node is positioned within the network and what is its local network structure. This additional features that describe the topology of the graph will allow for more accurate predictions.

in summary i. structural features and ii. feature describing the attributes and properties of the nodes



**B. Train a classical ML model **

like SVM, Random Forest, ANN etc on the nodes/links/graphs (objects converted to feature vectors)

**C. Inference:** 

Apply  the model to a new node/link/graph's features to make a prediction

##### A. Feature Design

Goal : how to make the predictions for a set of objects

Design Choices: 

- Features: *d*- dimensional vectors
- Objects: Nodes,edges sets of nodes or entire graphs
- Objective function:
  - depending on the task

Problem Formulation:

Given : $G = (V,E)$ 

Learn a function : $f:V \rightarrow \mathbb{R} $

​	

