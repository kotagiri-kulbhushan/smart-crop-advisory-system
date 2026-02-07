# Smart Crop Advisory System

This project is a location-based agricultural advisory system that provides daily farming recommendations using real-time weather data and official IMD Agromet bulletins.

The system combines weather conditions with government-issued agricultural guidance using a Retrieval-Augmented Generation (RAG) pipeline. The goal is to deliver reliable, evidence-based suggestions that farmers or agricultural planners can use for better decision-making.

---

## Overview

The system performs the following steps:

1. Fetches real-time weather data for a given city using OpenWeatherMap
2. Identifies the corresponding state and district
3. Downloads the latest IMD Agromet bulletin (state or district level)
4. Extracts text from the bulletin PDF
5. Converts the text into embeddings using HuggingFace models
6. Stores and searches the data using FAISS
7. Retrieves the most relevant advisory points based on current weather conditions
8. Generates:

   * Top priority advisories
   * Category-wise farming recommendations

---

## Advisory Categories

* Weather warnings
* Crop pest and disease alerts
* Irrigation guidance
* Spraying and fertilizer recommendations
* Harvesting and field operation guidance

All recommendations are grounded in official IMD bulletin content to ensure reliability.

---

## Tech Stack

* Python
* LangChain
* FAISS
* HuggingFace Embeddings (all-MiniLM-L6-v2)
* OpenWeatherMap API
* PyPDF2
* Retrieval-Augmented Generation (RAG)

---

## Installation

Clone the repository:

```bash
git clone https://github.com/kotagiri-kulbhushan/smart-crop-advisory-system.git
cd smart-crop-advisory-system
```

Install the required libraries:

```bash
pip install -r requirements.txt
```

---

## Getting the OpenWeather API Key

1. Create a free account at:
   [https://openweathermap.org/api](https://openweathermap.org/api)

2. After signing in, generate an API key from your dashboard.

3. Before running the notebook, set the API key:

```python
import os
os.environ["OPENWEATHER_API_KEY"] = "your_api_key_here"
```

Then run the notebook:

```
notebooks/crop_advisory.ipynb
```

---

## Example Output

The system provides:

* Current weather summary
* 24-hour forecast analysis
* State and district mapping
* Official IMD bulletin source (URL and file)
* Top important advisories
* Category-wise farming recommendations

---

## Project Highlights

* End-to-end implementation of a RAG pipeline
* Integration of real-time external weather data
* Use of government agricultural bulletins to reduce hallucinations
* Practical AI application for agriculture and decision support

---

## Disclaimer

Advisory content, including chemical usage and dosages, is extracted from official IMD bulletins. Users should verify recommendations with local agricultural officers or extension services before applying them in the field.

---

## Author

Kul Bhushan
