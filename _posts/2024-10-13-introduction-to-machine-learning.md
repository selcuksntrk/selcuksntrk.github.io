---
layout: post
title: "Introduction to Machine Learning"
date: 2024-10-13 12:00:00+0300
description: "Understanding the fundamentals of machine learning: types, learning modes, and main challenges."
tags: machine-learning data-science intelligent-systems ml-systems
categories: computer-science
giscus_comments: true
related_posts: false
toc:
  sidebar: left
---

## Types of Machine Learning

There are three main categories of machine learning systems:

- **Supervision modes**: supervised, unsupervised, and reinforcement learning
- **Learning modes**: online learning and batch learning
- **Inference types**: instance-based and model-based learning

These categories are not mutually exclusive and can be combined according to the needs of the problem.

### Example

A self-driving car might use a machine learning system that employs supervised learning, learns through batch learning, and reasons through a statistical model that enables short-term predictions, such as detecting that the car ahead is braking and the system needs to activate the brakes soon.

---

## Supervised Learning

The most common learning mode is supervised learning. This means training the system with data that contains the desired solution. These solutions are called **labels**.

An example of labeled data could be an image of a car, which is the input data, and its assigned car model, which is the label. After a machine learning system is trained on data and labels, it can take a new image and output its predicted label. The metrics used to measure the system's ability to assign correct labels vary by problem, and they are just as important as the training process itself.

The two most common tasks addressed with supervised learning are **classification** and **regression**.

### Classification

A classification problem assigns a discrete label to a new input. This can be a numerical value or a category, such as deciding whether a given image represents a dog or a cat. In either case, the answer belongs to a well-defined set of options. Properly defining those options can significantly affect model performance.

### Regression

A regression problem assigns a continuous value to new data. For example, a model might predict the price of a house from features such as the number of rooms, size in square meters, and number of bathrooms. In this case, the output belongs to a continuous range rather than a finite set.

Supervised learning requires a significant amount of labeled data for the model to learn effectively.

The classic example is a model trained on thousands of cat and dog images that learns to classify new photos into one of these two categories. Classification models can learn to distinguish any number of classes, as long as they have a representative dataset.

Generally, classification models predict the probability of an input sample belonging to each output class. These probabilities can be interpreted as the model's confidence that a particular sample belongs to each class. A predicted probability can be converted to a class value by selecting the label with the highest probability.

### Example

A model trained to distinguish cat and dog images, when given a cat image as input, might output probability values of 0.876 for cat and 0.124 for dog. In this case, the model decides the image is a cat because that probability is highest. We can also think of this value as the model's confidence in its conclusion.

---

## Unsupervised Learning

What if we do not have labeled data, or our goal is to discover structure we do not already know about? This is where unsupervised learning comes in, because the input consists of raw data without labels.

For example, imagine a supermarket sales dataset containing all purchases made by customers, basket by basket. By grouping frequently purchased items together, we can extract product relationships and choose to place products on nearby shelves or offer discounts on one product when others are purchased.

Unsupervised learning is also used as a complement to supervised learning. It can help explore data, even pre-labeled data, and reveal groupings or patterns that may have gone unnoticed.

Another use of this type of learning is **dimensionality reduction**. The aim is to reduce the number of features while preserving the value of the data. This is especially useful when the dataset is very large and sparse.

---

## Reinforcement Learning

Reinforcement learning is different from supervised and unsupervised learning. In this context, the learning system is called an **agent**. The agent learns by observing its environment, performing actions, and evaluating them based on a **reward** signal.

The agent is designed to improve itself by adjusting action parameters and aiming to achieve a larger reward. The model changes its behavior to optimize for the highest reward.

Reinforcement learning is heavily used in robotics. For example, a robot can learn to move around its environment by gradually learning from mistakes. Hitting a wall decreases the reward, while moving without collision increases the reward.

---

## Learning Modes

Another important feature of machine learning systems is whether they learn in one-shot mode, often called batch learning, or in a continuously incremental mode, often called online learning.

### Batch Learning

In batch learning, also called offline learning, the system is trained using all available data. This is usually a long and computationally expensive process, so it is only performed occasionally. When you want to retrain the model, you train it again on all the data, usually combining old data with any meaningful new data.

Fortunately, this training method can be automated. For example, a team might choose to retrain a model every night or every week.

### Online Learning

If you need a system that responds quickly to change, such as fraud detection or cyber attack detection, online learning can be a better solution. In online learning, the system is trained sequentially by taking small groups of data called **mini-batches** as input. Learning from new data is cheap and fast because the system updates as data arrives.

Online learning is useful when you need reactive system behavior or when you have limited computational power. The term "online" does not necessarily mean the system is connected to a network. It means the system learns from a continuous stream of data.

