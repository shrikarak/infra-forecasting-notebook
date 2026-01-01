# Predictive IT Infrastructure Management: CPU Usage Forecasting

**Copyright (c) 2026 Shrikara Kaudambady**

This project provides a Jupyter notebook that demonstrates a key AI/ML application for IT Infrastructure Management: **predictive resource forecasting**. The notebook builds a time-series model using the `prophet` library to forecast future server CPU utilization based on historical trends and seasonal patterns.

## Solution Explanation

Proactive capacity planning is essential for maintaining a stable and cost-effective IT infrastructure. By accurately forecasting future resource needs, organizations can prevent performance bottlenecks, avoid service outages, and optimize hardware expenditure.

This solution uses Facebook's `prophet` library, an open-source forecasting tool that is powerful yet simple to use. It is particularly well-suited for business forecasts as it robustly handles the multi-level seasonality (e.g., daily, weekly) common in infrastructure metrics.

The workflow implemented in the notebook is as follows:

1.  **Synthetic Data Generation:** To make the notebook self-contained, it programmatically generates a realistic time-series dataset simulating hourly CPU usage over several months. This data includes a baseline load, a gradual upward trend, daily and weekly seasonal cycles, and random noise.
2.  **Model Training:** An instance of the `Prophet` model is trained on the historical data. Prophet's algorithm automatically decomposes the time series to learn its underlying trend and seasonalities.
3.  **Forecasting:** The trained model is used to predict CPU utilization for a future period (in this case, the next 30 days). The forecast includes a central prediction (`yhat`) and an uncertainty interval (`yhat_lower`, `yhat_upper`) which provides a probabilistic range for the forecast.
4.  **Visualization and Interpretation:** The notebook uses Prophet's built-in plotting functions to visualize the forecast and its components.
    - The **forecast plot** shows the historical data, the future prediction, and the uncertainty bounds.
    - The **components plot** breaks the forecast down into its constituent parts: the overall trend, weekly seasonality (e.g., lower usage on weekends), and daily seasonality (e.g., lower usage at night). This is extremely useful for understanding the drivers of CPU demand.

## How to Use

Follow these steps to set up the environment and run the forecasting notebook.

### 1. Clone the Repository
If this project is on a Git repository, clone it to your local machine:
```bash
git clone <repository-url>
cd gemini-cli-projects/infra-forecasting-notebook
```

### 2. Create a Virtual Environment
It is highly recommended to use a virtual environment to avoid conflicts with other projects.
```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies
Install all the required Python libraries using the `requirements.txt` file.

**Note:** The `prophet` library has dependencies that can sometimes be complex to install. Using a virtual environment and `pip` is the most straightforward approach. If you encounter issues, please refer to the official [Prophet installation guide](https://facebook.github.io/prophet/docs/installation.html).

```bash
pip install -r requirements.txt
```

### 4. Launch Jupyter
Start the Jupyter Notebook server from your terminal.
```bash
jupyter notebook
```
A new tab should open in your browser with the project directory.

### 5. Run the Notebook
Click on the `cpu_usage_forecasting.ipynb` file to open it. You can then run the cells in sequence to generate the data, train the model, and visualize the forecast.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for full details.
