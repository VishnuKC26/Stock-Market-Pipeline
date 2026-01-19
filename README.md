# Stock Market Data Analysis Pipeline using AWS Serverless Architecture

## Architecture Diagram

<img width="576" height="373" alt="architecture-diagram" src="https://github.com/user-attachments/assets/1b991bd5-3a0e-408e-93a4-0697168b1975" />

## 🧰 AWS Services Used

| Service | Purpose |
|------|--------|
| Amazon Kinesis Data Streams | Real-time ingestion of stock price data |
| AWS Lambda | Stream processing and trend analysis |
| Amazon S3 | Storage of raw data and query results |
| AWS Glue Data Catalog | Schema management for Athena |
| Amazon Athena | SQL-based historical data analysis |
| Amazon DynamoDB | Low-latency storage for processed data |
| DynamoDB Streams | Event trigger for trend detection |
| Amazon SNS | Email notifications for alerts |
| Amazon CloudWatch Logs | Monitoring and debugging |

---

## 📊 Trend Detection Logic

The system detects market trends using **Simple Moving Averages (SMA)**:

- **SMA-5** → Short-term price movement  
- **SMA-20** → Medium-term trend  

### Signals
- 📈 **Uptrend (BUY)**  
  When SMA-5 crosses **above** SMA-20 (Golden Cross)
- 📉 **Downtrend (SELL)**  
  When SMA-5 crosses **below** SMA-20 (Death Cross)

Trend detection is triggered automatically using **DynamoDB Streams** whenever new stock data is inserted or updated.

---

## 🔄 Event Flow

A detailed explanation of the event-driven workflow is available here:

📄 **[Event Flow Documentation](architecture/event_flow.md)**


## 💰 Cost Optimization

- Fully serverless architecture
- No always-on compute resources
- Suitable for AWS Free Tier experimentation

All resources were deleted after successful validation.

---

## 🧠 Key Learnings

- Event-driven architectures using DynamoDB Streams
- Stream processing with AWS Lambda
- Serverless analytics using S3, Glue, and Athena
- Real-time notifications with Amazon SNS
- Debugging AWS triggers and permissions
- Cost-aware cloud system design

---

## 🔮 Future Improvements

- Replace SMA with **EMA** for faster response
- Add technical indicators like **RSI / MACD**
- Use **Amazon OpenSearch** for real-time analytics
- Build dashboards using **Amazon QuickSight**
- Use epoch timestamps for performance optimization
- Add alert deduplication logic

---

## 📜 License
This project is for educational and portfolio purposes.
