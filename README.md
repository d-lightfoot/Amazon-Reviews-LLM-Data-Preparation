# Amazon Reviews LLM Data Preparation
A data preparation project that uses Claude API to automatically clean messy Amazon product reviews for downstream machine learning tasks.

## Overview
This project demonstrates how large language models can clean user-generated text data by fixing spelling errors, standardizing grammar, and improving formatting while preserving the original sentiment/meaning. The solution processes Amazon product reviews using Claude to prepare higher-quality training data for ML applications.

## Dataset
The dataset is from Kaggle: https://www.kaggle.com/datasets/yasserh/amazon-product-reviews-dataset
- **amazon_product_reviews.csv**: Raw Amazon product reviews with ratings and metadata

To run this notebook:
1. Download the dataset from Kaggle (or from this repository)
2. Upload `amazon_product_reviews.csv` when prompted in Google Colab
3. Enter Anthropic API key (https://console.anthropic.com/settings/keys)
4. Download output file `amazon_reviews_cleaned.csv` with results

## Key Features
### LLM-Powered Data Cleaning
- **Spelling Correction**: Fixes common typos and misspellings in user reviews
- **Grammar Standardization**: Improves sentence structure and verb tenses
- **Capitalization Normalization**: Standardizes proper nouns and sentence capitalization
- **Punctuation Cleanup**: Removes excessive punctuation while maintaining meaning
- **Abbreviation Expansion**: Converts text speak and abbreviations to full words

### Processing Pipeline
- **Data Filtering**: Removes reviews shorter than 20 or longer than 1,000 characters
- **Claude API Integration**: Uses Sonnet 4 model for context-aware text cleaning
- **Batch Processing**: Processes 100 reviews with rate limiting (0.5s per review)
- **Error Handling**: Fallback to original text if the API call happens to fail

## Technical Stack
- **Python 3.11**
- **Core Libraries**:
  - `anthropic` - Claude API client
  - `pandas` - Data manipulation
  - `google.colab` - File upload/download

## Cleaning Pipeline
1. **Data Loading**: Upload and filter Amazon review dataset
2. **Sample Selection**: Randomly sample 100 reviews for processing
3. **API Configuration**: Initialize Claude client with API key
4. **Text Cleaning**: Send each review to Claude with cleaning instructions
5. **Results Compilation**: Collect cleaned reviews with metadata
6. **Output Generation**: Export the "before and after" comparison CSV file

## Project Context
This notebook was developed to demonstrate LLM-powered data preparation techniques for machine learning pipelines. The challenge involves working with real-world user-generated text that contains common quality issues like typos, inconsistent formatting, and poor grammar.

## Author
David Lightfoot
