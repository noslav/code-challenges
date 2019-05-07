# Glassnode: Blockchain Data Science Challenge

The Blockchain Data Science Code Challenge is an opportunity to demonstrate proficiency with problem solving, coding and data science skills we would expect you to use.

The challenge creates a foundation for further onsite collaboration during your interview. Additionally, we want you to get a feel for some of the challenges you'll encounter here at Glassnode.

## How to Complete a Challenge

Simply organize your code in a folder containing your jupyter notebooks, modules, scripts, READMEs -- anything you'd like to provide. Archive it and send it to us once you're done.

We love Python, and appreciate if you use it as well. If you have strong preferences for something
else, feel free to use your prefered language, tool, and libraries though.

## Time

We respect your time and the challenge is designed in such a way as not to take more than 3-4 hours. We just want to get a sense of your thought process and the way you do the work. If there are things you don't have time to implement, feel free to describe the intended approach to implementation in the README.

## The Challenge

The challenge consists of three parts.

### 1 - Blockchain Data Insights 

The goal of this task is to query data from the Ethereum blockchain in order extract a few on-chain insights.
To do so, you will be using [Google's BigQuery Ethereum
Database](https://console.cloud.google.com/marketplace/details/bigquery-public-data/ethereum-blockchain).

There are two ways in which you can interact with Ethereum's BigQuery DB.

1. If you have a Google Cloud Platform account, or you set one up, you can interact with the
   database directly.
   
   In order to be able to query data from BigQuery, you need to authenticate.
   Simply go to your GCP project, and firat select  `APIs & Services > Dashboard > Enable APIs and Services`. There,
   search for BigQuery DB and click on `Manage`. Once enabled head to `APIs & Services > Credentials > Create credentials > Service account key > New service account`. Create a service account with a role that let's you query BigQuery data
   (e.g. `BigQuery Data Admin`) and download the key as JSON. Then simply define an environment
   variable that points to the JSON file, e.g. 
   ```
   export GOOGLE_APPLICATION_CREDENTIALS="/your/path/to/gcp_credentials.json"
   ```
   Done! You should be able to make queries on the Ethereum BigQuery database. Try it out by
   executing the query in the [attached notebook](bigquery-sql-example.ipynb). Make sure you have the BigQuery Client library for
   Python installed (run `pip install --upgrade google-cloud-bigquery ` first).

2. You can also use [Kaggle's public dataset BigQuery
   integration](https://www.kaggle.com/bigquery/ethereum-blockchain). Simply sign in (or register)
   in Kaggle, create a new Python Jupyter notebook kernel and write your code there. Once you're done, you can
   download your code into as an `.ipynb` file.

Here are some questions we would like you to solve you in this task:

- Which ERC20 tokens had the most activity (in terms of number of transactions) within the last week?
- What is the total transaction volume of each of those top tokens within that period?
- How does the daily number of transactions of those top 5 tokens look like for the last month?

Think about how to best represent (visualise) the results obtained from the above questions.

### 2 - Unsupervised Learning: Clustering 

In this part your task is to query Ethereum transactions and use unsupervised learning in order to
cluster addresses. Using all transactions from the last 1-2 weeks should be enough to tackle this task.

The task is deliberately held general. Here are a couple of things to consider:

- Which features do you engineer in order to feed into the clustering algorithm?
- Can you tell which features had the most influence on your clustering results? Do you see interesting patterns, e.g. anything in particular that is common for addresses in a particular cluster?
- How do you chose the inital number of clusters?
- Is it possible to evaluate the results of your clustering? If so, how?
- How would you tackle this task if you had to run feature engineering and clustering on a year
  of transaction data, e.g. the data would be too large to fit into the memory of your computer and computation
  of features would be computationally very expensive?
- What are more advanced things you can think of on how to tackle this task, but that are out of
  this challenge's scope?

*BONUS:*

Now that you have a clustering model, build a simple Docker application that serves predictions.

This task consists in writing a simple REST API with a single endpoint that returns the cluster prediction for a new address.

Example usage of your Docker application:

```
docker build -t <your-rest-api-docker-image> .
docker run -t <your-rest-api-docker-image> -d
curl http://<DOCKER-IP>:5000/predict?address=<ethereum-address>
```

### 3 - Supervised Learning

In the present folder you will find a [time-series dataset in CSV format](challenge_data.csv) with six features and a target variable. Without further knowledge of what the variables actually represent, your task is to explore whether the features can be used in order to predict the target variable.

Again, the task is held rather general and you can approach it the way you like.

A couple of things to consider:

- Is there a correlation between the features and the target variable?
- Is there any feature that works better as a predictor as compared to the others?
- The time resolution of the dataset is 1h. Can we improve predictions by looking at a more
  coarse resolution?

## What we care about

Make sure you include:

- A description of the problem and solution.
- The reasoning behind your technical choices: trade-offs you might have made, anything you left out, or what you might do differently if you had additional time.
- What you'd do next and why.

Reviewing your submission we'll rather look at the following aspects:

* *Documentaion and Clarity*: Does the README/Jupyter notebook clearly explain the problem and solution? Do you use visualisations in order to clearly communicate you results?
* *Correctness*: Does the submission accomplish what was asked? If there is anything missing, does the README explain why it is missing?
* *Code Quality*: Is the code simple, easy to understand, well documented? Is it aligned with the community-accepted way of solving similar problems?
* *Technical choices and creativity*: What was your approach to tackle the problems? What algorithms and evaluation metric did you choose? What is the level of creativity / ingenuity of your solution?

# Questions?

Feel free to [email us](mailto:rafae@glassnode.com) with any questions you might have about the challenge.

Looking forward to your submission!
