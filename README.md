# DevOps Challenge - Weather Dashboard

Building a weather data collection system using AWS S3 and OpenWeather API

# Weather Data Collection System - DevOps Week 1 Challenge

## Project Overview
This project is a Weather Data Collection System that demonstrates core DevOps principles by combining:
- External API Integration (OpenWeather API)
- Cloud Storage (AWS S3)
- Infrastructure as Code
- Version Control (Git)
- Python Development
- Error Handling
- Environment Management

## Architecture Overview

<img src="https://i.imgur.com/pRq2G11.png"/>

## Features
- Fetches real-time weather data for multiple cities
- Displays temperature (°C), humidity, and weather conditions
- Automatically stores weather data in AWS S3
- Supports multiple cities tracking
- Timestamps all data for historical tracking

## Technical Architecture
- **Language:** Python 3.x
- **Cloud Provider:** AWS (S3)
- **External API:** OpenWeather API
- **Dependencies:** 
  - boto3 (AWS SDK)
  - python-dotenv
  - requests
 
## Project Prerequisites
- Python script for Weather Dashboard
- Basic knowledge of AWS Services, S3 and IAM
- AWS Access Key and Secret Key
- OpenWeatherAPI Key (Account needs to be created: https://home.openweathermap.org/users/sign_in)
- IDE (I used Visual Studio Code)

## Project Walkthrough - Step 1: Create Directories and Files in Local Environment
- Using (git) bash in VS Code terminal I created 3 directories with the names data, src and tests. Our src folder holds all of our main code which will drive the process. The tests folder is for unit testing, DevOps best practices. And the data folder is for local storage when doing development testing.  
<img src="https://i.imgur.com/pMo0JBT.png)"/>
<img src="https://i.imgur.com/ajqZIbZ.png)"/>

- Next I created __init__.py and weather_dashboard.py files in the src directory. The init file makes our directory a python package and allows imports between different files. The weather_dashboard.py is our python script which will drive the process.
<img src="https://i.imgur.com/x3ebQh5.png)"/>
<img src="https://i.imgur.com/tR54dDK.png)"/>

- Final step for the project (directory) structure I created a requirements.txt, README.md and .env file in the root directory. The requirements text file details everything required to run this Project. 
<img src="https://i.imgur.com/ohVaD88.png)"/>
<img src="https://i.imgur.com/p6EFZJM.png)"/>

```markdown
## Project Structure
weather-dashboard/
  src/
    __init__.py
    weather_dashboard.py
  tests/
  data/
  .env
  .gitignore
  requirements.txt

## What I Learned

AWS S3 bucket creation and management
Environment variable management for secure API keys
Python best practices for API integration
Git workflow for project development
Error handling in distributed systems
Cloud resource management

## Future Enhancements

Add weather forecasting
Implement data visualization
Add more cities
Create automated testing
Set up CI/CD pipeline
