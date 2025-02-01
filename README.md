
# NYC Taxi Trip Data Pipeline

## Project Description:
This project sets up a pipeline that processes real-time taxi trip data from New York City. The data is retrieved from a public API, sent to a Kafka topic, consumed by a Kafka consumer, and stored in an Elasticsearch index for querying and analysis. The system provides the ability to filter, aggregate, and analyze the taxi data using Elasticsearch.

## Features:
- **Kafka Producer:** Fetches real-time data from the NYC Taxi API and sends it to a Kafka topic.
- **Kafka Consumer:** Consumes messages from the Kafka topic and indexes them into an Elasticsearch cluster.
- **Elasticsearch Queries:** Provides filtering and aggregation capabilities to analyze data, such as:
  - Filtering by passenger count and payment type.
  - Aggregating total trips by vendor.
  - Calculating the average fare amount by payment type.

## Prerequisites:
- Python 3.x
- Docker (recommended for running Kafka and Elasticsearch)
- The following Python libraries, which can be installed using the `requirements.txt` file:

```bash
pip install -r requirements.txt
```

## File Structure:
```
├── taxi_python_producer.py        # Kafka producer to send NYC taxi data to a topic
├── taxi_python_consumer.py        # Kafka consumer to index data into Elasticsearch
├── index_query_filtering.py       # Script to filter data in Elasticsearch
├── index_analysis.py              # Aggregates total trips by vendor in Elasticsearch
├── index_agg.py                   # Calculates average fare amount by payment type
├── requirements.txt               # Python dependencies
```

## Setup Instructions:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/Gilad-Shai/NYC-Taxi-Trip-Data-Pipeline.git
   cd NYC-Taxi-Trip-Data-Pipeline
   ```

2. **Install the dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Run Kafka and Elasticsearch**:
   You can set up Kafka and Elasticsearch using Docker. Here’s a quick command to start them using Docker Compose:

   ```bash
   docker-compose up -d
   ```

4. **Run the Kafka Producer**:
   Start sending NYC taxi data to the Kafka topic:
   ```bash
   python taxi_python_producer.py
   ```

5. **Run the Kafka Consumer**:
   Index the data into Elasticsearch:
   ```bash
   python taxi_python_consumer.py
   ```

6. **Run Elasticsearch Queries**:
   - To filter trips with one passenger and a payment type of 2:
     ```bash
     python index_query_filtering.py
     ```

   - To aggregate the total trips by vendor:
     ```bash
     python index_analysis.py
     ```

   - To calculate the average fare amount by payment type:
     ```bash
     python index_agg.py
     ```

## Example Usage:
- **Taxi Data Producer**: Sends real-time taxi trip data from NYC’s API to Kafka.
- **Taxi Data Consumer**: Reads messages from Kafka and stores them in Elasticsearch for analysis.
- **Data Filtering & Aggregation**: Run custom queries on the data in Elasticsearch to perform analysis such as filtering by passenger count or aggregating average fare amounts.

## License:
This project is licensed under the MIT License.
