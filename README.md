# Azure
# Azure Data Factory – Copy Activity Project

## 📌 Project Overview

This project demonstrates how to use **Azure Data Factory (ADF)** to copy files between containers in an **Azure Storage Account**.

The project starts with a basic file-copy pipeline and gradually implements different file selection techniques to control which files are transferred from the source container to the destination container.

The project demonstrates practical use of **Azure Data Factory, Azure Blob Storage, datasets, pipelines, and Copy Data activity**.

---

## 🎯 Objectives

* Create and configure an Azure Resource Group
* Create an Azure Storage Account
* Create source and destination containers
* Upload files to Azure Blob Storage
* Create an Azure Data Factory
* Build a Copy Data pipeline
* Copy files from source to destination
* Filter files using a **prefix**
* Filter files using a **wildcard pattern**
* Copy specific files using a **list of files**
* Validate pipeline execution and verify the copied files

---

## ☁️ Azure Services Used

* **Azure Data Factory**
* **Azure Storage Account**
* **Azure Blob Storage**
* **Azure Resource Group**

---

## 🔄 Project Workflow

```text
Azure Portal
     ↓
Resource Group
     ↓
Storage Account
     ↓
Source Container
     ↓
Upload Files
     ↓
Azure Data Factory
     ↓
Data Factory Studio
     ↓
Copy Data Activity
     ↓
File Selection / Filtering
     ↓
Destination Container
```

---

## 🗂️ Storage Structure

The Storage Account contains two containers:

```text
Storage Account
│
├── source
│   ├── ANNA_VINCENT_RESUME.pdf
│   ├── santo 1.txt
│   ├── santo 2.txt
│   ├── santo 3.txt
│   └── list.txt
│
└── destination
    └── Copied Files
```

The **source** container stores the input files, while the **destination** container stores the files selected and copied by the pipeline.

---

## 🚀 Implementation

### 1. Basic File Copy

The first pipeline copies a file directly from the **source** container to the **destination** container.

A **Copy Data activity** is configured with the source and destination datasets.

The pipeline execution completed successfully with the status:

```text
Succeeded
```

The copied file was then verified in the destination container.

---

### 2. Prefix-Based File Filtering

Additional text files were added to the source container:

```text
santo 1.txt
santo 2.txt
santo 3.txt
```

The Copy Data activity was configured with the prefix:

```text
sant
```

This allows only files whose names start with `sant` to be copied.

### Result

```text
Copied:
✓ santo 1.txt
✓ santo 2.txt
✓ santo 3.txt

Not copied:
✗ ANNA_VINCENT_RESUME.pdf
```

The pipeline completed successfully.

---

### 3. Wildcard File Filtering

The next scenario uses a wildcard file path to select files based on their extension.

The configured wildcard pattern was:

```text
*.pdf
```

This means that any file ending with `.pdf` can be selected.

### Result

```text
Copied:
✓ ANNA_VINCENT_RESUME.pdf

Not copied:
✗ santo 1.txt
✗ santo 2.txt
✗ santo 3.txt
```

This demonstrates how wildcard patterns can be used to filter files by extension.

---

### 4. List-of-Files Filtering

The final scenario uses a file called:

```text
list.txt
```

The file contains the names of the files that should be copied.

The Copy Data activity is configured using:

```text
List of files
```

with the path:

```text
source/list.txt
```

Only the files specified in `list.txt` are copied to the destination.

### Result

The destination contains exactly the files specified in the list file, demonstrating controlled file-level selection.

---

## 📊 File Selection Methods Demonstrated

| Method        | Configuration               | Purpose                                     |
| ------------- | --------------------------- | ------------------------------------------- |
| Basic Copy    | Direct source → destination | Copy a file without filtering               |
| Prefix        | `sant`                      | Copy files beginning with a specific prefix |
| Wildcard      | `*.pdf`                     | Copy files matching a file pattern          |
| List of Files | `source/list.txt`           | Copy only explicitly specified files        |

---

## 🛠️ Key Concepts Learned

* Azure Data Factory pipelines
* Copy Data activity
* Azure Blob Storage containers
* Source and sink datasets
* File path configuration
* Prefix-based filtering
* Wildcard file filtering
* List-of-files configuration
* Pipeline validation
* Pipeline execution monitoring
* Verifying output files in Azure Storage

---

## 📸 Project Evidence

The project documentation includes screenshots showing:

* Azure Portal and Resource Group
* Storage Account and containers
* Files uploaded to the source container
* Azure Data Factory Studio
* Copy Data activity configuration
* Pipeline execution status
* Prefix filtering
* Wildcard filtering
* List-of-files configuration
* Final files in the destination container

---

## ✅ Project Outcome

Successfully implemented and tested multiple **Azure Data Factory Copy Activity** scenarios for controlled file movement between Azure Blob Storage containers.

The project demonstrates how ADF can be used to build simple yet practical **cloud data ingestion and file-transfer workflows** with different file-selection strategies.

---

## 👩‍💻 Author

**Anna Vincent**

Data Engineering Student
Interested in **Data Engineering, Azure Cloud, SQL, Python, and Data Analytics**.
