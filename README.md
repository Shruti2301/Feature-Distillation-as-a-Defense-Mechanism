
# Obfuscated Gradients in Machine Learning Models: Defenses and Attacks

## Overview

This project investigates the use of obfuscated gradients as a defense mechanism to protect machine learning models from various types of attacks. The research specifically focuses on three main types of obfuscated gradients:
- Shattered Gradients
- Stochastic Gradients
- Vanishing/Exploding Gradients

We explore the effectiveness of these strategies and introduce three new attacks designed to penetrate these defenses. Additionally, we implement enhancements beyond the original work to improve model robustness.

## Problem Studied

The primary objective of this research is to evaluate how obfuscated gradients can safeguard machine learning models against adversarial attacks.

The paper makes significant contributions to the field by:

1. Providing a comprehensive analysis of various defense strategies against adversarial attacks.
2. Developing three novel attacks that successfully breach these defenses.

[Watch the Defense Implementation Video](https://github.com/Shruti2301/Feature-Distillation-as-a-Defense-Mechanism/blob/main/Defense%20Implementation.mp4)

## Approach

The research involved a thorough examination of different defense mechanisms and devising methods to circumvent them. The focus was on enhancing the strength of obfuscated gradients against direct (white-box) attacks.

## Personal Learnings

Engaging with this research provided deeper insights into the functionality and limitations of defenses against adversarial attacks. The findings highlighted that while obfuscated gradients offer some protection, they are not foolproof. Reproducing the experiments was challenging due to outdated code and unsupported modules, necessitating considerable effort to achieve accurate results.

## Re-implementation Results

We re-implemented the attacks on all the defenses evaluated in the study. The results are as follows:

| Defense               | Dataset   | Original Accuracy (%) | Our Accuracy (%) |
|-----------------------|-----------|-----------------------|------------------|
| Thermometer Encoding  | CIFAR     | 0                     | 2                |
| LID                   | CIFAR     | 5                     | 5                |
| Input Transformation  | ImageNet  | 0                     | 0                |
| SAP                   | CIFAR     | 0                     | 0                |
| Randomization         | ImageNet  | 0                     | 3                |
| PixelDefend           | CIFAR     | 9                     | 12               |
| Defense-GAN           | MNIST     | 55                    | 55               |

## Enhancements Beyond Original Work

Initially, we attempted a straightforward white-box method to enhance security, which was not effective. We then adopted a black-box approach, concealing certain model features from potential attackers. This method not only corrected the images but also preserved the general category of the images, albeit imperfectly (e.g., confusing cats with coyotes or cheetahs). A key enhancement was the application of Feature Distillation, which simplified input features to improve model robustness and maintain accuracy against adversarial attacks. This enhancement was applied exclusively to the BPDA attack and not to the other two attacks discussed in the paper.

## Feature Distillation

Feature Distillation is a technique used to enhance the robustness of machine learning models by simplifying input features. This process involves training a distilled model that focuses on essential features, thereby reducing the vulnerability to adversarial attacks. In this project, Feature Distillation was employed to strengthen the BPDA attack defense, resulting in improved model resilience without significant loss of accuracy.

### Explanation of Feature Distillation

Feature Distillation simplifies the input features by training a smaller, distilled model that captures the most critical aspects of the input data. This process helps in the following ways:

1. **Reduction of Redundant Features**: By focusing on essential features, the distilled model eliminates unnecessary data, making it harder for adversarial attacks to find weak points.
2. **Improved Robustness**: The distilled model is less susceptible to perturbations, enhancing the overall robustness of the system.
3. **Maintained Accuracy**: Despite the simplification, the distilled model maintains a high level of accuracy, ensuring reliable performance even under attack.

## Project Structure

The project consists of the following key components:

1. **Data Preparation**: Scripts for loading and preprocessing datasets.
2. **Model Implementation**: Code for implementing various defense mechanisms.
3. **Attack Implementation**: Scripts for executing the original and newly developed attacks.
4. **Feature Distillation**: Implementation of Feature Distillation to enhance model robustness.
5. **Evaluation**: Scripts for evaluating model performance against attacks.
