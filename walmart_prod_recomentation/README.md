# Project: Enhancing Customer Shopping Experience with ML-Based Recommender System

## Introduction
- This project aims to enhance the customer shopping experience on an e-commerce platform(Walmart is used as a sample case study for this project) through the development of a machine learning-based recommender system. 
- The project will leverage cosine similarity and nearest neighbor algorithms, the system will provide personalized product recommendations based on product specifications, titles, manufacturers, and other relevant attributes. These will be based on a certain project that a user might have clicked or viewed, so he can get top K items which are closely related to that he selected based on their content, title, manufacturer etc.

## Problem Statement
- Customers often face overwhelming choices in online shopping platforms. The goal is to ease this issue by implementing a recommender system that assists users in discovering products aligned with their preferences and needs or what they are currently viewing.

## Solution Offered
- To overcome the above problem, this project proposes the creation of a recommendation engine utilizing cosine similarity and nearest neighbor algorithms. This engine will process and analyze key data columns such as specifications, titles, and manufacturers to generate personalized product recommendations for users.

## Data Used
- The dataset used for training and testing the recommender system includes essential columns such as 'Specifications,' 'Title,' 'Uniq Id,' 'Manufacturer,' and other relevant attributes.
- The data was achived by crawing walmart ecommerce site. It contains about 30k records. The data can be accessed from::::<<>>  https://data.world/promptcloud/product-listing-walmart/workspace/file?filename=marketing_sample_for_walmart_com-walmart_com_product__20210401_20210430__30k_data.csv


## Project Workflow Steps
### Engine Creation
    1. Get all data
    2. Clean the product description options
    3. Perform textual cleaning and processing
    4. Perfom Data EDA to get some informational from it
    5. Perform textual vectorization and tokenization
    6. Reduce dimensionality of the vectors to 'n'
    7. Perform similarity matrix scores or nearestneighbour distance computation on the reduced dimensions
    6. Save the algnorithm engine

### Prediction Engine
    1. Use the matrix archived during the training process
    2. Use the ID of the product passed to the engine and retrieve its similarity matrix or NearestNeigbour algrothm.
    3. Sort these matrices and retrieve the top 'k' items
    4. Retrieve the information for these products and return them to the user




### API APPLICATION


This API provides product recommendations based on a given product ID using a pre-trained Nearest Neighbours model. The API can serve as both a web interface and a REST API to generate and display product recommendations.

## Prerequisites

Make sure you have the following installed:

- Python 3.x
- Flask
- Pandas
- Pickle

Ensure you have the following files in the same directory:

- `nn_engine.pkl`: The pre-trained Nearest Neighbours model. You can also change to cosine if you have enough computing.
- `data.pkl`: The dataset containing product information.

## How to Run the API

1. **Clone the repository** and navigate to the project directory:
    ```bash
    git clone git@github.com:Stephen-Kamau/Enhancing-Customer-Shopping-Experience-with-ML-Based-Recommender-System.git
    cd Enhancing-Customer-Shopping-Experience-with-ML-Based-Recommender-System
    ```

2. Install All modules requiresd

3. Start the Flask server:
    ```bash
        python app.py
    ```


4. Access the application:
Open your browser and navigate to` http://127.0.0.1:5000/` to view the web interface.
Use the REST API endpoints to get product recommendations.
   

### Endpoint to List Available Product IDs

#### Endpoint
    GET <base_url>/api/products

#### Description
- This endpoint retrieves a list of available product IDs along with some sample product details.

#### Status Code: 200 OK
#### Response Format: JSON
#### Sample Response:

````
[
  {
    "uniq_id": "sample_id_1",
    "pageurl": "sample_url_1",
    "title": "Sample Product 1",
    "num_of_reviews": 100,
    "specifications": "Sample specifications",
    "manufacturer": "Sample Manufacturer",
    "price": 19.99,
    "stock": 50
  },
  // Add more sample products as needed
]

````


## Endpoint to Get Prediction for a Given Product ID
#### Endpoint
    GET <base_url>/api/predict/<product_id>

#### Description
- This endpoint provides recommendations for a given product ID based on a pre-trained machine learning model.

#### Parameters
- product_id (Path Parameter): The unique identifier of the product for which recommendations are requested.


#### Status Code: 200 OK
#### Response Format: JSON
#### Sample Response:

```json
[
    {
        "Recommended_Product_ID": "eaaa42a5829fb82e667754b31da94a9d",
        "Recommended_Product_Title": "BAND-AID Brand 4 Pack - Band-Aid Brand Adhesive Bandages, Disney/Pixar Toy Story 4, Assorted Sizes, 20 ea",
        "Similarity_Score": 1.0
    },
    {
        "Recommended_Product_ID": "fb6fac806f9d32ebe7c5068fa3f602dd",
        "Recommended_Product_Title": "Travelwell 7” PINK NEOPRENE TABLET ZIP SLEEVE",
        "Similarity_Score": 0.3707931717075194
    },
    //more items recommended
]
```

### Error Response
- If the provided product_id is not found in the database:
#### Status Code: 404 Not Found
#### Response Format: Plain Text
#### Sample Response for Error:
    ```Product with Id sample_id_1 not found in the database```


## ACCESS REPOSITORY
---
[Walmart Product Recommendation model and API](https://github.com/Stephen-Kamau/Enhancing-Customer-Shopping-Experience-with-ML-Based-Recommender-System)

---



---
Cheers!!
Feel free to reach out for contributions
---