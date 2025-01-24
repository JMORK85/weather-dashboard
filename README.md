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
- AWS account with AWS Access Key and Secret Key
- OpenWeatherAPI Key (Account needs to be created: https://home.openweathermap.org/users/sign_in)
- IDE (I use Visual Studio Code)

## Project Walk-through
## Step 1: Create Directories and Files in Local Environment
- Using (git) bash in VS Code terminal I created 3 directories with the names data, src and tests. Our src folder holds all of our main code which will drive the process. The tests folder is for unit testing, DevOps best practices. And the data folder is for local storage when doing development testing.  
<img src="https://i.imgur.com/pMo0JBT.png)"/>
<img src="https://i.imgur.com/ajqZIbZ.png)"/>

- Next I created __init__.py and weather_dashboard.py files in the src directory. The init file makes our directory a python package and allows imports between different files. The weather_dashboard.py is our python script which will drive the process.
<img src="https://i.imgur.com/x3ebQh5.png)"/>
<img src="https://i.imgur.com/tR54dDK.png)"/>

- Final step for the project (directory) structure I created a requirements.txt, README.md and .env file in the root directory. The requirements text file details everything required to run this Project. And the README.md will give an overview of the Project. 
<img src="https://i.imgur.com/ohVaD88.png)"/>
<img src="https://i.imgur.com/p6EFZJM.png)"/>

## Step 2: Initialize GitHub Repo (N.B. Git Bash needs to be installed in your local environment.)
- Using (git) bash in VS Code terminal I initialized an empty Git repository in my local environment with command:
    - $ git init
- Next I had to rename the current branch to 'main' by running the following command:
    - $ git branch -M main (This is commonly used to rename the default branch (master) to main, aligning with the modern naming convention for Git repo's.)
- Next up was completing structure of .gitignore file to let it know what not to track by running the following commands:
    - $ echo ".env" >> .gitignore
    - $ echo "__ pycache __/" >> .gitignore
    - $ echo "*.zip" >> .gitignore
- After this we had to structure our requirements.txt file with the following commands:
    - $echo "boto3==1.26.137" >> requirements.txt (this is the AWS SDK that allows us to talk to AWS using python)
    - $echo "python-dotenv==1.0.0" >> requirements.txt (this manages our environment variables)
    - $echo "requests==2.28.2" >> requirements.txt (this enables us to make https requests to the OpenWeatherAPI)

## Step 3: Install Dependencies
- With Step 2 tasks completed we now have to install our dependencies specified in our requirements.txt file using the following command:
    - $ pip install -r requirements.txt (this uses pip, python package installer, to install dependencies)
 
## Step 4: Environment Setup for AWS and OpenWeatherAPI
- To enable our python script to push data to AWS we configured AWS credentials using the following command:
  - $ aws configure (in git bash)
- This then prompted for AWS credentials as follows:
  - AWS Access Key ID: ************
  - AWS Secret Access Key: ************
  - Default Region: eu-west-2 (London)
  - Output Format: json
- Once you have created an account on OpenWeatherAPI and generated your key, run following command to stash it in your .env file:
  - $ echo "OPENWEATHER_API_KEY=your_api_key_goes_here" >> .env
- Create bucket name in .env file for our AWS S3 bucket using following command:
  - $ echo "AWS_BUCKET_NAME=myweatherdashboardbucket" >> .env

## Step 5: Edit/update weather_dashboard.py script
- Edited the following lines of python script that was provided as part of this project:
  - Updated lines 87 and 88 to print temperature and feels like f-strings in degrees °C instead of °F
    <img src="https://i.imgur.com/MPEmN8T.png)"/>
  - Updated cities variable on line 76 to include UK based cities to track
    <img src="https://i.imgur.com/yH2p3qR.png)"/>
  - Hit Ctrl+S to save changes! 😉

## Step 6: Run weather_dashboard.py script and Output
- To execute the script I ran the following command:
  - $ python3 src/weather_dashboard.py
- My script ran successfully, created my S3 bucket, fetched the weather data from OpenWeatherAPI and saved to my S3 bucket. Terminal output below 😎
  <img src="https://i.imgur.com/N0vlhWE.png)"/>
- And here are screenshots from AWS console showing my S3 bucket (myweatherdashboard), S3 objects and metadata:
  <img src="https://i.imgur.com/Hw2dbpr.png)"/>
  <img src="https://i.imgur.com/I7214qG.png)"/>
  <img src="https://i.imgur.com/eT1OJhv.png)"/>

## PROJECT COMPLETE 👨🏻‍💻✌️

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
