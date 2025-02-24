# 📌 API Testing for RAG Backend

## 🔬 Overview
This section provides detailed steps to test the API endpoints for both **text** and **JSON data** using Python scripts. The scripts automate bulk uploads and queries, ensuring the backend functions correctly.

---

## 📂 API Testing Directory Structure
```

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
#### **Script:** `Text/textFilesUpload.py`

**Functionality:**
- Iterates through all text files (`PDF`, `DOCX`, `TXT`) in a folder.
- Extracts text and uploads it via `/api/files/upload`.
- Stores `document_id` for each file in `queries.json`.

### 📌 **Steps to Upload Text Data**
```sh
python Text/textFilesUpload.py
Fill in the queries in the queries empty array under " " and use comma for seperating multiple queries.
```
✅ A `queries.json` file is created with document IDs and space for entering multiple queries individually for each uploaded file.

### 🔍 **Running Queries on Uploaded Text Data**
#### **Script:** `Text/textQueries.py`

**Functionality:**
- Reads `queries.json` to fetch document IDs.
- Sends queries to `/api/search/search`.
- Saves results in `queries_results.txt`.

### 📌 **Steps to Run Queries**
```sh
python Text/textQueries.py
```
✅ Results are stored in `Text/queries_results.txt`.

---

## 📊 **2. Bulk Upload & Query (JSON Data)**

### 📤 **Uploading Multiple JSON Files**
#### **Script:** `Json/JsonUpload.py`

**Functionality:**
- Iterates through all JSON files in a folder.
- Uploads them via `/api/json/json_upload`.
- Stores `document_id` and fields for computations.

### 📌 **Steps to Upload JSON Data**
```sh
python Json/JsonUpload.py
```
✅ A `json_uploaded_files.json` file is created with document IDs.
Fill the relevant (single)field from one of the relevant properties of the json objects uploaded and add more operations in the below operations array as per need.
Supported operations are :
1. max – Maximum value of the field <br>
• # 2. min – Minimum value of the field <br>
• # 3. sum – Sum of all values in the field<br>
• # 4. average – Average (mean) of the field values<br>
• # 5. median – Median of the field values<br>
• # 6. mode – Most frequently occurring value<br>
• # 7. variance – Variance of the field values<br>
• # 8. std_dev – Standard deviation of the field values<br>
• # 9. count_above – Count of values greater than a given number<br>
• # 10. count_below – Count of values less than a given number<br>
• # 11. count_equal – Count of values equal to a given number<br>
• # 12. group_by – Groups values by another field<br>
• # 13. bucket – Buckets values into defined ranges<br>
• # 14. most_common – Most frequently occurring string value in a field<br>
• # 15. unique_count – Count of unique values in a field<br>
<br>

Simply add more operations as strings seperated by comma.
### 🔢 **Running Computations on Stored JSON Data**
#### **Script:** `Json/JsonGetStats.py`

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
Shubham Sharma <br>
shubham.sharma200121@gmail.com<br>

