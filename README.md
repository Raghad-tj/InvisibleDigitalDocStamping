# 🔒 Invisible Digital Document Stamping

## Final Project Submission: Secure File Sealing & Verification Tool (Python)

## I. Project Overview

### Objective

This project implements a secure digital sealing and verification system to ensure the integrity of digital files and detect unauthorized modifications. The seal is generated using the **HMAC-SHA256** cryptographic algorithm.

### Supported File Types

* **Images (PNG/JPG/JPEG):**

  * Generates a digital signature based on the image pixel data.
  * Stores the signature inside the PNG metadata.

* **PDF Documents:**

  * Generates a digital signature based on the extracted text content.
  * Stores the signature within the PDF metadata.

### Result

The tool allows users to verify whether a sealed file has remained unchanged since it was originally sealed.

---

## II. Prerequisites & Environment

### Development Environment

* Google Colab

The project uses the `google.colab.files` module for uploading and downloading files.

### Required Libraries

* Pillow (PIL)
* PyPDF2
* hmac (built into Python)
* hashlib (built into Python)

---

## III. Setup Instructions

### 1. Install Required Libraries

```python
!pip install pillow PyPDF2 -q
```

### 2. Define the Secret Key

```python
SECRET_KEY = "my_super_secret_key_123"
```

---

## IV. Running the Project

The notebook consists of two main operations:

### 1. Sealing Process

**Description:**
Upload a file, generate its digital seal, then save and download the sealed version.

| Input        | Process                                          | Output                             |
| ------------ | ------------------------------------------------ | ---------------------------------- |
| Image or PDF | Generate HMAC signature and store it in metadata | A new file prefixed with `sealed_` |

---

### 2. Verification Process

**Description:**
Upload a previously sealed file, extract the stored signature, recompute the signature, and compare the results.

| Result                   | Meaning                                                        |
| ------------------------ | -------------------------------------------------------------- |
| ✅ File Verified          | The file has not been modified since it was sealed.            |
| ❌ No Valid Security Seal | The file has been modified or no valid digital seal was found. |

---

## V. Project Structure

```text
Project.ipynb

│── Cell 1: Environment Setup
│   └── Install required libraries

│── Cell 2: Helper Functions & Signature Generation
│   ├── SECRET_KEY
│   ├── normalize_text()
│   ├── generate_image_signature()
│   └── generate_pdf_signature()

│── Cell 3: Sealing Functions
│   ├── seal_image_bytes()
│   └── seal_pdf_bytes()

│── Cell 4: Verification Functions
│   ├── verify_image_bytes()
│   └── verify_pdf_bytes()

│── Cell 5: File Sealing
│   └── files.upload()

│── Cell 6: File Verification
│   └── files.upload()
```

---

## Technologies Used

* Python
* HMAC-SHA256
* Pillow (PIL)
* PyPDF2
* Google Colab

---

## Project Goal

To provide a lightweight and secure solution for digitally sealing and verifying image and PDF files, ensuring data integrity and protecting documents against unauthorized modifications.
