
**Introduction**
This project focuses on building an AI model for generating Vietnamese poems using text generation techniques, a subset of natural language processing (NLP). Text generation models create new sentences based on input data, offering creative outputs applicable in various contexts. The project aims to generate complete Vietnamese poems from an initial user-provided phrase.


**Project Phases**

**1. Data Collection**

Source: Poems are collected from thivien.net, a comprehensive website featuring various Vietnamese literary works.

Tools and Methods:

  -Selenium: Used for web scraping and data extraction.
  
  -Google Colab: Execution environment for running Selenium with specific installation steps for compatibility.
  
**Steps for Data Collection:**

  -Library Installation: Installation of Selenium and its dependencies.
  
  -Selenium Setup: Initialization of Selenium WebDriver for navigating and extracting    data from web pages.
  
  -Data Extraction:
  
    +Navigate to search pages on thivien.net.
    
    +Extract poem content, title, and source using HTML tags and XPath.
    
    +Store the extracted data into a list of dictionaries.
    
  -Data Storage: The collected data is saved into a .csv file for further processing.
  
**2. Model Building**

  -Model: GPT-2 (Generative Pre-trained Transformer 2), a large language model developed by OpenAI, based on the Transformer architecture.
  
  -Process:
  
    +Library Installation: Necessary libraries such as datasets, evaluate, transformers, and accelerate are installed.
    
    +Data Preparation:
    
      Load the collected poem data from the .csv file.
      
      Process the poems by splitting them into suitable samples for model training.
      
    +Model Fine-Tuning:
    
      Use the pre-trained GPT-2 model.
      
      Fine-tune the model specifically for Vietnamese poem generation using the prepared dataset.
      
**Implementation Details**

Data Processing

    -CSV Handling: The poems are read from the .csv file into a DataFrame.
    
    -Sample Creation: Each poem is divided into smaller parts (stanzas) to create manageable training samples.
    
Model Training

    -Tokenizer and Model Initialization: GPT2Tokenizer and GPT2LMHeadModel from the HuggingFace library are utilized.
    
    -Training Setup: Define training arguments and initiate the training process using the HuggingFace Trainer class.





