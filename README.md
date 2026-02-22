# Learning Probability Density Functions using GAN(Generative Adversarial Network)

## Objective
Learn unknown probability density function using GAN from transformed NO2 concentration data.

## Dataset

https://www.kaggle.com/datasets/shrutibhargava94/india-air-quality-data

NO₂ concentration values were extracted from the dataset and used as the feature (x).

## Transformation
z = x + a_r * sin(b_r * x)
where:

a_r = 0.5 × (r mod 7)  
b_r = 0.3 × (r mod 5 + 1)

Here:

- mod represents the remainder operation.
- r is 102303561(university roll number)

## GAN Architecture

Generator:
- Input noise vector
- Dense(32) + ReLU
- Dense(32) + ReLU
- Dense(1)

Discriminator:
- Dense(32) + LeakyReLU
- Dense(32) + LeakyReLU
- Dense(1) + Sigmoid

## Results

### Transformation Parameters
- a_r = 1.5
- b_r = 0.6

### PDF Plot obtained from GAN samples

<img width="400" height="446" alt="Screenshot 2026-02-22 at 10 01 44 PM" src="https://github.com/user-attachments/assets/9fbf2a5f-57b5-4798-bde9-4ef73d44c0f7" />

### Observations

**Mode Coverage**
- The generator captures the dominant peak of the distribution and aligns well with the real sample histogram.

**Training Stability**
- Generator and discriminator losses remain stable and bounded during training, indicating stable adversarial learning.

**Quality of Generated Distribution**
- Generated distribution closely approximates the empirical distribution with minor deviations in tail regions.

## License

This project is licensed under the MIT License.
