# ai-document-processing-and-matching
End-to-end intelligent document processing and matching pipeline.

## Overview

An end-to-end data and AI solution developed in Databricks to automate the processing, extraction, transformation, and comparison of information from PDF documents and SAP Datasphere views.

The solution combines AI-powered document parsing and information extraction with data processing, fuzzy matching, and historical tracking to generate structured and validated results.

## Objective

The main objective of this project is to automate the extraction of relevant information from PDF documents that contain the worked hours of the employees and compare it against existing workforce data, reducing manual processing and improving consistency and efficiency.

## Architecture

![Project Architecture](images/Diagram_architecture.png)

The solution consists of two main workflows:

### 1. PDF Processing & Comparison

The user uploads PDF documents through a Databricks App. The application triggers a processing job that:

1. Loads the PDF files into a staging volume.
2. Parses the documents using AI.
3. Extracts structured information from the parsed content.
4. Generates summarized data.
5. Performs fuzzy matching to identify corresponding extracted records with existing workforce data.
6. Compares the extracted information with existing workforce data.
7. Performs fuzzy matching to identify corresponding records.
8. Stores the comparison results and historical data.

### 2. Workforce Data Loading

A scheduled workflow retrieves workforce data from SAP Datasphere and processes it into structured tables.

The workflow includes:

- Data ingestion
- Transformation
- Data summarization
- Scheduled execution

The resulting dataset is then used in the PDF comparison workflow.

## Workflow

```text
PDF Documents
      ↓
Databricks App
      ↓
Staging Volume
      ↓
AI Parsing
      ↓
AI Extraction
      ↓
Data Transformation & Summary
      ↓
Fuzzy Matching
      ↓
Comparison Results
      ↓
Historical Tracking
