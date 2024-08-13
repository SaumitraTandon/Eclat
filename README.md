# Eclat Algorithm for Market Basket Analysis

This project demonstrates the implementation of the Eclat algorithm, a simple and efficient method for frequent itemset mining in Market Basket Analysis. The objective is to identify items that frequently appear together in transactions.

## Project Overview

- **Eclat Algorithm**: Eclat (Equivalence Class Clustering and bottom-up Lattice Traversal) is used for finding frequent itemsets in transaction data. Unlike the Apriori algorithm, Eclat uses a depth-first search approach for discovering frequent itemsets, making it faster in some cases.
- **Market Basket Analysis**: This technique helps in understanding customer purchase behavior by analyzing the associations between different products bought together.

## Getting Started

### Prerequisites

You need to have the following libraries installed:

```bash
pip install apyori
```

Additionally, standard libraries for data manipulation and visualization are required:

```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
```

### Installation

1. Clone the repository to your local machine:

    ```bash
    git clone https://github.com/yourusername/your-repository.git
    cd your-repository
    ```

2. Install the required Python packages:

    ```bash
    pip install -r requirements.txt
    ```

3. Ensure you have the dataset named `Market_Basket_Optimisation.csv` in your project directory.

### Running the Project

The project is structured as a Jupyter notebook. You can run it step-by-step as follows:

1. **Data Preprocessing**: The dataset is loaded and processed into a format suitable for the Eclat algorithm.

    ```python
    dataset = pd.read_csv('Market_Basket_Optimisation.csv', header=None)
    transactions = []
    for i in range(0, 7501):
        transactions.append([str(dataset.values[i,j]) for j in range(0, 20)])
    ```

2. **Training the Eclat Model**: The Eclat model is trained using the processed transaction data. (Note: The implementation here seems to use `apyori` which is traditionally for Apriori; ensure Eclat is correctly implemented).

    ```python
    from apyori import apriori
    rules = apriori(transactions=transactions, min_support=0.003, min_confidence=0.2, min_lift=3, min_length=2, max_length=2)
    ```

3. **Visualizing the Results**: The discovered frequent itemsets and association rules are visualized and sorted, focusing on support as the key metric.

    ```python
    results = list(rules)
    ```

    The results can be further organized into a Pandas DataFrame and sorted by support:

    ```python
    resultsinDataFrame.nlargest(n=10, columns='Support')
    ```

## Project Structure

- `eclat.ipynb`: The main Jupyter notebook containing the implementation.
- `Market_Basket_Optimisation.csv`: The dataset used for training the model.
- `README.md`: Project documentation.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request with your suggestions or improvements.
