## Real-Time Weather Monitoring System
A real-time weather monitoring application that processes and visualizes weather data with custom alerts, built using Java, Spring Boot, and MySQL. This system aggregates weather information from the OpenWeatherMap API, storing daily summaries and offering threshold-based alerts. The project is containerized for easy deployment.

## Objective
Develop a system to:

Monitor and process real-time weather data.
Summarize daily insights using rollups and aggregates.
Trigger user-defined alerts for specific weather conditions.

## Key Features
Real-Time Data Collection

Retrieves weather data every 5 minutes from OpenWeatherMap API for key Indian cities (Delhi, Mumbai, Chennai, Bangalore, Kolkata, Hyderabad).
Supports dynamic data polling at user-configurable intervals.
Temperature Conversion

Converts Kelvin temperatures to Celsius for display, with an option to integrate Fahrenheit for user preference.
Daily Weather Summaries

Stores and calculates daily aggregates including:
Average, maximum, and minimum temperatures.
Dominant weather condition (based on frequency).
Customizable Alerts

Allows users to set thresholds for weather conditions (e.g., temperature > 35°C).
Alerts can be sent via email for immediate notification.
Data Visualization

Displays historical trends and daily summaries using Thymeleaf and Bootstrap.
Charts for weather trends (temperature, humidity, wind speed).
Dockerized for Deployment

Fully containerized with Docker Compose for easy setup.

Technology Stack
Backend: Java, Spring Boot, Spring Security
Database: MySQL
Frontend: Thymeleaf, Bootstrap
Data Source: OpenWeatherMap API
Visualization: Thymeleaf, Chart.js
Containerization: Docker, Docker Compose
🛠️ Setup & Installation
Prerequisites
JDK 21 or later
Docker & Docker Compose
MySQL
Maven
IntelliJ IDEA
🚀 Local Setup (Recommended for Development)
Clone the Repository

bash
Copy code
git clone https://github.com/yourusername/weather-monitoring-system.git
cd weather-monitoring-system
Configure Database

Ensure MySQL is running, and create a new database:
sql
Copy code
CREATE DATABASE weather_monitoring;
Update application.properties with your MySQL credentials.
Build and Start Application

Clean and package with Maven:
bash
Copy code
mvn clean package
Run the Spring Boot application:
bash
Copy code
mvn spring-boot:run
Access Dashboard

Visit http://localhost:8080/dashboard/dailySummary to view daily summaries, forecasts, and historical data.
🐳 Dockerized Setup (For Production)
Setup Database

Configure MySQL connection details in the Docker Compose file, if required.
Build and Run with Docker Compose

bash
Copy code
docker-compose up
Access Dashboard

Available at http://localhost:8080.
🔗 API Endpoints (Test with Postman)
Daily Summary

GET /weather/dailySummary?date={date}
Weather Forecast

GET /weather/forecast?city={city}
Historical Data

GET /weather/historyData?city={city}&date={date}
✅ Test Cases
System Initialization: Verifies connection to OpenWeatherMap API.
Data Retrieval: Simulates data polling and verifies data parsing.
Temperature Conversion: Tests Kelvin to Celsius (or Fahrenheit) conversions.
Daily Aggregates: Tests daily summaries, including max/min and dominant weather condition.
Threshold Alerts: Simulates data breaches to confirm alert triggers.
🎉 Additional Features
Extended Parameters: Added humidity and wind speed metrics.
Email Notifications: Sends alerts via email for significant weather changes.
