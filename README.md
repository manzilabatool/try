# 📖 RDF-Based Catalog System

## 📐 System Architecture

### **Overview**
The RDF-based catalog system is an integrated platform designed to streamline the ingestion, storage, and visualization of RDF data. It automates data processing through a robust pipeline that handles external files, databases, and live data streams. A user-friendly web interface further enhances interaction by enabling users to query RDF data, manage data sources, and visualize complex data relationships through dynamic RDF graphs. This architecture provides a scalable and interactive solution for comprehensive RDF data management.

---

### **Architecture Diagram**

![Architecture Diagram](path/to/architecture-diagram.png)

*Figure 1: High-Level Architecture of the RDF-Based Catalog System.*

---

## 🔍 Components Breakdown

### **1. Data Integration**
- **Function:** Automates the ingestion of external files, databases, and live streams.
- **Technologies Used:**
  - **Apache Airflow** – Automated Workflow management.
  - **Apache Kafka** – Data streaming.
  - **Apache Spark** – Metadata extraction and transformation.
- **Process:**
  - Data is collected → Processed by Spark → Raw data stored in **Cassandra** → Transformed metadata stored in **GraphDB**.

### **2. Data Storage**
- **Function:** Stores both raw data and processed metadata.
- **Technologies Used:**
  - **Cassandra** – Raw data storage and internal metadata management for system processes.
  - **GraphDB** – RDF metadata storage.

### **3. User Interface**
- **Function:** Web interface for querying and visualizing RDF data.
- **Technologies Used:**
  - **Frontend:** Python, Flask, Pyvis, JavaScript
  - **Backend:** Flask and JavaScript
- **Features:**
  - SPARQL query execution.
  - RDF graph visualization.
  - Database management.

---

## 🛠️ Technology Stack

### **Backend - Service Layer**
The backend service layer is responsible for processing requests from the frontend, managing catalog data, and exposing RESTful APIs to facilitate seamless interaction between system components. It also performs outbound REST requests to external services or databases to retrieve and aggregate data, ensuring the system provides accurate and up-to-date information.

### **Data Integration Technologies**

| **Technology**     | **Purpose**                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| **Airflow**        | Workflow automation tool for ETL processes                                  |
| **Kafka**          | Streaming platform for handling real-time data feeds with high throughput    |
| **Spark**          | Distributed data processing engine for batch and stream processing workloads |
| **Python Wrappers**| Used for integrating relevant libraries in the data integration layer        |

### **Databases**

| **Database**       | **Purpose**                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| **Cassandra**      | Distributed NoSQL database for high scalability and large data volumes       |
| **GraphDB**        | Semantic graph database for knowledge representation and ontology management |

### **Deployment Technologies**

| **Technology**     | **Purpose**                                                                 |
|--------------------|-----------------------------------------------------------------------------|
| **NixOS Server**   | Linux-based, reproducible, declaratively configured, and immutable server    |
| **Docker**         | Consistent deployment across environments with lightweight containers        |
| **ZooKeeper**      | Coordination and synchronization service for distributed systems             |

### **Frontend - Web Application**
The frontend is a user-friendly web application that interacts with the backend through RESTful API requests. It enables users to browse, query, and manage catalog data efficiently, providing an intuitive interface for data exploration and interaction with the system.

### **Programming Languages**

| **Language**  | **Purpose**                              |
|--------------|------------------------------------------|
| **Python**   | Backend development and data processing |
| **HTML**     | Structure of the web pages              |
| **CSS**      | Styling and layout of the web pages     |
| **JavaScript**| Interactive frontend functionality     |

### **Libraries & Frameworks**

| **Library/Framework** | **Purpose**                                         |
|----------------------|-----------------------------------------------------|
| **Flask**            | Routing and template rendering for the backend      |
| **Pyvis**            | Interactive network graph visualization             |
| **rdflib**           | RDF data handling and manipulation                  |
| **SPARQLWrapper**    | Execution of SPARQL queries                         |
| **json**             | Reading and writing JSON data for data sources      |
| **Bootstrap**        | Responsive and mobile-friendly web design           |

---

## Frontend Documentation
### **Overview**
The frontend of the CMS DCAT system is a user-friendly web interface designed to allow users to interact with RDF datasets. It enables users to navigate through data sources, submit SPARQL queries, and visualize data insights. The interface is built with HTML, CSS, JavaScript, and Flask, offering seamless communication with the backend services.

## **Key Features**

## **File Structure**

## 📂 Frontend File Structure

The frontend of this project is organized to separate the presentation layer (HTML templates) from static assets (CSS, JavaScript, and images) for better scalability and maintainability.

