# NLP-based Score Calculator for Job Applications

This repository contains a Flask web application for scoring job applications using Natural Language Processing (NLP). It evaluates candidate responses based on similarity to ideal answers.

## Overview

The application processes user-provided data from job applications and calculates scores for different sections of the application. It compares the user input to predefined ideal answers using cosine similarity to generate scores.

## Features

- Parses user input from job applications
- Calculates similarity scores for different sections (previous positions, aptitude, volunteering experiences, and what would you do differently)
- Stores scores in Firebase Firestore
- Provides JSON response with scores and success message

## Setup

### Prerequisites

- Python 3.x
- Flask
- spaCy
- numpy
- Firebase Admin SDK

### Installation

1. Clone the repository:

    ```bash
    https://github.com/amankappooresabu/Natural-language-processing.git
    ```

2. Install dependencies:

    ```bash
    pip install -r requirements.txt
    ```

3. Set up Firebase:

    - Create a Firebase project at [Firebase Console](https://console.firebase.google.com/)
    - Generate a service account key file for your Firebase project
    - Place the service account key file in the root directory of the project

4. Run the application:

    ```bash
    python app.py
    ```

## Usage

- Send a POST request to `/submit` with JSON data containing job application details. 
- The application will process the data, calculate scores, and store them in Firebase.
- You will receive a JSON response with the calculated scores.

### Example Request

```json
{
  "identifier": "user@example.com",
  "previousPositions": "Web Developer at X Company",
  "aptitude": "I'm a quick learner and have good problem-solving skills.",
  "volunteering": "I volunteered at Y organization where I managed their website.",
  "whatWouldYouDoDifferently": "I would focus more on teamwork and innovation."
}
