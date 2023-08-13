# VN-Solver: Vision-based Neural Solver for Combinatorial Optimization over Graphs
This repository contains the code for experiments in the paper entitled ["VN-Solver: Vision-based Neural Solver for Combinatorial Optimization over Graphs"](https://arxiv.org/abs/2308.03185)  accepted in Proceedings of the 32nd ACM International Conference on Information and Knowledge Management (CIKM '23).

Our experiments consist of 4 models, namely, Naive Bayesian, Graph Transform [Graphormer](https://github.com/Microsoft/Graphormer), Gray-scale VN-Solver, Uniform-color VN-Solver.

In the VN-Solver RGB folder, we have the code for generating figures from adjacency matrixes in generate_figure.py. We have introduced another layout as ellipse in layout.py which should be replaced by the layout.py in networkx package. After generating figures, we train 5 ResNet models using 3, 7, 11, 13, 29 as seeds to split the data. The random seed of the model is 23 and the models are trained on 2 GPUs. As we have datasets with 3 different sizes, we defined a tv variable to indicate the size of the training set and validation set. The test_on_best.py evaluate the model with highest F1 score on the test set while the test_on_epochs.py evaluate models saved in each epoch against the test set. Evaluation on each epoch is further used to draw Figure 3 in the manuscript. The code to generate this figure is avaiable in draw_figures_in_manuscript.py. After evaluating the the best model on trst set, we should aggregate the results on each seed to have the final result which is done in aggregate_seed.py. 
