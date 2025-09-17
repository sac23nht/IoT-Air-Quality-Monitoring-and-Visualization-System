# 🌍 IoT Air Quality Monitoring and Visualization System  

**Technologies:** Node-RED, InfluxDB, Grafana, Open Meteo API, Time-Series Database, Data Visualization, MQTT (optional)  

---

## 📌 Project Overview  

This project implements a robust **Internet of Things (IoT) system** designed for **real-time monitoring and visualization of air quality data** in five major German cities: **Berlin, Munich, Dresden, Essen, and Zwickau**.  

The solution integrates **data ingestion, processing, storage, and visualization** layers using open-source tools to deliver actionable environmental insights.  

- Data is collected (simulated or from live APIs) and processed using **Node-RED**, enabling flexible and scalable data automation.  
- Processed air quality data—covering **PM10, PM2.5, CO, CO2, CH4, Dust, and UV Index**—is stored in a time-series optimized database, **InfluxDB**, ensuring efficient storage and querying.  
- **Grafana dashboards** provide a comprehensive, user-friendly interface with multiple visualization types, all color-coded for quick interpretation of air quality levels.  

This modular design shows how open-source IoT and visualization tools can empower communities and policymakers with **data-driven environmental insights**.  

---
## 📌 Complete Dashboard
<img width="1077" height="378" alt="image" src="https://github.com/user-attachments/assets/a83787f5-7a8f-49a2-9bb8-4d379194d2b5" />
<img width="1079" height="328" alt="image" src="https://github.com/user-attachments/assets/350c6cdf-747b-4229-9185-5bb6ee8353df" />
<img width="1079" height="414" alt="image" src="https://github.com/user-attachments/assets/f7ac2b74-b977-4770-87c0-96e40a247cea" />



## ⚙️ Data Collection & Processing  

To collect weather and air quality data, a workflow was first designed for a **single city** in **Node-RED**, then replicated for all five cities.  

The **Node-RED workflow** retrieves air quality data from the **Open Meteo API**, processes it, and stores the results in **InfluxDB**.  

### Workflow Structure  

- **Inject Node** → Triggers data retrieval every 1 hour  
- **HTTP Request Node** → Fetches live data from API using:  
https://air-quality-api.open-meteo.com/v1/air-quality?latitude={LAT}&longitude={LON}{PARAMS}

- **Function Process Data Node** → Parses pollutants (PM10, PM2.5, CO2, CO, CH4, Dust, UV Index)  
- **Change Node** → Maps `msg.payload.timestamp` → `global.timestamp` with deep copying for time accuracy  
- **Function Prepare Data for Influx Node** → Converts parsed data into the InfluxDB structure  
- **InfluxDB Node** → Stores the air quality metrics into the time-series database  

## 📌 Node-RED Workflow- Fetch Data of 5 Cities 
<img width="602" height="462" alt="image" src="https://github.com/user-attachments/assets/40832b2d-53cc-4b01-95ba-cbee805fa0b5" />

## 📌 Node-RED Workflow- Fetch Live Air Quality Data of a City 
<img width="517" height="218" alt="image" src="https://github.com/user-attachments/assets/bfa26a9a-7bf4-435f-9783-6fcd03b26b29" />

---
## 📌 Storing Data in InfluxDB
<img width="511" height="259" alt="image" src="https://github.com/user-attachments/assets/3b0d19b2-5778-40c4-af11-b96857c4948a" />

 Through the Influx Out node, we send the data to InfluxDB, where it is stored. As shown in the (Figure 3), the data is organized inside its respective bucket in InfluxDB. We have all
 the previous mentioned weather indicators stored for each city.



## 🌍 Cities Monitored  

| City     | Latitude | Longitude | Key Characteristics       |  
|----------|----------|-----------|---------------------------|  
| Berlin   | 52.5244  | 13.4105   | Generally good            |  
| Munich   | 48.1374  | 11.5755   | Usually good              |  
| Dresden  | 51.0509  | 13.7383   | Variable, often good      |  
| Essen    | 51.4566  | 7.0123    | Industrial influence      |  
| Zwickau  | 50.7272  | 12.4884   | Generally good            |  

---

## ✨ Features and Highlights  

- **Flexible Data Collection & Processing** – Node-RED flows for seamless ingestion from APIs or simulated sensors  
- **Efficient Time-Series Storage** – InfluxDB for storing timestamped data at scale  
- **Rich, Interactive Dashboards** – Grafana dashboards with multiple chart types  
- **Color-Coded Air Quality Indicators** – (Green = Good, Yellow = Moderate, Red = Unhealthy)  
- **Geographical Contextualization** – City mapping with markers and location-based data  
- **Real-Time & Historical Views** – Dashboards refresh hourly, with 48-hour forecast trends  
- **Scalability & Extensibility** – Easy to add more sensors, cities, or parameters  

---

## 🛠️ Technologies Used  

| Technology   | Purpose |  
|--------------|---------|  
| **Node-RED** | Visual programming tool for designing data ingestion, transformation, and automation flows |  
| **InfluxDB** | High-performance time-series database optimized for sensor/telemetry data |  
| **Grafana**  | Dashboard platform for time-series data visualization |  
| **Open Meteo API** | Provides weather & air quality metrics (simulated or supplementary data) |  
| **MQTT** *(optional)* | IoT messaging protocol for real-time sensor integration |  

---

## 📊 Visualizations Included  

- **Geographical Map** → City markers with coordinates  
- **Time-Series Graphs** → Hourly PM10 & PM2.5 trends  
- **Bar Charts** → CO2 averages per city  
- **Heatmaps** → Dust concentration patterns  
- **Gauge Panels** → Real-time pollutant levels (color-coded)  
- **Stat Graphs** → CO concentration with thresholds  
- **Pie Charts** → UV Index distribution across cities  
- **Histograms** → Methane concentration levels  

---

## ✅ Project Outcomes  

- Built a **scalable IoT pipeline** from data ingestion → processing → storage → visualization  
- Developed **intuitive Grafana dashboards** for technical & non-technical users  
- Enabled **clear communication** of complex environmental data with color-coded alerts  
- Delivered a **proof of concept** for IoT-based environmental monitoring  
- Provided **insights into geographic/environmental factors** influencing air quality  

---

## 🚀 Future Enhancements  

- Integration with **live IoT sensors** via MQTT  
- Addition of **weather overlays** (temperature, humidity, wind)  
- Incorporation of **ML models** for pollution forecasting & anomaly detection  
- Expansion to more cities and environmental parameters  

---

## ▶️ Getting Started  

### Prerequisites  
- Node.js and Node-RED installed  
- InfluxDB server running  
- Grafana installed and configured  
- Access to Open Meteo API or another data source  

### Setup Instructions  
1. Clone the repository  
2. Import Node-RED flows from `/flows` directory  
3. Configure InfluxDB connection parameters in Node-RED & Grafana  
4. Import Grafana dashboard JSON files  
5. Run Node-RED to start ingestion and processing  
6. Open Grafana to view live dashboards  

---

## 📜 License  

This project is **open-source** and available under the **MIT License**.  

---

## 👥 Authors  

- Kandanoor Deepika Sahi  
- Ravula Srikar Reddy  
- Saijaya Chilekampalli  

---

## 📖 References  

- [Open-Meteo API](https://open-meteo.com)  
- [Node-RED Documentation](https://nodered.org/docs/)  
- [InfluxDB Documentation](https://docs.influxdata.com/influxdb/)  
- [Grafana Documentation](https://grafana.com/docs/)  
