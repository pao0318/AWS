# Model architecture
In this section, we will walk through the architecture of the proposed GAN.

The model consists of two networks, a generator and a critic. These two networks work in a tight loop as following:

Generator:
The generator takes in a batch of single-track piano rolls (melody) as the input and generates a batch of multi-track piano rolls as the output by adding accompaniments to each of the input music tracks.
The critic then takes these generated music tracks and predicts how far it deviates from the real data present in your training dataset.
This feedback from the critic is used by the generator to update its weights.
Critic: As the generator gets better at creating better music accompaniments using the feedback from the critic, the critic needs to be retrained as well.
Train the critic with the music tracks just generated by the generator as fake inputs and an equivalent number of songs from the original dataset as the real input.
Alternate between training these two networks until the model converges and produces realistic music, beginning with the critic on the first iteration.
We use a special type of GAN called the ## Wasserstein GAN with Gradient Penalty (or WGAN-GP) to generate music. While the underlying architecture of a WGAN-GP is very similar to vanilla variants of GAN, WGAN-GPs help overcome some of the commonly seen defects in GANs such as the vanishing gradient problem and mode collapse (see appendix for more details).

Note our "critic" network is more generally called a "discriminator" network in the more general context of vanilla GANs.