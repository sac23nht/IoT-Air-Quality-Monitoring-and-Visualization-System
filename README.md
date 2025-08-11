# IoT Air Quality Monitoring and Visualization System  
**Technologies:** Node-RED, InfluxDB, Grafana, Open Meteo API, Time-Series Database, Data Visualization, MQTT (optional)
<img width="669" height="244" alt="image" src="https://github.com/user-attachments/assets/3ef62cf9-7d48-41b2-b6f2-e6bcb4ea622b" />
<img width="664" height="252" alt="image" src="https://github.com/user-attachments/assets/0dbad5ef-831c-48a8-8ba0-6968385e655c" />



## Project Overview
This project implements a robust Internet of Things (IoT) system designed for real-time monitoring and visualization of air quality data in five major German cities: Berlin, Munich, Dresden, Essen, and Zwickau. The solution integrates data ingestion, processing, storage, and visualization layers using open-source tools to deliver actionable environmental insights.

Data is collected (simulated or from live APIs) and processed using **Node-RED**, which enables flexible and scalable data flow automation. The processed air quality data—covering key parameters such as particulate matter (PM10 & PM2.5), carbon monoxide (CO), carbon dioxide (CO2), methane (CH4), dust, and UV Index—is stored in a time-series optimized database, **InfluxDB**. This ensures efficient storage and rapid querying of time-dependent sensor data.

For data visualization, **Grafana** dashboards provide a comprehensive, user-friendly interface that incorporates various chart types: time-series graphs, bar charts, heatmaps, gauges, pie charts, and geographical maps. The dashboards employ a consistent color-coded system to categorize air quality status (Good, Moderate, Unhealthy), enabling quick interpretation by users of all technical backgrounds.

This modular and scalable design demonstrates how open-source IoT and visualization tools can be leveraged for environmental monitoring, helping communities and policymakers make data-driven decisions.

---

## Features and Highlights

- **Flexible Data Collection and Processing:** Utilizes Node-RED flows for seamless ingestion of air quality data, enabling easy integration with live APIs or simulated data sources.
- **Efficient Time-Series Storage:** Employs InfluxDB to store large volumes of timestamped data with high performance and scalability, supporting long-term environmental data analysis.
- **Rich, Interactive Dashboards:** Grafana dashboards feature multi-type visualizations tailored to each pollutant, providing insightful comparisons across five cities and time frames.
- **Color-Coded Air Quality Indicators:** Visual signals (green, yellow, red) based on pollutant thresholds facilitate immediate understanding of air quality status for non-technical users.
- **Geographical Contextualization:** Mapping of cities with location markers links pollution data to spatial factors, enhancing environmental analysis with local geographic influences.
- **Real-Time and Historical Views:** Dashboards update hourly, allowing users to track real-time changes and study pollutant trends over a 48-hour forecast period.
- **Scalability and Extensibility:** Modular Node-RED workflows and InfluxDB’s time-series model make the system easily extendable for additional sensors, cities, or parameters.

---

## Technologies Used

| Technology | Purpose |
|------------|---------|
| **Node-RED** | Visual programming tool for designing data ingestion, transformation, and automation flows. Handles data routing from APIs/sensors to database. |
| **InfluxDB** | High-performance time-series database optimized for storing sensor and telemetry data efficiently. Supports complex queries for analysis. |
| **Grafana** | Powerful open-source dashboard platform for visualizing time-series data with interactive graphs, charts, and maps. |
| **Open Meteo API** | Provides weather and environmental data, used here to simulate or supplement air quality metrics. |
| **MQTT** *(optional)* | Messaging protocol for IoT device communication (if live sensors are integrated). |

---

## Visualizations Included

- **Geographical Map:** Displays monitoring stations for the five cities with clickable markers showing coordinates.
- **Time-Series Graphs:** Hourly trends of PM10 and PM2.5 particulate matter for all cities, with color coding by city.
- **Bar Charts:** Average carbon dioxide levels per city over selected periods.
- **Heatmaps:** Dust concentration patterns across cities and time.
- **Gauge Panels:** Real-time PM10 levels with color-coded thresholds for each city.
- **Stat Graphs:** Current and peak carbon monoxide concentrations with safety thresholds.
- **Pie Charts:** UV Index distribution among the cities showing proportional exposure.
- **Histograms:** Methane concentration levels compared across the five cities.

---

## Project Outcomes

- **Validated data flow pipeline** from acquisition through Node-RED to storage in InfluxDB.
- **Functional, intuitive Grafana dashboards** that provide multi-parameter air quality insights in near real-time.
- **Clear visual communication** of complex environmental data using color-coded alerts and diverse chart types.
- **Proof of concept for scalable IoT environmental monitoring** with potential for future expansion.
- **Insights into geographic and environmental factors** influencing air quality, facilitating better urban planning and public health policies.

---

## Future Enhancements

- Integration of **live sensor networks** via MQTT for real-time physical monitoring.
- Addition of **weather data overlays** (temperature, humidity, wind) for deeper analysis.
- Incorporation of **machine learning** models for pollution forecasting and anomaly detection.
- Expansion to cover more cities and additional air quality parameters.

---

## Getting Started

### Prerequisites

- Node.js and Node-RED installed
- InfluxDB server running
- Grafana installed and configured
- Access to Open Meteo API or other data sources

### Setup Instructions

1. Clone the repository.
2. Import Node-RED flows from `/flows` directory.
3. Configure InfluxDB connection parameters in Node-RED and Grafana.
4. Import provided Grafana dashboard JSON files.
5. Run Node-RED to start data ingestion and processing.
6. Open Grafana to view live dashboards.

---

## License
This project is open-source and available under the MIT License.

---

## Authors
- Kandanoor Deepika Sahi  
- Ravula Srikar Reddy  
- Saijaya Chilekampalli  

---

## References
- [Open-Meteo API](https://open-meteo.com)  
- [Node-RED Documentation](https://nodered.org/docs/)  
- [InfluxDB Documentation](https://docs.influxdata.com/influxdb/)  
- [Grafana Documentation](https://grafana.com/docs/)  
