Maps API Testing with SOAP UI
This repository contains a SOAP UI project for testing the REST APIs provided by Rahul Shetty Academy. The project focuses on end-to-end (E2E) testing of the Maps API, covering operations like adding, retrieving, updating, and deleting a place.
Project Overview
The project is built using SOAP UI (version 5.8.0) and tests the following REST API endpoints:

POST /maps/api/place/add/json: Adds a new place with details like location, name, and address.
GET /maps/api/place/get/json: Retrieves details of a place using its place_id.
PUT /maps/api/place/update/json: Updates the address of an existing place.
DELETE /maps/api/place/delete/json: Deletes a place using its place_id.

The test suite includes a test case (HappyPath) that performs an E2E flow:

Adds a place and verifies the response contains a place_id and status "OK".
Retrieves the place using the place_id and verifies the name.
Deletes the place and verifies the operation’s success.

Prerequisites
To run this project, you need:

SOAP UI: Version 5.8.0 or higher (download from SoapUI).
API Key: The project uses the API key qaclick123 for Rahul Shetty Academy’s Maps API.
Internet Connection: To access the API at https://rahulshettyacademy.com.

Setup Instructions

Clone the Repository:git clone https://github.com/yourusername/Maps-API-Testing-SOAPUI.git


Open SOAP UI:
Launch SOAP UI on your machine.
Import the project by selecting File > Import Project and choosing maps-API-soapui-project.xml.


Configure the Endpoint:
Ensure the endpoint is set to https://rahulshettyacademy.com.
Verify the API key (qaclick123) in the request parameters.


Run the Test Suite:
Open the E2ETesting test suite and run the HappyPath test case.
Review the assertions to ensure the API responses are as expected.



Test Case Details

Add Place:
Sends a POST request with a JSON payload to add a place.
Assertions:
Checks for HTTP 200 status.
Verifies the response contains "OK".
Ensures place_id exists in the response.
Uses a Groovy script to store the place_id for subsequent requests.




Get Place:
Sends a GET request using the stored place_id.
Assertion: Verifies the place name is "Backline house".


Delete Place:
Sends a DELETE request using the stored place_id.
Assertion: Checks for "OK" in the response.



Notes

The project uses a hardcoded place_id in some requests. Ensure the place_id is dynamically captured from the POST response for accurate E2E testing.
The Groovy scripts in assertions parse JSON responses and validate specific fields.
If you encounter endpoint errors, verify the URL (https://rahulshettyacademy.com) and API key.

Contributing
Feel free to fork this repository, make improvements, and submit pull requests. Suggestions for additional test cases or optimizations are welcome!
License
This project is licensed under the MIT License.
