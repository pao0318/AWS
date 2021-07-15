# Critic (Discriminator)
The goal of the critic is to provide feedback to the generator about how realistic the generated piano rolls are, so that the generator can learn to produce more realistic data. 
The critic provides this feedback by outputting a scalar that represents how “real” or “fake” a piano roll is.

Since the critic tries to classify data as “real” or “fake”, it is not very different from commonly used binary classifiers. 
We use a simple architecture for the critic, composed of four convolutional layers and a dense layer at the end.
