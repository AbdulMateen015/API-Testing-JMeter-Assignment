# API CRUD Testing with JMeter

## Project Overview
This project is an automated API test plan created using **Apache JMeter**. It tests the full CRUD (Create, Read, Update, Delete) lifecycle against the JSONPlaceholder fake API.

## Assignment Details
* **Assignment:** No. 5 – API Testing with JMeter
* **Tools Used:** Apache JMeter 5.6.3
* **Target API:** [https://jsonplaceholder.typicode.com](https://jsonplaceholder.typicode.com)

## Features
* **CRUD Workflow:** Automates the cycle of POST -> GET -> PATCH -> DELETE -> GET (Verify).
* **Data Driven:** Uses a CSV file (`userData.csv`) to dynamically create users.
* **JSON Extraction:** Dynamically captures the `id` of created users for subsequent requests.
* **Assertions:** Validates HTTP Status codes (handles 200, 201, 204, and 404).

## Files in this Repository
1.  **`API CRUD Testing Project.jmx`**: The main JMeter test script.
2.  **`userData.csv`**: The data file containing test users (Title, Body, UserID).
3.  **`create_user_payload.json`**: Reference JSON structure for POST requests.

## How to Run This Test
1.  **Clone the repository:**
    ```bash
    git clone https://github.com/AbdulMateen015/API-Testing-JMeter-Assignment.git
    ```
2.  **Open JMeter:**
    * Launch Apache JMeter.
    * Go to **File > Open** and select `API CRUD Testing Project.jmx`.
3.  **Verify Data File:**
    * Ensure `userData.csv` is in the same folder as the `.jmx` file.
4.  **Run:**
    * Click the **Green Play Button** (Start).
    * View results in the "View Results Tree" listener.

## Test Scenarios Covered
| Method | Endpoint | Description | Expected Result |
| :--- | :--- | :--- | :--- |
| **POST** | `/posts` | Create a new user from CSV data | `201 Created` |
| **GET** | `/posts/{id}` | Retrieve the created user | `404` (Mock API behavior) |
| **PATCH** | `/posts/{id}` | Update the user's title/body | `200 OK` |
| **DELETE** | `/posts/{id}` | Delete the user | `200 OK` |
| **GET** | `/posts/{id}` | Verify deletion | `404 Not Found` |
