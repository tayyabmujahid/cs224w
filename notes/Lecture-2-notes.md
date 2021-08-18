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

learn a function $f$ that would for example predict the age of each node in a social network

 ###### Node Level Features and Tasks

Semi supervised case:

-  Node Classification : Given a network with  few nodes which are labelled(colors for eg). Given a color of nodes predict the color or the unlabeled (uncolored) node.

- Characterize the structure and position of  a node in the network

  this can be done in the following ways

  - node degree
  - node centrality
  - clustering coefficient
  - graphlets

  **Node Degree** ($k_v$)

  - the degree $k_v$ of a node v is the number of edges(neighbouring nodes) the node has

  - Drawback is that it treats all the neighbours equally 

    nodes with same degree are treated similarly even if they are in different parts of the network

   **Node Centrality** ($c_v$)

  - node degree does not capture a nodes importance 

  - node centrality measures captures how important the node is in the graph

    - <u>*Eigen vector centrality*</u>- page rank algorithm

      a node $v$ is important if surrounded by important neighbours nodes $u$

      $c_v= 1/\lambda \Sigma_{u} c_u \Leftrightarrow \lambda \bold c= \bold A \bold c$     

      where $\bold A$ is the adjacency matrix and $\bold c$ is centrality vector

      The largest eigenvalue $\lambda_{max}$ is always positive and unique

      The leading eigen vector is used $\bold c_{max}$ is used for centrality

    - *<u>Betweenness centrality</u>* 

      node is important if it lies  on many shortest paths between other nodes

      if a node is an important transit hub

      $c_v = \sum{(number~of~paths~between~s~and ~ t ~ that~ contains v)/(total~ number~ of~ paths~ between~ s ~and ~t)}$

      

    - *<u>Closeness centrality</u>* - how close a node is to the center of the network etc...

      a node is important if it has small shortest path lengths to all other nodes

      $c_v = 1/(\sum shortest ~path  ~between~ u ~and ~v)$

  **Clustering Coefficient**

  how connected the neighbours of $v$  are 

  $e_v = (edges ~among ~neighbour~ nodes)/{k_v \choose 2}$

  

  **Graphlets**

  clustering coefficient counts the number of triangles of the ego-network(the network that is degree 1 neighbourhood)

  graphlet is rooted, connected and non-isomorphic sub-graph

  Graphlet Degree Vector

  GDV provide a measure of  nodes local network topology

- **Summary**

  - Node degree and Node Centrality are **importance based features**

    eg. application : Predicting celebrity users in a social network, predicting influential nodes in a graph

  - **Structure based features**: Node degree, clustering coefficient,  graphlet degree vector

    eg. application : predictin protein functionality  in a protein-protein interaction network.