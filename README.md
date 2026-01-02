# Information Bottleneck Tutorial

A Docker Container-based Jupyter Notebook server that provides an interactive tutorial on the **Information Bottleneck (IB)** principle in information theory.

## Overview

This tutorial covers:
- **Mathematical foundations** of the Information Bottleneck principle
- **Synthetic example**: Binary noisy channel demonstrating how observation of one random variable (X) can infer information about another unobservable variable (Y)
- **Real-world application**: Document clustering using IB-inspired methods

## What is Information Bottleneck?

The Information Bottleneck is a fundamental concept in information theory that provides a principled approach to compress information while preserving what's relevant for a specific task. It seeks to find a compressed representation T of input X that:
1. Minimizes information about X (compression)
2. Maximizes information about target Y (preserves relevance)

## Prerequisites

- Docker installed on your system
- Docker Compose (optional, but recommended)

## Quick Start

### Option 1: Using Docker Compose (Recommended)

```bash
# Build and start the Jupyter server
docker-compose up --build

# Access the notebook at http://localhost:8888
```

### Option 2: Using Docker directly

```bash
# Build the Docker image
docker build -t ib-tutorial .

# Run the container
docker run -p 8888:8888 -v $(pwd):/workspace ib-tutorial

# Access the notebook at http://localhost:8888
```

## Accessing the Notebook

Once the container is running:
1. Open your web browser
2. Navigate to `http://localhost:8888`
3. Open `information_bottleneck_tutorial.ipynb`
4. Run the cells to explore the tutorial

**Note**: The notebook is configured without authentication for ease of use. Do not expose this to the public internet.

## Tutorial Contents

### 1. Mathematical Foundations
- Entropy and mutual information
- The Information Bottleneck optimization problem
- Theoretical framework

### 2. Synthetic Example: Binary Noisy Channel
- Medical diagnosis scenario
- Demonstrates inference of disease state (Y) from noisy test results (X)
- Visualization of different compression schemes
- Information bottleneck trade-off curves

### 3. Real-World Application: Document Clustering
- Text document dataset across multiple topics
- TF-IDF feature extraction
- IB-inspired clustering
- Analysis of compression vs. topic preservation trade-off

### 4. Practical Insights
- Applications in deep learning, feature selection, and privacy
- Connection to machine learning and generalization

## Repository Structure

```
.
├── Dockerfile                           # Docker image definition
├── docker-compose.yml                   # Docker Compose configuration
├── requirements.txt                     # Python dependencies
├── information_bottleneck_tutorial.ipynb # Main tutorial notebook
└── README.md                            # This file
```

## Dependencies

The tutorial uses the following Python libraries:
- `jupyter` - Jupyter Notebook server
- `numpy` - Numerical computing
- `matplotlib` - Plotting and visualization
- `scipy` - Scientific computing
- `pandas` - Data manipulation
- `seaborn` - Statistical visualization
- `scikit-learn` - Machine learning tools

## Stopping the Server

To stop the Jupyter server:

```bash
# If using docker-compose
docker-compose down

# If using docker run
# Press Ctrl+C in the terminal where the container is running
```

## References

- Tishby, N., Pereira, F. C., & Bialek, W. (1999). "The information bottleneck method."
- Tishby, N., & Zaslavsky, N. (2015). "Deep learning and the information bottleneck principle."

## License

This tutorial is provided for educational purposes.

## Contributing

Feel free to open issues or submit pull requests to improve the tutorial.
