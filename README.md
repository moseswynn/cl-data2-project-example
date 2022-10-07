# StockX Price Monitor

## Project Brief
### Purpose
This notebook will allow the user to search for items from StockX, select a product or multiple products that they would like to analyze, and provide key metrics about the price and volume of sales that can aid in the decision to execute or wait on a purchase or sale of a product.

### Features:

#### **Read TWO datasets from an API**

This project will first ingest a dataset from the stockX API when searching for a product based on input provided by the user. The user will be able to perform multiple searches and select multiple products. Once finished selecting products, 3 datasets will be loaded for each product selected:

- Asks - the historical prices at which sellers have listed the product.
- Bids - the historical prices at which buyers have offered to purchase the product.
- Sales - the historical prices at which transactions between buyers and sellers have been executed.

#### **Clean your data and perform a pandas merge with your two data sets, then calculate some new values based on the new data set**

For each selected product, the asks, bids, and sales will have an additional column indicating the type. If multiple products are selected, another column for the product label will be added.Outliers will be filtered out of each dataset, and then the datasets will be appended to each other.

#### **Make 3 matplotlib or seaborn (or another plotting library) visualizations to display your data**

Once the data for the product has been summarized, the following charts will be displayed, users will be able to select which charts they want to display:

- The gap between the asking and bidding price will be displayed in a boxplot summarized by rolling *n* days. If multiple products are selected, a widget will allow the user to select which chart the product is for. This gap could indicate the following scenarios:
    - For sellers looking to quickly offload merchandise at a lower profit margin, they should execute when the gap is wide to the benefit of bidders (negative).
    - For sellers looking to increase profits, they should execute when the gap is narrow to the benefit of bidders, or to the benefit of sellers (positive).
    - For purchasers looking to increase savings, they should execute when the gap is wide to the benefit of bidders.
- If multiple products are selected, a chart showing the rolling average sale price for up to 3 products can be shown. The user will be asked which products to compare if more than 3 were selected. This chart can help purchasers determine which product they should purchase or help sellers determine which product they should focus on marketing.
- A scatter plot will be shown to compare the volume of sales to a binned range of sale prices, the user will be able to select the period of time to analyze and, if multiple products are selected, which product to analyze. This metric will help sellers determine their best asking price for a quick sale and purchasers their best bidding price for a likely win.

#### **Utilize a virtual environment and include instructions in your README on how the user should set one up**

The project will include a *pyproject.toml* file and a *requirements.txt* file, allowing the user to install all dependencies using the dependency management tool of their choice. Instructions will be included for using poetry or venv to setup the project.

### Interpretation
This project will contain two notebooks:
- *main.py* - where the user can run their own analyses
- *example.py* - an example notebook where an analysis has already been run.

The main notebook will contain descriptions of possible scenarios and how to interpret the provided metrics.

The example notebook will contain a specific example of an analysis performed on an individual product.

Finally, the user will be able to generate an export that will output a PDF file containing the charts and descriptions on how to interpret them, based on their specified scenario.