---

## Inference Types

One last way to categorize machine learning systems is by how they generalize.

### Model-Based Systems

Model-based systems aim to create a representation, or model, of knowledge. That model is then used to produce outputs.

### Instance-Based Systems

Instance-based systems do not generalize from an unseen input in the same way. Instead, they compare the input with previous data stored in memory and try to find the closest match.

### Example Scenario

Given a set of coordinates, such as X and Y values, suppose we want to estimate the right Y value for a new X value. One strategy is to compare the new X value with known X values, take the closest known point, and assign its Y value to the new point.

This approach is simple, but it relies on the strong assumption that a new point's output is determined by its nearest neighbor.

The system learns its knowledge by memory and applies a similarity measure, such as distance along the X dimension, to new situations.

Another approach is to create a representation of how the existing data was generated and use that model to estimate the Y value for a new X value. A model is a set of parameters that, when tuned appropriately, can provide a reasonable estimate for unseen inputs.

In a simple example, the model might be a straight line that best represents a series of points. The parameters are the slope of the line and the point where it intersects the y-axis. Training the model means finding good values for these parameters.

A machine learning model can contain tens of thousands or even millions of parameters. Training those parameters requires computational power, and improving the model training process is an important research and engineering topic.

---

## Main Challenges of Machine Learning

### Insufficient Data

The fundamental assumption of machine learning is having enough data to train models and then use them to solve problems. In the real world, there may be situations where the available data is not sufficient to train a model that can identify useful patterns.

Even simple problems can require thousands of examples. Complex problems like image recognition or speech recognition may require millions of examples.

Various organizations are moving toward open data platforms to share datasets and enable applications that would otherwise be difficult to build.

The labeling issue is also important. Services like CloudFactory or AWS Mechanical Turk try to meet this need by bringing together organizations that need data labeling and people who can label that data. Such services have limitations, including labeling accuracy and completion time.

### Low-Quality and Non-Representative Data

Another common problem is low-quality training data. Missing, poorly formatted, or incorrect data can be fatal for a machine learning project. Ideally, high-quality data should be produced directly, but many projects start from existing data that is messy or incomplete.

Therefore, one of the most important and time-consuming steps in developing an ML application is **data preprocessing**.

Data preprocessing consists of cleaning the data and preparing it for the machine learning model. This can include removing damaged samples, adjusting string formats, and managing missing values. The preprocessing stage is context-dependent and can take many forms.

At this stage, we may also try to increase the size of the dataset. For example, if we have an image dataset, we might add transformed copies of images, such as rotated or blurred versions. This lets the model learn from different views of the same image.

This technique, called **data augmentation**, is useful for increasing model robustness. The model learns to recognize images even when they are damaged or altered. However, augmentation usually does not add truly new information. That can only come from additional data.

Non-representative data is another common issue. For a model to generalize effectively, it must have seen cases that cover most realistic situations.

For example, consider a dataset of temperatures collected on various days of the year, where the task is to predict the temperature of a given day. If we only have November temperatures, how can the model discover the April temperature pattern? Even worse, if that particular November was unusually warm, the model may produce misleading predictions.

As a thought experiment, a random model that generates a random number within the minimum and maximum temperature range could outperform a model trained on non-representative data.

### Underfitting

Underfitting occurs when the model is too simple to represent the structure of the dataset, so it cannot capture the patterns in the data.

For example, if we wanted to use a linear model to classify dog and cat images, we would probably get unacceptable performance because a linear model cannot capture the complexity of image data.

One solution to underfitting is to train more complex models, such as neural networks with many parameters. These models can account for more variables that may affect the output. In a 64 by 64 pixel image, there are 4096 possible pixel positions that may influence the result. A model with too few parameters may struggle with this complexity.

### Overfitting

Overfitting is the opposite problem. It happens when a model is too complex for the task or the amount of data available.

For example, a complex high-degree curve trained to predict house prices may represent the training dataset extremely well, but fail on new data. The model has memorized the training data rather than learning a pattern that generalizes.

### The Balance Between Underfitting and Overfitting

The balance between model complexity, amount of data, and task difficulty is one of the fundamental concepts behind model architecture choices.

- **Underfitting**: The model is too simple and cannot capture the complexity of the dataset.
- **Normal Learning**: The model captures the general pattern in the data without memorizing each point.
- **Overfitting**: The model adapts too strongly to the training data and has difficulty generalizing later.

---

## Conclusion

We have seen how machine learning models can be classified, and we have introduced classification, regression, learning modes, inference types, and common ML challenges.

In the continuation of this series, we will build the technical foundation needed to create machine learning models. We will start with mathematical concepts and continue by examining the architectures of machine learning models. The ultimate goal is to gain the ability to build AI models for real problems.
