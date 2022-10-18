# Online Link Prediction on Drug-Drug interaction network
Term project for graph machine learning (AI60007) course. Group - 04. [Colab Link](https://colab.research.google.com/drive/1xNihZALJrhtnuu1YhWTAgFkRp8o4er87?usp=sharing)

Taking certain combinations of drug can be unsafe if they interact with each other and produce a combined effect different from what they produce when taken
individually. Medical professionals and patients rely on drug-drug interaction databases to make safe medical decisions.

### Dataset
Drug-drug interaction (DDI) dataset **ogbl-ddi** is provided by **[Open Graph Benchmark (OGB)](https://ogb.stanford.edu/)**

We define the DDI graph mathematically as G = (V, E), where V is the set of nodes and E is the set of edges. Each node v ∈ V in the graph represents an FDA-approved or experimental drug. The existence of an edge (u, v) between two nodes u and v indicates that the two drugs interact such that the effect of taking both drugs together is considerably different from the expected effect in which drugs act independently of each other.For example, two drugs that target the same proteins may have a significant joint interaction.

