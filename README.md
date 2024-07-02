# Realtime Election Voting System

This repository contains the code for a realtime election voting system built with Python, Kafka, Spark Streaming, PostgreSQL, and Streamlit. The system utilizes Docker Compose for easy deployment of services in Docker containers.

## System Architecture
![System Architecture](system_architecture.jpg)

## System Flow
![System Flow](system_flow.jpg)

## System Components
- **main.py:** Creates PostgreSQL tables (candidates, voters, votes), sets up the Kafka topic, and manages vote consumption and production to `voters_topic` on Kafka.
- **voting.py:** Consumes votes from `voters_topic`, generates voting data, and produces data to `votes_topic` on Kafka.
- **spark-streaming.py:** Consumes votes from `votes_topic`, enriches data from PostgreSQL, aggregates votes, and produces data to specific Kafka topics.
- **streamlit-app.py:** Consumes aggregated voting data from Kafka and PostgreSQL, displaying it in realtime using Streamlit.

##Reference:
https://github.com/airscholar/realtime-voting-data-engineering
