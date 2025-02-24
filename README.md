# 📌 API Testing for RAG Backend

## 🔬 Overview
This section provides detailed steps to test the API endpoints for both **text** and **JSON data** using Python scripts. The scripts automate bulk uploads and queries, ensuring the backend functions correctly.

---

## 📂 API Testing Directory Structure
```
APItesting/
│── Text/
│   ├── textFilesUpload.py  # Uploads multiple text files
│   ├── textQueries.py      # Runs queries on uploaded text files
│
│── Json/
│   ├── JsonUpload.py       # Uploads multiple JSON files
│   ├── JsonGetStats.py     # Runs computations on stored JSON data
```

---

## 📝 **1. Bulk Upload & Query (Text Data)**

### 📤 **Uploading Multiple Text Files**
#### **Script:** `APItesting/Text/textFilesUpload.py`

**Functionality:**
- Iterates through all text files (`PDF`, `DOCX`, `TXT`) in a folder.
- Extracts text and uploads it via `/api/files/upload`.
- Stores `document_id` for each file in `queries.json`.

### 📌 **Steps to Upload Text Data**
```sh
python Text/textFilesUpload.py
```
✅ A `queries.json` file is created with document IDs.

### 🔍 **Running Queries on Uploaded Text Data**
#### **Script:** `APItesting/Text/textQueries.py`

**Functionality:**
- Reads `queries.json` to fetch document IDs.
- Sends queries to `/api/search/search`.
- Saves results in `queries_results.txt`.

### 📌 **Steps to Run Queries**
```sh
python Text/textQueries.py
```
✅ Results are stored in `queries_results.txt`.

---

## 📊 **2. Bulk Upload & Query (JSON Data)**

### 📤 **Uploading Multiple JSON Files**
#### **Script:** `APItesting/Json/JsonUpload.py`

**Functionality:**
- Iterates through all JSON files in a folder.
- Uploads them via `/api/json/json_upload`.
- Stores `document_id` and fields for computations.

### 📌 **Steps to Upload JSON Data**
```sh
python Json/JsonUpload.py
```
✅ A `json_uploaded_files.json` file is created with document IDs.

### 🔢 **Running Computations on Stored JSON Data**
#### **Script:** `APItesting/Json/JsonGetStats.py`

**Functionality:**
- Reads `json_uploaded_files.json` to fetch document IDs.
- Sends computation requests to `/api/json/json_stats`.
- Saves results in `json_query_results.txt`.

### 📌 **Steps to Run JSON Computations**
```sh
python Json/JsonGetStats.py
```
✅ Results are stored in `json_query_results.txt`.

---

## 🛠 **Setup & Dependencies**
Ensure you have **Python 3+** installed.
Run - pip install requests

---

## 🚀 **Conclusion**
The provided Python scripts efficiently test text and JSON data endpoints, ensuring the RAG backend performs as expected. Modify the scripts as needed for additional test cases.

---

📩 **For any issues, feel free to reach out!**

