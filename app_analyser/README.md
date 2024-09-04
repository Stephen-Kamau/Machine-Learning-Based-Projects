# App Analyser

### Building a No-Code Machine Learning App with Streamlit

**App Analyser** is a no-code data analytics and machine learning application designed to empower users to perform complex data analysis and build predictive models without writing a single line of code. With the rise in data-driven decision-making, this application bridges the gap for users who may not have the technical expertise to code but still require advanced analytical tools.

## 🌟 Features

### 1. Data Upload and Exploration
- Users can easily upload datasets in Excel or CSV formats.
- The app provides a preview of the uploaded dataset, including summary statistics, data types, and any missing values, helping users understand their data at a glance.

### 2. Data Visualization
- The app supports a range of data visualizations to explore the relationships between variables.
- Currently, it includes a correlation plot to examine the relationships between numerical columns.
- Univariate and multivariate analysis features allow users to create various plots such as count plots and histograms, making it easy to visualize data distributions and relationships.

### 3. Machine Learning Setup
- The app simplifies machine learning preparation by allowing users to:
  - Select a target variable.
  - Specify the train-test split ratio.
  - Choose encoding methods for categorical variables.
  - Apply text data preprocessing techniques like CountVectorizer or TF-IDF Vectorizer.

### 4. Model Training
- Users can choose from a variety of machine learning models tailored to their specific tasks, such as:
  - **Classification Models**: Decision Trees, Random Forests, Support Vector Machines, Boosting Models.
  - **Regression Models**: Linear Regression, Ridge, Lasso, and more.
- The app automatically handles the training process, making it accessible even to those without prior machine learning experience.

### 5. Model Evaluation
- After training, the app provides comprehensive evaluation metrics:
  - **Classification Tasks**: Confusion matrices, ROC curves, and precision-recall curves.
  - **Regression Tasks**: Predicted versus actual values plots, Mean Squared Error (MSE), and R-squared metrics.

### 6. Model Selection and Deployment
- The app suggests the best-performing model based on evaluation metrics.
- Users can save the model directly from the application and receive code to create an endpoint for real-world predictions.

## 🛠 How to Run the App

Follow these steps to get the app running on your local machine:

1. **Clone the Repository**
   ```bash
   git clone git@github.com:Stephen-Kamau/App-Analyser-A-No-Code-Machine-Learning-App-with-Streamlit.git
   cd App-Analyser-A-No-Code-Machine-Learning-App-with-Streamlit
    ```
2. **Install the Required Dependencies Make sure you have Python installed. Then, install the necessary packages using `pip`**:
    ```
    pip install -r requirements.txt
    
    ```

3. **Run the Application Launch the Streamlit app by running the following command:**
    ```
    streamlit run app.py 
    ```

4. **Use the App Once the app is running, it will open in your default web browser. You can now upload your dataset, perform exploratory data analysis (EDA), train models, compare their performance, and retrain model—all from within the app.**


## ACCESS REPOSITORY
---
[App Analyser:No-Code Machine Learning App with Streamlit](https://github.com/Stephen-Kamau/App-Analyser-A-No-Code-Machine-Learning-App-with-Streamlit)

---


---

## 🚀 Summary
App Analyser democratizes data science by making advanced analytical tools accessible to everyone. Whether you are a business analyst, a domain expert, or a starter data enthusiast, this platform enables you to derive actionable insights and build powerful predictive models with ease. With the app now fully completed, you can run the entire machine learning process, from data upload to model comparison, training, and deployment, all within a single application.
Please feel free to contribute to app and enhance it.


