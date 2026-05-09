# Serverless Event-Driven Order Processing System (AWS)

This project demonstrates a high-performance, decoupled architecture for handling order spikes in a cloud environment. By using a Producer-Consumer pattern with **Amazon SQS**, the system ensures that no data is lost during high traffic and the database (DynamoDB) is not overwhelmed.

## 🚀 Architecture Overview

1. **Order Producer (AWS Lambda):** Receives incoming order data and validates it.
2. **Amazon SQS (Simple Queue Service):** Acts as a buffer, holding the order messages in a queue.
3. **Order Consumer (AWS Lambda):** Automatically triggered by SQS messages to process the order.
4. **Amazon DynamoDB:** Stores the final processed order details.



---

## 🛠️ Tech Stack

- **Cloud Provider:** Amazon Web Services (AWS)
- **Services:** Lambda, SQS, DynamoDB, IAM
- **Language:** Python 3.12 (Boto3 SDK)
- **Concept:** Event-Driven Architecture, Decoupling, Asynchronous Processing

---

## 📸 Screenshots

(https://github.com/cit-24-01-0532-cyber/Serverless-Event-Driven-Inventory-System/blob/main/Screenshot%202026-05-09%20085132.png)

(https://github.com/cit-24-01-0532-cyber/Serverless-Event-Driven-Inventory-System/blob/main/Screenshot%202026-05-09%20085457.png)

(https://github.com/cit-24-01-0532-cyber/Serverless-Event-Driven-Inventory-System/blob/main/Screenshot%202026-05-09%20091008.png)
 
 (https://github.com/cit-24-01-0532-cyber/Serverless-Event-Driven-Inventory-System/blob/main/Screenshot%202026-05-09%20091503.png)

---

## 📖 How it Works

1. The **Producer Lambda** is triggered with a JSON payload representing an order.
2. The Producer generates a unique `orderId` and sends the message to the **SQS Queue**.
3. **SQS** triggers the **Consumer Lambda** as soon as a message arrives.
4. The Consumer reads the message body and writes the record into the **OrdersTable** in DynamoDB.

---

## 🔑 Key Learnings

- Implementing **Decoupling** to improve system reliability.
- Handling **Asynchronous** workflows in AWS.
- Configuring **IAM Policies** for cross-service communication (SQS & DynamoDB).
- Working with **Boto3** to interact with AWS services programmatically.
