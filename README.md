# Assignment2-Zeotap-Springboot

Weather Monitoring System

Overview
This project is a real-time data processing system designed to monitor weather conditions and provide summarized insights using rollups and aggregates. The system continuously retrieves weather data from the OpenWeatherMap API for major Indian metros (Delhi, Mumbai, Chennai, Bangalore, Kolkata, Hyderabad) and performs data analysis to generate daily summaries and alerts based on user-configurable thresholds.

Features

Real-time weather data retrieval

Temperature conversion (Kelvin to Celsius/Fahrenheit)

Daily weather summaries with averages, max, min, and dominant conditions

User-configurable alert thresholds

Visualization of weather summaries, historical trends, and alerts

Tools and Technologies
Spring Boot: Backend framework

SQL Database: Database for storing weather data and summaries

Java: Programming language

OpenWeatherMap API: Source of real-time weather data

HTML, CSS, JavaScript: Frontend visualization

Getting Started
Prerequisites
Java 8 or higher

Maven

SQL Database (e.g., MySQL, PostgreSQL)

Installation
Clone the repository:

sh

Copy
git clone https://github.com/yourusername/weather-monitoring-system.git
cd weather-monitoring-system
Set up the SQL Database:

Ensure your SQL database is installed and running.

Create a database named weather (or another name of your choice).

Create tables for storing weather data and summaries:

sql

Copy
CREATE TABLE weather_data (
    id INT AUTO_INCREMENT PRIMARY KEY,
    main VARCHAR(255),
    temp DOUBLE,
    feels_like DOUBLE,
    dt BIGINT,
    city VARCHAR(255)
);

CREATE TABLE weather_summaries (
    id INT AUTO_INCREMENT PRIMARY KEY,
    city VARCHAR(255),
    avg_temp DOUBLE,
    max_temp DOUBLE,
    min_temp DOUBLE,
    dominant_condition VARCHAR(255),
    date DATE
);
Configure application.properties: Modify src/main/resources/application.properties to match your SQL database setup:

properties

Copy
spring.datasource.url=jdbc:mysql://localhost:3306/weather
spring.datasource.username=your_db_username
spring.datasource.password=your_db_password
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
openweathermap.api.key=YOUR_API_KEY
Build and run the application:

sh

Copy
mvn clean install
mvn spring-boot:run
Open the application:

Navigate to http://localhost:8080 in your web browser.

Usage
Creating a Rule
Open the application.

Enter a rule string in the input field (e.g., ((age > 30 AND department = 'Sales') OR (age < 25 AND department = 'Marketing')) AND (salary > 50000 OR experience > 5)).

Click the "Create" button.

Viewing All Rules
The home page displays a list of all existing rules.

Evaluating Rules
Implement the evaluate_rule function to check a user's eligibility based on the defined rules.

API Endpoints
GET /: Home page, displays the form and list of rules.

POST /api/rules/create: Creates a new rule.

Request Body: { "ruleString": "((age > 30 AND department = 'Sales') OR (age < 25 AND department = 'Marketing')) AND (salary > 50000 OR experience > 5)" }

GET /api/rules/all: Retrieves all rules.

GET /api/rules/{id}: Retrieves a rule by ID.

DELETE /api/rules/{id}: Deletes a rule by ID.

Example Data
Sample SQL data for weather summaries:

sql

Copy
INSERT INTO weather_data (main, temp, feels_like, dt, city) VALUES 
('Clear', 298.15, 298.15, 1618291200, 'Delhi'),
('Rain', 297.15, 297.15, 1618291200, 'Mumbai'),
('Clouds', 299.15, 299.15, 1618291200, 'Chennai'),
('Clear', 300.15, 300.15, 1618291200, 'Bangalore'),
('Rain', 296.15, 296.15, 1618291200, 'Kolkata'),
('Clouds', 295.15, 295.15, 1618291200, 'Hyderabad');
Contributing
Contributions are welcome! Please open an issue or submit a pull request with any improvements or fixes.

License
This project is licensed under the MIT License - see the LICENSE file for details.

This README should provide clear instructions and details for setting up and running your weather monitoring system with an SQL database. Customize it to better fit your project's specifics as needed! 🚀
