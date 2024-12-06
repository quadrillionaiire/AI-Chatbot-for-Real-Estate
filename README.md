# Washington D.C. Housing Market Analysis

## Overview
This project explores the real estate market in Washington, D.C., utilizing a dataset containing over 5,000 current listings from Zillow, as of June 5, 2024. The dataset provides comprehensive details on properties for sale in the area, such as property types, listing prices, square footage, amenities, and more. The goal of this analysis is to uncover insights related to pricing trends, neighborhood comparisons, property characteristics, and market dynamics within Washington, D.C.

## Business Problem
The Washington, D.C. housing market is highly competitive, with various factors influencing listing prices and property demand. This project aims to address key business problems such as:

- Identifying pricing trends and price per square foot across neighborhoods and property types.
- Understanding factors that drive property pricing, such as square footage, age of construction, and amenities.
- Evaluating the role of school quality and neighborhood characteristics in influencing property prices.

By solving these problems, real estate professionals and prospective buyers can make data-driven decisions, enhancing their understanding of the market and improving investment strategies.

## Data Understanding
The dataset includes comprehensive details on 5,000+ real estate listings sourced from Zillow, with the following key attributes:

- **Location Details**: Address, city, state, zip code, latitude/longitude coordinates.
- **Property Details**: Property type (single-family, condo, apartment, etc.), number of bedrooms and bathrooms, square footage, lot size, year of construction.
- **Financial Information**: Listing price, HOA fees (if applicable), property tax history.
- **Amenities**: Features such as rooftop terraces, concierge services, etc.
- **Nearby Schools**: GreatSchools ratings for nearby schools.
- **Agent Information**: Property and listing agents, brokers, and their contact information.

The data is available in both light and heavy JSON versions, allowing for flexibility in analysis.

## Data Preparation
The raw data required significant preprocessing to ensure that it was clean and ready for analysis. This included:

- Parsing and transforming JSON data into a structured format for easier analysis.
- Handling missing or incomplete values, particularly in fields like HOA fees and property tax history.
- Standardizing location data to ensure consistency in the analysis of neighborhood trends.
- Extracting and categorizing the property types for more meaningful comparisons.

## Analysis and Results

In this analysis, we performed a parallel analysis using two real estate datasets: a lighter dataset (5181 rows, 57 columns) and a heavier dataset (5181 rows, 207 columns). Both datasets were examined using a variety of machine learning and deep learning models, with a focus on predicting property prices based on various features.

### Key Analyses Conducted:
- **Price Trends**: Analyzed price per square foot across different neighborhoods and property types to identify the most expensive and affordable areas in Washington, D.C.
- **Property Characteristics**: Studied how factors like square footage, year of construction, and amenities affect listing prices.
- **Neighborhood Comparisons**: Mapped listings to visualize the spatial distribution of available inventory and identify hotspots for property investments.

### Machine Learning Models:

#### Light Dataset (57 Columns):
- **Linear Regression**: Achieved perfect predictions with MAE = 0.00, MSE = 0.00, R² = 1.00.
- **Decision Tree**: Also performed perfectly with MAE = 0.00, MSE = 0.00, R² = 1.00.
- **Random Forest**: Matched the performance of Linear Regression and Decision Tree, achieving MAE = 0.00, MSE = 0.00, R² = 1.00.

The light dataset demonstrated that classical machine learning models like Linear Regression, Decision Trees, and Random Forest can be highly effective for property price prediction, achieving flawless results.

#### Heavy Dataset (207 Columns):
- **Random Forest**: This model performed the best with an R² of 0.7918, indicating strong predictive power despite the dataset's complexity. It achieved MAE = 250,602 and MSE = 747.66 billion.
- **Linear Regression**: Showed lower accuracy with R² = 0.5586 and higher error rates (MAE = 566,707).
- **Decision Tree**: Had a lower error rate (MAE = 340,444) but showed signs of overfitting, with R² = 0.4935.
- **Support Vector Machine (SVM)**: Performed poorly across all metrics, suggesting it was not suited for this dataset.

#### Deep Learning:
- We tested a sequential neural network model for deep learning, but it underperformed compared to Random Forest, with an R² of 0.39 and high error values (MAE = 595,520.27; MSE = 1.03 trillion). This suggests that deep learning requires more data preprocessing and larger datasets to perform effectively.

#### Chatbot Development:
- **Pretrained Chatbot Model**: Encountered issues with attention mask and padding configurations, preventing the use of a pretrained model. A fallback system was implemented with a lighter dataset, which successfully extracted the number of bedrooms but struggled to accurately capture city names.

