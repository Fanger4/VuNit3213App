NIT3213 Android Application Development Project Project Overview This Android application demonstrates proficiency in API integration, user interface design, and adherence to Android development best practices. The app includes three primary screens: Login, Dashboard, and Details, which interact with the vu-nit3213-api to authenticate users and retrieve relevant data.

Features Login Screen:

Simple login interface where the user enters their first name as the username and their student ID (format: s12345678) as the password. Authentication through the API endpoint for the respective class location (/footscray/auth, /sydney/auth, or /ort/auth). Handles error responses and displays appropriate error messages. Dashboard Screen:

Displays a list of entities from the API in a RecyclerView. Uses the keypass returned from the login request to authenticate the data retrieval. Each item in the RecyclerView shows basic information (excluding the description) with click functionality to view more details. Details Screen:

Displays the full details of the selected entity, including a detailed description. Presents the data in a user-friendly layout.

API Information Base URL: https://vu-nit3213-api.onrender.com

Login Endpoint:

URL: /footscray/auth, /sydney/auth, or /ort/auth depending on class location. Method: POST

Request Body: json

{ "username": "shrey", "password": "s8073324" } Successful Response: json Copy code { "keypass": "topicName" } Dashboard Endpoint:

URL: /dashboard/{keypass} Method: GET Successful Response: json Copy code { "entities": [ { "property1": "value1", "property2": "value2", "description": "Detailed description" } ], "entityTotal": 7 } How to Build and Run the Application Prerequisites Android Studio installed on your machine. Minimum SDK: 23 (Android 6.0, Marshmallow). Internet permission must be added to AndroidManifest.xml: xml Copy code Build Instructions Clone the repository:

bash

git clone Open the project in Android Studio.

Sync Gradle to ensure all dependencies are downloaded.

Run the project:

Select the device/emulator. Click the "Run" button in Android Studio. Dependency Injection This project uses Hilt for Dependency Injection.

Hilt is integrated for managing dependencies across ViewModels and other app components. Ensure that all necessary Hilt modules and components are properly configured.

Testing

Unit tests are written for critical components, such as ViewModels. To run the unit tests, execute:

bash ./gradlew test

Git Usage Meaningful commit messages have been used throughout the project. Git history reflects the progress and changes made during development. Project Structure The project follows the MVVM architecture with clearly defined layers for UI, ViewModels, and data repositories. Each component adheres to clean code principles for maintainability and readability.

Future Improvements Add more UI/UX improvements such as animations and enhanced error handling. Extend functionality by integrating additional endpoints.

License This project is developed as part of the NIT3213 Android Application Development course and is not meant for distribution.
