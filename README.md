# link-prediction-gnn
Term project for graph machine learning (AI60007) course. Group - 04. [Colab Link](https://colab.research.google.com/drive/1xNihZALJrhtnuu1YhWTAgFkRp8o4er87?usp=sharing)

### Dataset
Drug-drug interaction (DDI) dataset **ogbl-ddi** is provided by **[Open Graph Benchmark (OGB)](https://ogb.stanford.edu/)**

### Problem Definition
*positive edges* - edges which are present in the graph
*negative edges* - edges which are not present in the graph
*missing edges* - edges which may have a significant joint interaction, but the knowledge of whether it is positive or negative is not present in the graph.

Goal is to develop a graph machine learning model to solve the link prediction task: given two drugs as input, we want to predict if the two drugs interact with each other, i.e., if an edge should exist between these two nodes in the graph. This should allow us to complete our dataset by understanding missing edges as either positive or negative edges. Additionally, improve the robustness of the model making it more generalizable to new drugs.

### Dataset split
We do an edge split which is a "protein-target split": the edges are split such that drugs in the validation and test sets target different proteins than the drugs in the training set. The GNN will be trained using only the edges in the training set - at training time, it doesn't know anything about the validation or test edges. This makes the model more robust,  because it mirrors a more realistic use-case: new drug discoveries are likely to target different proteins than the existing set of drugs in the database. We want our model to be able to make accurate predictions about drugs that may be different from every other drug we’ve seen so far.

### Model
Our model has 2 components:-
1. Graph Neural Network (GNN) to generate node embeddings (using GraphSAGE)
2. Deep Neural Network to output probability for link prediction.
