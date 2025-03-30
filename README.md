Web Scraping for Palestine-related News Articles
This Python script scrapes news articles related to Palestine war from various Arabic news websites and saves the extracted paragraphs to a CSV file.
Features
- Fetches HTML content from news websites
- Extracts all paragraphs using BeautifulSoup
- Stores the extracted data in a pandas DataFrame
- Exports the data to a CSV file
- Designed to work in Google Colab environment
Supported Websites
Currently configured to scrape from:
- Al Jazeera Arabic and CNN Arabic
- Al-Hudood 
Requirements
- Python 
- requests
- beautifulsoup4
- pandas
# Web Scraping System Architecture

```mermaid
flowchart TB
    subgraph InputLayer[Input Layer]
        A1[Al Jazeera Arabic]:::newsSource
        A2[Al-Hudood]:::newsSource
        A3[CNN Arabic]:::newsSource
    end

    subgraph ProcessingLayer[Processing Layer]
        B1[HTTP Request\nrequests.get()]:::processing
        B2[HTML Parsing\nBeautifulSoup]:::processing
        B3[Data Structuring\npandas DataFrame]:::processing
    end

    subgraph OutputLayer[Output Layer]
        C1[CSV File\nset_data.csv]:::output
        C2[Google Colab Download]:::output
    end

    subgraph Environment[Execution Environment]
        D1[Google Colab]:::env
    end

    InputLayer -->|URLs| ProcessingLayer
    ProcessingLayer -->|Structured Data| OutputLayer
    Environment -->|Runs Script| ProcessingLayer

    classDef newsSource fill:#ffdddd,stroke:#ff9999,stroke-width:2px,stroke-dasharray: 5 5
    classDef processing fill:#ddffdd,stroke:#99cc99,stroke-width:2px
    classDef output fill:#ddddff,stroke:#9999ff,stroke-width:2px
    classDef env fill:#ffffdd,stroke:#ffcc66,stroke-width:2px