### **Templates Folder**
This folder contains all the HTML templates rendered by the Flask backend to serve dynamic web pages.
(((recheck this))))
``` 
📂 templates/                # HTML templates for web pages
├── index.html               # Homepage with project overview
├── query.html               # SPARQL query submission interface
├── ingest.html              # Data ingestion page
├── pyvis_graph.html         # Visualization of RDF data using Pyvis
├── Registered_Catalogue.html# List of registered datasets
├── explore.html             # Data exploration interface
├── file_system.html         # File system visualization
├── tabular_data.html        # Tabular data display
├── layout.html              # Common layout for consistent design
└── visualize_graph.html     # Graph-based data visualization
```

### **Static Folder**
This folder holds all the static files like custom styling, JavaScript for interactivity, and images used in the frontend.

```
📂 static/                   # Static assets (CSS, JS, images)
├── 📂 assets/               # General assets for the application
│   └── 📂 img/             # Images and icons
│       └── favicon.ico     # Website favicon
├── 📂 css/                 # CSS files for styling
│   └── styles.css          # General UI styling
└── 📂 js/                  # JavaScript files for interactivity
    └── scripts.js          # Interactive JS functionalities
```

### **Uploads Folder**
This folder stores files uploaded by users during the data ingestion process.

```
📂 uploads/                  # Stores user-uploaded files
```

### **Summary**
- **HTML templates** provide the structure and layout for different pages of the application.
- **Static files** manage the styling and interactivity of the frontend.
- **Uploads folder** securely stores files uploaded by users for further processing.

### **Installation and Configuration**

This section provides detailed instructions on how to set up and configure the project environment to run the CMS DCAT system.

---

## 📦 Prerequisites

Before running the project, ensure you have the following installed:

- **Python 3.8+**  
- **pip** (Python package installer)

Install Python from the [official website](https://www.python.org/downloads/) if it's not installed.

---

## 🔧 Project Setup

1. **Clone the Repository**

   ```bash
   git clone https://github.com/your-username/cms-dcat.git
   cd cms-dcat
   ```

2. **Create a Virtual Environment (Recommended)**

   ```bash
   python -m venv venv
   source venv/bin/activate   # For Linux/macOS
   venv\Scripts\activate      # For Windows
   ```

3. **Install Required Dependencies**

   Install all necessary Python libraries listed in the `requirements.txt` file:

   ```bash
   pip install -r requirements.txt
   ```

   **Or install manually if needed:**

   ```bash
   pip install Flask
   pip install rdflib
   pip install pyvis
   pip install SPARQLWrapper
   ```

--- ((recheck this))

## 📂 Project Configuration

1. **Uploads Folder Setup**

   Ensure the **uploads** folder exists in the project root to store user-uploaded files. If it doesn't exist, create it manually:

   ```bash
   mkdir uploads
   ```

   This folder is defined in the configuration:

   ```python
   UPLOAD_FOLDER = os.path.join(os.getcwd(), 'uploads')
   app.config['UPLOAD_FOLDER'] = UPLOAD_FOLDER
   ```

2. **Data Sources Configuration**

   Ensure that the file `data_sources.json` is present in the project root. This file contains the configuration for connected data sources.

3. **Logging Configuration**

   Debugging and logs are enabled for development purposes:

   ```python
   logging.basicConfig(level=logging.DEBUG)
   ```

---

## 🚀 Running the Project

Start the Flask application by running the main script:

```bash
python main.py
```

The server will start, and you can access the web application by navigating to:

```
http://localhost:5000
```

---

## ⚙️ Installed Dependencies Explained

| **Library**         | **Purpose**                                                                 |
|---------------------|-------------------------------------------------------------------------------|
| **Flask**           | Web framework for routing and rendering templates.                           |
| **rdflib**          | Handles RDF data parsing and manipulation.                                   |
| **pyvis**           | Used for interactive RDF graph visualization.                                |
| **SPARQLWrapper**   | Executes SPARQL queries against RDF datasets.                                 |
| **requests**        | Makes HTTP requests to external APIs.                                         |
| **json**            | Reads and writes JSON data for data sources and formatting.                   |
| **datetime**        | Handles date and time operations for data logging.                           |
| **re**              | Regular expressions for data validation and pattern matching.                 |
| **logging**         | Logs messages for debugging and monitoring.                                   |
| **time**            | Tracks execution time for performance monitoring.                            |
| **os**              | Handles file system paths and operations.                                     |

---

## ❗ Troubleshooting

- **ModuleNotFoundError:**  
  If you encounter this error, reinstall the missing dependency:

  ```bash
  pip install <missing-package>
  ```

- **Port Already in Use:**  
  If port 5000 is occupied, run the app on a different port:

  ```bash
  python main.py --port=5001
  ```

---
## **State Management**
backened and frontend connection
## **Styling

see chatgppt/
## 📞 Contact

For any questions or suggestions, feel free to contact:
- **Name:** [Your Name]
- **Email:** [your.email@example.com]
- **University:** [Your University]

---

## 📄 License
This project is for academic purposes only.

