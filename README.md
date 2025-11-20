# StateLens: US State Comparison Tool

## Project Goal
StateLens is a comparative analytics tool designed to help users considering relocation by providing a fast, side-by-side analysis of two US states across critical factors: **Average Rent, Cost of Living (CoL) Score, Crime Rate, and Weather.**

This project focuses on demonstrating foundational software engineering skills, particularly **system architecture design, data structure optimization, and cloud service integration** (AWS S3 & ElastiCache concepts).

##  Key Architectural Features

This application showcases a tiered data retrieval strategy designed for speed and cost-efficiency:

1.  **High-Speed Caching (Python & ElastiCache):** Before hitting an external API, the application first checks the **in-memory Dictionary** and the **ElastiCache layer**. This provides $O(1)$ lookup time for frequently requested states, minimizing latency and external service costs.
2.  **Data Persistence (AWS S3):** Once data is retrieved from the external API, a raw copy is archived in an **AWS S3 bucket**. This ensures permanent persistence, allowing the application to function using backup data if the external API is unavailable or rate-limited.
3.  **Data Structure Optimization:**
    * **Dictionaries (Hash Maps):** Utilized for the primary **caching layer** due to their fast key-value lookup capabilities.
    * **Binary Search Trees (BST):** Planned implementation to sort state profiles by **Cost of Living Score**. This allows for quick, efficient traversal and filtering of states that fall within a user's defined budget.

---

## System Architecture Diagram

This diagram visually represents the data flow, from the user interface to the persistent cloud storage layer.

[View Live System Diagram](https://www.mermaidchart.com/d/b7cf9b5f-ff32-405e-867d-0c968ad4838d)

##  Tech Stack & Dependencies

* **Backend Framework:** Python / Flask
* **APIs:** Placeholder simulation (`requests` library will be used for actual API calls)
* **Data Structures:** Dictionary (Cache), Binary Search Tree (Sorting)
* **Cloud Concepts:** AWS S3 (Persistence), AWS ElastiCache (Caching)
* **Frontend:** HTML5, CSS3

##  Setup and Local Development

### Prerequisites
* Python 3.8+
* `pip` (Python package installer)

### Installation
1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/YourUsername/StateLens.git](https://github.com/YourUsername/StateLens.git)
    cd StateLens
    ```

2.  **Create and Activate a Virtual Environment (Recommended):**
    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Run the Application:**
    ```bash
    python app.py
    ```

The application will now be running on `http://127.0.0.1:5000/`.
