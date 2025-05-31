# Cultive_Connect

**FAOSTAT Agricultural Producer Prices: ETL & Data Insights**

## Project Overview

This repository contains a Python notebook that implements an Extract, Transform, Load (ETL) pipeline to programmatically fetch agricultural producer price data from the FAOSTAT API. The primary objective is to acquire clean, structured, and consistent annual price data for selected countries across North, Central, and South America.

Beyond the core ETL process, the notebook also incorporates initial data analysis and visualization. These integrated visuals are designed to provide an immediate and better understanding of the extracted data's key trends, distributions, and regional insights. This modular approach enhances the clarity of the data engineering workflow by providing instant feedback on the processed dataset, while still allowing for more in-depth analysis in separate environments if needed.

Finally, the processed and explored data is prepared for storage, typically in a Google Drive environment for further use.

## Features

### Data Extraction (E)
Programmatically fetches agricultural producer price data from the FAOSTAT API using defined parameters (countries, commodities, years, etc.).

### Data Transformation (T)
- Cleans and renames columns for clarity and consistency
- Removes irrelevant or redundant columns
- Filters out non-American countries after extraction to focus on the target regions
- Categorizes countries into 'North America', 'Central America', and 'South America' by adding a new 'Region' column
- Includes checks for zero values in price data, highlighting potential data anomalies

### Initial Data Exploration & Visualization
Generates key visualizations to provide immediate insights:
- Distribution of Producer Prices (with Log Scale)
- Average Producer Price over Years
- Average Producer Price per Region
- Top 10 Commodities by Average Price

### Data Loading (L)
Prepares the processed data for storage (e.g., to Google Drive, though the saving mechanism itself might be a subsequent step or user action).

## Data Source

The data is sourced from the **FAOSTAT API**, specifically the "Producer Prices" domain. The parameters for the API request (country codes, item codes, years, etc.) are defined within the notebook and can be updated to reflect changes in FAOSTAT's interface or desired filters.

## Prerequisites

To run this notebook, you will need:

- **Google Colab Environment**: The notebook is designed to run seamlessly in Google Colab
- **Google Drive Mounted**: The script assumes you will mount your Google Drive within the Colab environment, as it's intended for processed data storage
- **Python Libraries**: `pandas`, `requests`, `io`, `matplotlib.pyplot`, `seaborn`. These are typically pre-installed in Colab or can be installed via pip

## Usage

1. **Open in Google Colab**: Upload or open the `.ipynb` file in Google Colab
2. **Mount Google Drive**: Run the cell to mount your Google Drive (if you intend to save data there)
3. **Run All Cells**: Execute all cells sequentially. The notebook will:
   - Define API parameters
   - Fetch data from FAOSTAT
   - Perform data cleaning, filtering, and region categorization
   - Generate and display the various data visualizations
   - Print summary statistics and unique country lists

## Key Insights from Visualizations

The integrated visualizations provide a quick understanding of the agricultural producer price landscape:

### Average Producer Price by Region: Summary of Insights

The chart reveals a clear hierarchy in average producer prices across the Americas: **North America leads significantly**, followed by Central America, and then South America with the lowest average.

- **North America's Premium**: Higher prices are likely due to elevated production costs (labor, inputs, regulations), a focus on higher-value/processed agricultural products, and stronger market demand
- **Central America's Middle Ground**: Its intermediate position suggests a mix of agricultural practices and commodity types, yielding prices between North and South America
- **South America's Lower Average**: This is primarily driven by its role as a major global supplier of bulk commodities (e.g., soybeans, corn) which have lower prices per tonne, alongside potentially lower production costs

### Average Producer Price Over Time: Summary of Insights

The average producer price (USD/tonne) has shown a **clear upward trend from 2000 to 2024**, with notable fluctuations:

- **Overall Uptrend (2000-2024)**: Driven by global population growth, increased demand, and rising production costs (e.g., inflation, inputs like fuel and fertilizer)
- **2014 Spike (~$1300)**: Likely attributed to a global commodity boom, strong demand from emerging markets, and high energy prices
- **2016 Drop (~$1100)**: A market correction occurred due to potential oversupply, global economic slowdown, or falling energy prices that reduced input costs
- **Sustained Increase (2016-2024 to ~$1600)**: A strong rebound and continued rise were influenced by renewed global demand, significant supply chain disruptions (e.g., post-pandemic, geopolitical conflicts), persistently high input costs, and general inflationary pressures

### Top 10 Commodities by Average Producer Price: Summary of Insights

This chart highlights which commodities command the highest average producer prices per tonne:

- **High-Value Specialty/Perishable Crops Lead**: Coffee (green), Raspberries, and Blueberries are at the top (approaching $3,600 USD/tonne). Their high prices are driven by perishability, specialized growing conditions, labor intensity, and strong consumer demand
- **Meat Products in the Mid-Range**: Meat of pig and Meat of chickens feature in the middle (around $1,800 - $2,200 USD/tonne), reflecting processing requirements and feed costs
- **Cocoa Beans and Strawberries are Notable**: Cocoa beans maintain a high value due to global demand, and Strawberries reinforce the trend of perishable fruits commanding higher prices
- **Lower-Priced Staples at the Bottom of this Top 10**: Hen eggs, Cotton lint, and Avocados (around $900 - $1,600 USD/tonne) represent commodities with high volume or different market dynamics compared to the top-tier items

## Contributing

Contributions are welcome! If you have suggestions for improvements, feature additions, or bug fixes, please feel free to open an issue or submit a pull request.

## License

This project is open-sourced under the **MIT License**.
