# CRIMAC-classifiers-vae

Variational Auto Encoder on acoustic data

## Idea

An _autoencoder_ (AE) is a neural network that transforms input to a _latent
representation_, and then reconstructs the input from this
representation.  A _variational_ AE (VAE) generates a latent
representation as a statistical distribution over the latent space,
typically Gaussian represented as a vector of expectations and a
vector of (log) variances.

The VAE uses a cost function that combines the reconstruction error
with a cost based on KL divergence from a normal distribution, i.e. it
drives the output distribution twowards a Gaussian around the origin.

## Plan

Use a VAE to build an unsupervised representation of acoustic data.
For visualization purposes, the representation should be 2D or 3D.

0. Identify a large data set that provides the same frequencies and
   uses the same sampling intervals.
1. Using a segment of a ping as input (sv and angles) , train for
   reconstruction
2. Ditto, but train for reconstructing the next ping (eliminate noise)
3. Include one or more observational variables: depth, time of day,
   time of year, lattitude, temperature
4. Factor out total intensity/acoustic mass?

### Testing

In addition to reconstruction loss, test the latent representation by
examining manual annotations, and mapping them to the latent space. If
the latent mapping is useful, different annotations should occupy
dense and distinct regions.

