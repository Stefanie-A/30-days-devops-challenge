## DAY 1: WEATHER DATA COLLECTION SYSTEM USING OpenWeather API And AWS S3.

### Overview
The Weather Data Collection System is a project designed to fetches and store weather data from OpenWeather API. The data is retrieved for specified locations and stored in an AWS S3 bucket.

### Features

- Fetches real-time weather data using the OpenWeather API.

- Dynamically generates unique AWS S3 bucket names for data storage.

- Stores weather data in JSON format in S3 for easy retrieval and analysis.

- Supports multiple cities and periodic data collection through automation.

### Prerequisites

To set up and run this project, ensure you have the following:

- AWS Account: For creating and managing S3 buckets.

- OpenWeather API Key: Sign up at OpenWeather to get an API key.

- Environment Setup:

  -    Python 3.x

  -  AWS CLI configured with your credentials.

  - Required Python libraries (see below).

## Installation

1. Clone the repository:

```
git clone https://github.com/Stefanie-A/30-days-devops-challenge.git
cd weather-dashboard
```

2. Install dependencies:
```
pip install -r requirements.txt
```

3. Set up your environment variables in a .env file:
```
OPENWEATHER_API_KEY=your_openweather_api_key
AWS_BUCKET_NAME=your_aws_bucket_name
```
4. Ensure AWS CLI is configured:
```
aws configure
```
### Usage

Collect Weather Data

Run the script to fetch and store weather data:
```
python weather_data.py
```
Example Output

Data will be saved in the S3 bucket in the following structure:
```
Fetching weather for New York...
Temperature: 26.06°F
Feels like: 13.46°F
Conditions: clear sky
Successfully saved data for New York to S3
Weather data for New York saved to S3!
```
File Structure
```
weather-dashboard/
  src/
    __init__.py
    weather_dashboard.py
  tests/
  data/
  .env
  .gitignore
  requirements.txt
```
AWS S3 Bucket Naming

The bucket name is dynamically generated using the prefix defined in the .env file and a random suffix. It must be a globally unique name. Example:

weather-data-12345

### Dependencies

Install the following Python libraries:

boto3: AWS SDK for Python

requests: To make HTTP API requests

python-dotenv: For environment variable management

### Deployment

You can deploy this project to AWS Lambda or run it on an EC2 instance for continuous data collection.

Automate with CRON (Optional)

To periodically collect weather data, schedule the script using CRON or a task scheduler.

### License

This project is licensed under the [MIT License] (LICENSE). See the LICENSE file for details.

### Acknowledgements

OpenWeather API for providing weather data.

AWS S3 for scalable storage solutions.

