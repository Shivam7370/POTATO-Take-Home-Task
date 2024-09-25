# Project Title: POTATO Twitter Analysis System

## Table of Content
- [Overview](#overview)
- [Key Features](#key-features)
- [Technologies Used](#technologies-used)
- [Task Breakdown](#task-breakdown)
- [Contact Information](#contact-information)


## **Overview**

This repository contains the solution to the POTATO (Panel-based Open Term-level Aggregate Twitter Observatory) take-home task. POTATO is a prototype system developed to analyze and aggregate Twitter data from the Lazer Lab’s Twitter Panel. This panel connects over one million real U.S. voters to their Twitter accounts, covering tweets from 2016 to 2023.

The main goal of POTATO is to provide aggregate insights into users' tweets on specific topics. For instance, when a term like “COVID” is searched, POTATO returns key metrics about the users who tweeted about the term, such as tweet counts, user demographics, and engagement statistics. The system ensures privacy by applying a threshold that hides demographic data for groups smaller than ten users and may incorporate statistical noise to further protect individual identities.

## **Key Features**

- Efficient Data Ingestion: POTATO efficiently handles large datasets (using Twitter Panel data), making it scalable for high-volume data analysis.
- Term-based Queries: Users can search for specific terms (e.g., "music," "COVID") and retrieve detailed insights, such as:
  - The number of tweets containing the term posted on each day.
  - The number of unique users tweeting about the term.
  - The average number of likes on tweets containing the term.
  - Geographic information (place IDs) from where the tweets originated.
  - The times of day the tweets were posted.
  - The user who posted the most tweets about the term.
- Privacy Focus: POTATO ensures that no demographic bucket with fewer than ten users is displayed, and noise may be added to safeguard the distribution of sensitive data.
- Modular and Extensible: The system can be extended to include NoSQL databases, Docker containers for deployment, and API support (via Flask).

## **Technologies Used**

- **Python:** The core of the system is written in Python, using pandas for data manipulation.
- **Docker (optional):** To ensure the system can be containerized and run in isolated environments.
- **Elasticsearch (optional):** Used for indexing and querying large datasets efficiently.
- **Streamlit (optional):** Provides a user interface for visualizing the queries and results.
- **Flask (optional):** Allows the creation of APIs for querying the data.
- **HDFS:** The system can ingest data from the Hadoop Distributed File System (HDFS), making it scalable for large datasets.

## **Task Breakdown**
**Data Ingestion:**

The first part of the task involves reading Twitter data from two TSV files (one ~50MB, another ~500MB). The data is then loaded into a structure (like a pandas DataFrame) for querying and analysis.

**Query Functionality:**

Several key metrics must be calculated when a user searches for a term:
- Number of tweets containing the term on each day.
- Number of unique users who tweeted about the term.
- Average number of likes for tweets with the term.
- Geographic origin of the tweets (place IDs).
- Times of day when the tweets were posted.
- The user with the highest number of tweets about the term.

**System Usage:**

The task requires creating a system that can be easily run by others. This includes writing clear instructions and justifying key design choices in the implementation.

**Bells and Whistles:**

The system can be enhanced by using Docker for containerization, a NoSQL database for data storage, constructing a REST API (via Flask), optimizing query performance, providing thorough documentation, and including unit tests (e.g., using pytest).

**Getting Started**

- **Clone the Repository:**

```Jupyter Notebook
git clone https://github.com/your-username/potato-twitter-analysis.git
cd potato-twitter-analysis
```
- **Install Dependencies:**

Ensure you have Python 3.7+ installed. Install the required Python packages by running:
```Jupyter Notebook
pip install -r requirements.txt
```
- **Running the System:**

After cloning the repo and installing dependencies, you can run the system by executing the Python script:
```Jupyter Notebook
python main.py
```
- **(Optional)Running with Docker:**

If you want to run the system inside a Docker container:
```Jupyter Notebook
docker build -t twitter-analysis
docker run -p 5000:5000 twitter-analysis
```
- **Querying the Data:**

Use built-in functions such as tweets_per_day(), unique_users(), and average_likes() to query the data based on specific terms.



## **Contact Information**

If you have any questions about the system, feel free to reach out to me at shivamshekhar702@gmail.com.
