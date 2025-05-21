# Movie Remakes Graph Analysis

Analyze a movie remakes data using graph creation, graph visualization, node embeddings, and link prediction using Logistic Regression

Dataset: Movie Remakes Dataset crawled from Wikipedia, containing director and movie pairs (original, remake) https://mozart.diei.unipg.it/gdcontest/contest2021/index.php?id=creative-topics

Data was loaded and used to create multiple graphs for visualization and property analysis

  * Graphs
    
      * Movies Graph: Nodes = movies, Edges = movies by the same director
        
      * Directors Graph: Nodes = directors, Edges = directors that have a movie in the same decade
        
      * Bipartite Graph: Nodes = movies and directors, Edges = directors of movies
        
      * Projected Graph: Nodes = directors, Edges = directors that directed the same movie

  * Properties

      * Num nodes/edges

      * Max/min/avg degree

      * Num connected components, largest cc

      * Assortativity

      * Avg clustering coefficient

      * Centralities: degree, closeness, betweenness, eigenvector, Katz

Node embeddings of the projected graph were created using Node2Vec (Word2Vec with biased random walks) and visualized using t-SNE dimensionality reduction

Logistic Regression was trained to perform link prediction on the projected graph, which were visualized using PCA

  * Edges were split into training and testing sets (70:30)

  * Hyperparameters for Node2Vec and LR were tuned based on the maximization of ROC AUC

  * Four link embedding operators were tested: Hadamard, L1, L2, avg

LR Model: 90% train, 77% test ROC AUC

