# Glassnode: Data Science Challenge

The Data Science Code Challenge is an opportunity to demonstrate proficiency with problem solving and collaboration skills we would expect you to use.

The Challenge creates a foundation for further onsite collaboration during your interview. Additionally, we want you to get a feel for some of the challenges you'll encounter here.

## How to complete a Challenge

Create a new git repository for your solution.

Organize your work within that repository. When you get to a stopping point, publish it, preferably on Github but you can just as well archive it and send it to us.

## Time

We respect your time and the challenge is designed in such a way as not to take more than 3-4 hours. We just want to get a sense of your thought process and the way you do the work. If there are things you don't have time to implement, feel free to describe the intended approach to implementation in the README.

## The Challenge

The challenge consists of two parts.

### 1 - Cryptocurrency Price Predictor

The goal of this task is to build a model to predict price movement of a crypto asset.

Fetch hourly historic price data from the Cryptocompare API and build a machine learning model for your cryptocurrency of choice that predicts if the price is going to go up or down in the next hour.

Next, build a model that predicts if the price will go up or down for the next 6 hours (one prediction per hour).

The challenge is deliberately kept very general. You are free to use the approach you think is best, including any additional data that you think might be helpful.

### 2 - Dockerised API

Now that you have a model, build a simple application that serves predictions.

This task consists in writing a simple REST API with a single endpoint that for a coin returns the predictions for the next 6 hours as JSON. The predictions should start at one hour after the last price datapoint available. Ideally, use Docker to containerise your API.

Example usage of your Docker application:

```
docker build -t <your-rest-api-docker-image> .
docker run -t <your-rest-api-docker-image> -d
curl http://<DOCKER-IP>:5000/predict?coin=BTC
```

## Questions to keep in mind

* How well does your model perform? How does it compare to the simplest baseline model you can think of?
* How does the 1-hour-prediction-model compare to the 6-hour-prediction-model?
* Where do you see the main challenge in building a model like the one we asked here?
* What would you do if you had more time to improve the model?
* What additional data would you incorporate if you had access to it? Why?

## What we care about

We love Python, but feel free to use your prefered language, tool, and libraries.

Make sure you include:

- A description of the problem and solution.
- The reasoning behind your technical choices: trade-offs you might have made, anything you left out, or what you might do differently if you had additional time.
- What you'd do next and why.

The exact predictive accuracy will not be the main evaluation critereum for this challenge. Reviewing the application we'll rather look at the following aspects:

* *Documentaion and Clarity*: Does the README/Jupyter notebook clearly explain the problem and solution?
* *Correctness*: Does the submission accomplish what was asked? If there is anything missing, does the README explain why it is missing?
* *Code Quality*: Is the code simple, easy to understand, well documented? Is it aligned with the community-accepted way of solving similar problems?
* *Technical choices and creativity*: What was your approach to tackle the problem? What ML algorithm and evaluation metric did you choose? What is the level of creativity / ingenuity of your solution?

# Questions?

Feel free to [email us](mailto:ds@wattx.io) with any questions you might have about the challenge.

Looking forward to your submission!
