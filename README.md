# VibeVisor

## Description
**VibeVisor** is a sentiment analysis application developed using embedded Watson AI libraries. This project demonstrates how to analyze the sentiment of a given text and provides a comprehensive solution that includes running unit tests, performing static code analysis, and deploying the application as a web service using the Flask framework. VibeVisor is designed to process text input and deliver a formatted output that reflects the sentiment conveyed in the text.

## Features
- **Sentiment Analysis**: Uses the Watson NLP library to analyze and determine the sentiment of the provided text.
- **Formatted Output**: Processes and formats the sentiment analysis results for easy interpretation.
- **Unit Testing**: Includes unit tests to ensure the application performs as expected.
- **Static Code Analysis**: Performs static code analysis to maintain code quality and adherence to best practices.
- **Web Deployment**: Deploys the application as a web service using the Flask framework.
- **Error Handling**: Incorporates error handling to manage potential issues during execution.

## Installation

### Prerequisites
- Python 3.7 or higher
- Watson NLP API credentials

### Steps
1. **Clone the Repository:**
   ```bash
   git clone https://github.com/your-username/VibeVisor.git
   cd VibeVisor

2. **Set Up a Virtual Environment:**

    Create and activate a Python virtual environment:

        python -m venv env
        source env/bin/activate  # On Windows use `env\Scripts\activate`

3. **Install Required Libraries:**

    Install the necessary Python packages:

        pip install -r requirements.txt

4. **Set Up Environment Variables:**

    Create a .env file in the project root directory and add your Watson NLP API credentials:

        WATSON_API_KEY=your_watson_api_key_here
        WATSON_URL=your_watson_service_url_here

5. **Run Unit Tests:**

    Execute unit tests to ensure the application is functioning correctly:

        python -m unittest discover tests

6. **Perform Static Code Analysis:**

    Run static code analysis tools to check for code quality and adherence to best practices:

        pylint server.py

7. **Run the Application:**

    Start the Flask web application:

        flask run

8. **Access the Application:**

    Open your web browser and navigate to http://localhost:5000 to interact with the VibeVisor sentiment analysis tool.

## Usage

1. **Enter Text:** Input the text you wish to analyze in the provided field.
2. **Analyze Sentiment:** Click the "Analyze" button to submit the text for sentiment analysis.
3. **View Results:** The application will display the sentiment of the text, indicating whether the sentiment is positive, negative, or neutral.

## Example Code

Here’s an example of how the sentiment analysis function is implemented:

from watson_developer_cloud import NaturalLanguageUnderstandingV1
from watson_developer_cloud.natural_language_understanding_v1 import Features, SentimentOptions

    def analyze_sentiment(text):
        nlu = NaturalLanguageUnderstandingV1(
            version='2021-08-01',
            iam_apikey=os.getenv('WATSON_API_KEY'),
            url=os.getenv('WATSON_URL')
        )
        response = nlu.analyze(
            text=text,
            features=Features(sentiment=SentimentOptions())
        ).get_result()
        
        sentiment = response['sentiment']['document']['label']
        return sentiment

## Deployment

VibeVisor is deployed as a Flask web application, making it accessible over the web. The application can be hosted on any platform that supports Flask.


## License
This project is licensed under the MIT License. See the LICENSE file for more information.
