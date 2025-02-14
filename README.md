# Twitter API Integration with Apache Kafka

This project demonstrates how to integrate the **Twitter API** with **Apache Kafka** to collect and process tweets in real-time. The tweets are retrieved using the **Twitter API**, sent to a Kafka topic, and then consumed for further processing and storage.

## 📌 Features

- Fetch real-time tweets from Twitter using the Twitter API.
- Produce tweets to an Apache Kafka topic (`twitter_topic`).
- Consume tweets from Kafka and store them in a **MySQL database**.
- Handle large-scale streaming data efficiently.

## 🛠️ Technologies Used

- **Python** (Kafka producer & consumer)
- **Apache Kafka** (Message broker)
- **Twitter API** (Data source)
- **MySQL** (Data storage)
- **Kafka-Python** (Python client for Apache Kafka)

---

## 🚀 Setup Instructions

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/IlhamBouatioui15/Twitter-API-integration-with-Apache-Kafka.git
cd Twitter-API-integration-with-Apache-Kafka
```

### 2️⃣ Install Dependencies
Ensure you have Python installed, then install required packages:

```bash
pip install kafka-python tweepy mysql-connector-python
```

### 3️⃣ Start Apache Kafka
Ensure Kafka and Zookeeper are running:

```bash
# Start Zookeeper
zookeeper-server-start.sh config/zookeeper.properties

# Start Kafka
kafka-server-start.sh config/server.properties
```

Create the Kafka topic:
```bash
kafka-topics.sh --create --topic twitter_topic --bootstrap-server localhost:9092
```

### 4️⃣ Configure Twitter API Keys
Create a `.env` file in the project root and add your Twitter API credentials:

```env
TWITTER_API_KEY=your_api_key
TWITTER_API_SECRET=your_api_secret
TWITTER_ACCESS_TOKEN=your_access_token
TWITTER_ACCESS_SECRET=your_access_secret
```

### 5️⃣ Run the Kafka Producer
Start the Twitter stream producer:

```bash
python producer.py
```

### 6️⃣ Run the Kafka Consumer
Start the consumer that reads from Kafka and inserts into MySQL:

```bash
python consumer.py
```

---

## 📊 Database Schema

The **MySQL database** stores tweets in a table with the following schema:

| Column       | Type         | Description                  |
|-------------|-------------|------------------------------|
| id          | INT         | Primary key, auto-increment |
| tweet_id    | VARCHAR(255)| Unique Twitter ID           |
| text        | TEXT        | Tweet content               |
| username    | VARCHAR(100)| Twitter username            |
| created_at  | DATETIME    | Timestamp of the tweet      |

---

## 📌 Future Enhancements

- Implement **Elasticsearch** for tweet searching.
- Add **sentiment analysis** on tweets.
- Deploy using **Docker & Kubernetes**.
- Integrate with **Apache Spark** for real-time analytics.

---

## 🤝 Contributing

Feel free to fork this repository, open issues, or submit pull requests! Contributions are welcome. 🚀

---

## 📧 Contact

👤 **Ilham Bouatioui**  
📩 [LinkedIn](https://www.linkedin.com/in/ilham-bouatioui)  
📧 Email: bouatioui.ensa@uhp.ac.ma 

---

This README provides a **clear structure**, setup guide, and future improvements. Let me know if you want modifications! 🚀
