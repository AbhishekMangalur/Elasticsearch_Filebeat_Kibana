# 🚀 ELK Stack – Nginx Log Monitoring with Filebeat (Docker)

A fully containerized ELK stack project to monitor **Nginx access and error logs** using:

- Elasticsearch 8.13.0  
- Kibana 8.13.0  
- Filebeat 8.13.0  
- Nginx  

This project demonstrates a centralized logging architecture using Docker.

---

## 📌 Architecture


Nginx → Filebeat → Elasticsearch → Kibana


### 🔄 How It Works

1. Nginx generates `access.log` and `error.log`
2. Logs are written to a Docker-mounted volume
3. Filebeat reads logs from the shared volume
4. Filebeat sends logs to Elasticsearch (`filebeat-*` index)
5. Kibana visualizes logs from Elasticsearch

---

---

## 🛠️ Prerequisites
Make sure you have installed:
- Docker
- Docker Compose
Check versions:
```bash
docker --version
docker compose version

▶️ How to Run
1️⃣ Clone the Repository
git clone https://github.com/YOUR_USERNAME/YOUR_REPO.git
cd YOUR_REPO
2️⃣ Start the Stack
docker compose up -d
3️⃣ Verify Running Containers
docker ps

Expected containers:
elasticsearch
kibana
nginx
filebeat

🌐 Access Services
Service	URL
Nginx	http://localhost
Kibana	http://localhost:5601
Elasticsearch	http://localhost:9200

🔐 Elasticsearch Credentials
Username: elastic
Password: viWmk2XOXFGjiOtXNMr6

📊 Viewing Logs in Kibana
Open:
http://localhost:5601
Go to:
Stack Management → Data Views
Create Data View:
filebeat-*
Select:
@timestamp
Go to:
Analytics → Discover
Select filebeat-* data view
You will now see Nginx logs in real time.

🧪 Generate Test Logs
Run:
curl http://localhost/
curl http://localhost/favicon.ico
Refresh Kibana to see new log entries.


📈 Example Visualizations
Using Kibana Lens, you can create:
Requests per minute
HTTP status code breakdown (200 vs 404)
Top requested URLs
Error trends
Traffic spike monitoring

🛑 Stop the Stack
Stop containers:
docker compose down
Remove containers and volumes:
docker compose down -v

💡 Features
Fully containerized setup
Secure Elasticsearch (xpack enabled)
Real-time Nginx log monitoring
Centralized logging pipeline
Modular structure
Resume-ready DevOps project

📚 Learning Outcomes
This project demonstrates:
Docker networking & volume mapping
ELK stack configuration
Log shipping with Filebeat
Log indexing with Elasticsearch
Log visualization with Kibana
Troubleshooting containerized systems

🔮 Future Improvements
Add alerting (404/500 threshold)
Export and include ready-made dashboards
Integrate Logstash for advanced parsing
Deploy to cloud VM (AWS/GCP/Azure)
Add CI/CD pipeline
