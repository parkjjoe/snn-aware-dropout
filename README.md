# SNN-dropout-custom
## Spiking Neural Networks
Spiking Neural Networks (SNNs) is a new paradigm in the field of neural networks as the third-generation neuromorphic artificial intelligence technology. It has evolved from the first-generation Perceptron and second-generation Artificial Neural Networks. Unlike traditional deep learning models (DNNs), SNNs aim to more precisely mimic the biological characteristics of neurons and processes input information as temporal signals. Neurons in SNNs transmit information using discrete signals called ‘spikes’ instead of continuous values. Since the information is transmitted through spikes only when neurons are activated, SNNs are more energy-efficient than traditional DNNs.
## Dropout
Among the layers that make up the neural network model structure, the Dropout layer randomly deactivates some neurons during training. This prevents the network from overly depending on certain neurons. The most common reason why dropout layers are used is to improve overfitting. Overfitting occurs when a model becomes too reliant on the training data, leading to poor generalization on new data. By adding dropout layers, the model can learn various characteristics of the data and ultimately improve the model's generalization performance. In particular, the great effect of dropout can be expected in DNNs, and the robustness of the network can be improved by randomly removing some neurons across multiple layers.
## Motivation
However, applying traditional Dropout techniques directly to SNNs is challenging. Unlike standard DNNs, SNNs attempt to physically replicate human brain signals and deliver information based on the temporal patterns of neuron activity. So, a neuron generates a spike only when its membrane potential exceeds a certain threshold. In SNNs, the output value after the activation layer using an activation function, which imparts non-linearity to the output of the previous layer and passes it to the next layer, appears as 0 in most cases. As a result, applying traditional Dropout techniques to SNNs could be ineffective, as neurons that don't generate spikes would be unaffected, and the sparse spikes generated by active neurons could be further reduced, negatively impacting learning. That's why different approaches are needed in SNNs, leading to research that adjusts removal probabilities using membrane potential or synaptic weights.

Therefore, I propose several new dropout techniques suitable for SNNs.
