# named-entity-recognition-LLM-

## Overview
* This project is about implementing a real-time data ingestion system for EthioMart to consolidate e-commerce activities from various Telegram channels into a centralized platform. The focus is on developing an Amharic NER system capable of extracting key business entities such as product names, prices, and locations.
* With the rise of Telegram as a platform for e-commerce transactions in Ethiopia, multiple independent channels have emerged, creating a fragmented experience for vendors and customers. EthioMart's vision is to unify these channels into a single platform that facilitates easier product discovery, order placement, and communication.

## Key Objectives
* Real-time Data Extraction: Develop a system to fetch messages, images, and documents from Ethiopian-based Telegram e-commerce channels.
* Fine-tune LLM for Amharic NER: Train models to extract entities like product names, prices, and locations.

## Major Tasks
* Data Ingestion: Telethon library used to develop script for scrapping data from Telegram.
* Preprocess Text Data:
- Handling missing message data
- Emoji Removal
- Tokenization: A rule-based approach was implemented to tokenize using regular expressions, capturing all non-whitespace characters
* Label a Subset of Dataset in CoNLL Format
* Entity Detection: a rule-based approach was implemented to tokenize and label the relevant entities in the dataset. This involved defining specific rules for identifying various entities such as products, prices, locations, and phone numbers.
- Phone Numbers: Tokens matching a pattern of 10 consecutive digits are labeled as I-PHONE.
- Prices: Tokens that represent prices (e.g., numbers followed by currency indicators like "ETB", "ብር", “birr” or "$") are labeled as I-PRICE.
- Locations: Tokens that match known locations like ('Addis Ababa', 'ለቡ', 'ለቡ መዳህኒዓለም', 'መገናኛ', 'ቦሌ', 'ሜክሲኮ', 'ብስራተ', 'ገብርኤል', 'ገርጂ', 'ኢምፔሪያል', 'ህንፃ', 'ፕላዛ', '4ኪሎ', 'ፎቅ', 'ላፍቶ', 'ሞል', 'ስላሴ')  names are labeled as I-LOC.
- General Tokens: All other tokens are labeled as O (outside any entities).

* Fine Tune NER Model: fine-tune a Named Entity Recognition (NER) model to extract key entities, such as products, prices,phone numbers and locations, from Amharic Telegram messages. 
- The model was fine-tuned using pre-labeled data in CoNLL format 
- a pre-trained model i.e.  bert-base-multilingual-cased, distilbert-base-uncased and xlm-roberta-base.

## Prerequisites
* Python 3.x: Ensure Python is installed on your system.
* Virtual Environment: Recommended for managing project dependencies.

**Installation**

1. Create a virtual environment:
On macOS/Linux:

```python -m venv venv```
```source venv/bin/activate```

on windows:
```python -m venv venv ```
```venv\Scripts\activate ```

2. Install dependencies:
``` pip install -r requirements.txt```


**Contributing**

Contributions are welcome!

**License**

This project is licensed under the MIT License. See the LICENSE file for more details.