### Final Analysis:

- **Light Dataset**: Classical ML models (Random Forest, Decision Tree, and Linear Regression) performed exceptionally well, delivering perfect predictions (MAE = 0.00, MSE = 0.00, R² = 1.00). These models are highly suitable for price prediction tasks in real estate.
  
- **Heavy Dataset**: Random Forest outperformed all other models with an R² of 0.7918, offering strong predictive capabilities for real estate data. While Linear Regression and Decision Tree models had lower performance, Random Forest's ability to capture non-linear relationships made it the best choice for predicting property prices in complex datasets.

- **Deep Learning**: The sequential neural network model failed to provide competitive performance, indicating that more advanced tuning and data preprocessing are required for deep learning to be effective in this context.

- **Chatbot Challenges**: The chatbot integration encountered significant hurdles, particularly related to dataset alignment and configuration of pretrained models. However, the fallback system showed some progress, extracting basic property details.

### Non-Technical Summary:

Machine learning models, particularly Random Forest, performed exceptionally well in predicting property prices, demonstrating their ability to manage complex real estate data with high accuracy. Although deep learning models show potential, they underperformed in comparison to Random Forest, highlighting the need for better data preprocessing and larger datasets. The chatbot, while in early stages, successfully extracted basic details from user inputs, laying the foundation for future development.

### Next Steps for Chatbot Development:
1. **Improve Dataset Quality**: Add more representative data, especially for cities and nuanced property features.
2. **Address Pretrained Model Issues**: Resolve attention mask and padding configuration problems for pretrained models.
3. **Optimize Deep Learning Models**: Refine model architecture with hyperparameter tuning and regularization.
4. **Enhance NLP Capabilities**: Expand the chatbot's ability to handle more complex queries and provide comprehensive responses.

### Business Recommendations for Stakeholders:
1. **Leverage Random Forest**: Prioritize Random Forest integration into the chatbot backend to ensure accurate predictions for property pricing.
2. **Expand and Refine Data**: Enrich the dataset with more detailed property attributes to improve model predictions.
3. **Focus on User Experience**: Ensure the chatbot is user-friendly and capable of handling a variety of input types for a seamless user experience.
4. **Implement Phased Rollouts**: Gradually deploy enhanced chatbot features, starting with basic functionality and iterating based on user feedback.
5. **Monitor and Iterate**: Continuously evaluate the performance of the chatbot and models with real-world data to improve their functionality over time.

By following these steps, we can build an advanced AI-powered tool that transforms the real estate industry by making price estimation and client interaction more efficient and reliable.

### Example Future Test Cases:
- **Case 1: NLP-Based Input**
  - **You**: Tell me about 3-bedroom properties in DC.
  - **Chatbot**: Based on the data, we found properties in the following price ranges: {'Low', 'Medium'}

- **Case 2: Feature-Based Input**
  - **You**: beds=3, baths=2, area=0.2
  - **Chatbot**: The predicted price for the given features is approximately $450,000.00.

- **Case 3: Unsupported Input**
  - **You**: Show me houses.
  - **Chatbot**: Sorry, I couldn't understand your request. Please provide more details.

### Descriptive Analysis Questions:
- What is the distribution of property prices?
- How do the number of bedrooms and bathrooms influence property prices?
- What is the distribution of property sizes (area)?
- How does the property status type (e.g., for sale, sold) vary across price ranges?
- Are properties built by specific builders more expensive on average?
- Are there properties with undisclosed addresses, and how do they differ in price or size?

### Inferential Analysis Questions:
- Is there a significant difference in prices based on the number of bedrooms?
- Is there a correlation between property size and price?

### Conclusion:
The analysis and machine learning results demonstrate that AI can significantly enhance real estate pricing models, improving predictions and providing valuable insights for stakeholders. Despite some challenges with the chatbot integration, the project shows promising potential for further development and refinement in the real estate market.

## For More Information
- See the full analysis in the Jupyter Notebook or review this presentation.
- The original data was sourced from Kaggle: [Washington D.C. Housing Market 2024 Dataset](https://www.kaggle.com/datasets](https://www.kaggle.com/datasets/datadetective08/washington-d-c-housing-market-2024?select=washington+dc_real+estate+market_houses+for+sale_2024.json)).

---

## Repository Structure
```
├── data               # Raw and processed data files
├── images             # Visualizations and charts
├── notebooks          # Jupyter notebooks for analysis
├── presentations      # Presentation slides and reports
├── src                # Scripts and utility functions
├── .gitignore         # Git ignore file
```

---

