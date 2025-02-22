Evaluating Activation Functions: Performance in Classification, Regression, and Smoothing Output Landscapes

The comparative evaluation of 12 state-of-the-art activation functions (AFs), based on rigorous statistical and experimental methodologies, provided insights into their efficacy. This evaluation assists practitioners in making informed decisions when selecting and designing AFs for specific deep learning tasks, thereby improving the efficiency and accuracy of their models.

Regression Experiment

During training, the Gradients RMS per batch, Gradients RMS per epoch, weights RMS per epoch, round loss and validation loss are monitored to ensure proper training dynamics. The evolutions of metrics are plotted for each AF, showing how the metrics change over the training iterations.

Classiﬁcation Experiment

During training, the Gradients RMS per batch, Gradients RMS per epoch, weights RMS per epoch, round loss and validation loss, are monitored to ensure proper training dynamics. The evolutions of metrics are plotted for each AF, showing how the metrics change over the training iterations. The experiment monitors training progress through confusion matrix plots,  compares the results, and visualizes the decision boundaries, to understand the influence of each AF on training dynamics and classification performance.

Smoothing Output Landscapes

We also visualized the output landscape of a 3-layer randomly initialized Neural Network (NN) with various AFs such as ReLU, ELU, SELU, GELU, Swish, HardSwish, Mish, SoftPlus, HardTanh, HardSigmoid, Sigmoid, and Tanh for visual clarity. Specifically, we input the 2-dimensional coordinates of each position in a grid into the network and plotted the scalar network output for each grid point. Our observations indicate that AFs significantly influence the smoothness of output landscapes.

ReLU, HardTanh, HardSigmoid, and HardSwish each uniquely affect NN performance. ReLU enhances sparsity and efficiency by producing zero output for negative inputs, but its abrupt transition at zero causes sharp regions in the output landscape, posing challenges for gradient-based optimization. HardTanh, which approximates the Tanh function, provides some sparsity with constant gradients within the range of -1 to 1, but introduces sharp transitions at -1 and 1, potentially affecting optimization. HardSigmoid, a piecewise linear approximation of the Sigmoid function, offers smoother transitions with a constant gradient within the range of -2.5 to 2.5, yet still has sharp regions at the boundaries, impacting optimization. HardSwish, a piecewise linear approximation of Swish, maintains smoothness within [-3,3], promoting better gradient flow and mitigating the vanishing gradient problem while being computationally efficient. These four functions can create non-smooth regions in the output landscape (and loss landscape), potentially leading to issues in gradient-based optimization. Conversely, networks using ELU, SELU, GELU, Swish, Mish, SoftPlus, Sigmoid, and Tanh exhibit considerably smoother output landscapes. Smoother output landscapes lead to smoother loss landscapes, which are easier to optimize and result in improved training and test accuracy.
