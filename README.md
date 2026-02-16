# Legal Document Clustering & Extraction Engine ⚖️

![Python](https://img.shields.io/badge/Python-3.11+-blue.svg)
![NLP](https://img.shields.io/badge/Tech-NLP%20%7C%20OCR-green)
![Model](https://img.shields.io/badge/Model-DistilBERT-orange)

## 📋 Project Overview

This project focuses on enhancing legal research efficiency by applying Natural Language Processing (NLP) techniques to Indian legal judgments. The system automatically extracts legal statutes (IPC, CrPC, etc.), analyzes their co-occurrence patterns using a hybrid approach, and clusters documents based on their legal nature.

By leveraging **DistilBERT** for semantic understanding and **Google Gemini** for high-level classification, this tool transforms unstructured legal texts into organized, actionable data.

## 🚀 Key Features

* **Automated IPC Extraction:** Uses Regex and OCR (Tesseract) to identify and extract citations of the Indian Penal Code (IPC), CrPC, and Evidence Act from raw PDF/Image documents.
* **Hybrid Analysis Engine:**
    * **Co-occurrence Analysis:** Identifies which legal sections frequently appear together (Explicit matching).
    * **Semantic Clustering:** Uses **DistilBERT** embeddings to find sections that are contextually related even if not explicitly linked.
* **Intelligent Document Clustering:** Automates the categorization of case files (e.g., separating "Criminal" vs. "Civil" cases) using Large Language Models (LLM), organizing them into a structured directory system.
* **Missing Statute Recommendation:** Analyzes the context of a judgment and suggests relevant legal sections that may have been missed or are pertinent to the cluster.

## 🛠️ Tech Stack

* **Language:** Python
* **Core NLP:** Transformers (DistilBERT), Scikit-learn
* **OCR & Processing:** Pytesseract, PDF2Image, PyPDF2
* **LLM Integration:** Google Gemini API (for advanced classification)
* **Data Structure:** JSON-based Hybrid Co-occurrence Matrix

## 📂 Architecture

1.  **Training Module:** Ingests legal documents, builds semantic embeddings, and constructs the co-occurrence knowledge base.
2.  **Analysis Module:** Scans new input files, extracts sections, and runs the recommendation algorithm.
3.  **Clustering Module:** Classifies the document nature and physically organizes files into a clustered folder structure.

## 📦 Installation

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/yourusername/legal-document-clustering-nlp.git](https://github.com/yourusername/legal-document-clustering-nlp.git)
    cd legal-document-clustering-nlp
    ```

2.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Setup Tesseract OCR:**
    * Ensure Tesseract-OCR is installed on your system and added to your PATH.

4.  **Configuration:**
    * Add your Google Gemini API key in `3_storage.ipynb` to enable the automated clustering features.

## 📊 Usage

**Step 1: Train the Knowledge Base**
Run `1_training.ipynb` to process your document corpus and generate the hybrid analysis matrix.

**Step 2: Analyze & Recommend**
Run `2_input.ipynb` to feed a specific case file and receive IPC extraction analysis and recommendations.

**Step 3: Cluster & Organize**
Run `3_storage.ipynb` to classify the documents and move them into their respective clusters (folders).

## 📄 License

[MIT License](LICENSE)
