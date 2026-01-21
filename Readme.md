# Sales Data Analysis Project

## 🎥 Project Presentation
**[Watch the Complete Project Walkthrough](https://drive.google.com/file/d/1r5hr2fmdK2vDjAO6Av_GT2rKkfqwRCTj/view?usp=sharing)**

### Key Highlights:
- 📊 Comprehensive sales data analysis across 3+ years (2015-2017)
- 🔄 Data integration from multiple CSV sources into unified dataset
- 🗃️ MySQL database implementation for efficient querying
- 📈 Revenue analysis by products, customers, and territories
- 🧹 Data cleaning and preprocessing pipeline

## 📁 Project Structure

```
├── demo.ipynb                    # Main analysis notebook
├── output.csv                    # Generated output file
├── returns.csv                   # Returns analysis export
└── dataset/
    ├── All_Sales_Clean.csv       # Consolidated clean sales data
    ├── calendar.csv              # Date dimension table
    ├── customers.csv             # Customer information
    ├── product_categories.csv    # Product category mappings
    ├── product_subcategories.csv # Product subcategory details
    ├── products.csv              # Product catalog
    ├── returns.csv               # Returns data
    ├── sales_2015.csv           # 2015 sales transactions
    ├── sales_2016.csv           # 2016 sales transactions
    ├── sales_2017.csv           # 2017 sales transactions
    └── territories.csv          # Sales territory information
```

## 🚀 Getting Started

### Prerequisites
```bash
pip install pandas numpy sqlalchemy pymysql
```

### Data Pipeline
The project implements a complete ETL pipeline:

1. **Extract**: Load multiple CSV files from the [dataset/](dataset/) folder
2. **Transform**: Clean and standardize data formats, especially date handling
3. **Load**: Import data into MySQL database for analysis

### Key Features

#### 📊 Data Integration
- Combines sales data from 2015-2017 into a unified dataset ([All_Sales_Clean.csv](dataset/All_Sales_Clean.csv))
- Standardizes date formats using US format (MM/DD/YYYY)
- Handles encoding issues (Latin1 for customer data)

#### 🔗 Relational Structure
The data follows a star schema with these key relationships:
- `sales_*.ProductKey` → [`products.ProductKey`](dataset/products.csv)
- `sales_*.CustomerKey` → [`customers.CustomerKey`](dataset/customers.csv)
- `sales_*.TerritoryKey` → [`territories.SalesTerritoryKey`](dataset/territories.csv)

#### 📈 Analysis Capabilities
- Product-wise revenue calculation
- Customer segmentation analysis
- Territory performance metrics
- Returns analysis integration

## 💾 Database Integration

The project includes MySQL database setup with automatic table creation. All CSV files are automatically imported as database tables for efficient querying.

## 📋 Data Schema

### Sales Tables Structure
- **OrderDate, StockDate**: Transaction timestamps
- **OrderNumber**: Unique order identifier
- **ProductKey**: Links to product catalog
- **CustomerKey**: Links to customer information
- **TerritoryKey**: Links to sales territories
- **OrderLineItem**: Line item sequence
- **OrderQuantity**: Quantity sold

### Supporting Tables
- **Products**: Product catalog with pricing and descriptions
- **Customers**: Customer demographics and information
- **Territories**: Sales territory definitions
- **Returns**: Product return transactions
- **Calendar**: Date dimension for time-based analysis

## 🛠️ Usage

1. Clone the repository
2. Install required dependencies
3. Run the [demo.ipynb](demo.ipynb) notebook for complete analysis
4. Generated outputs will be saved as CSV files

## 📊 Output Files
- [`output.csv`](output.csv): Analysis results export
- [`returns.csv`](returns.csv): Returns analysis data
- [`All_Sales_Clean.csv`](dataset/All_Sales_Clean.csv): Consolidated sales dataset

## 🔧 Technical Notes
- Handles multiple date formats and encoding issues
- Implements error handling for data quality issues
- Uses pandas for data manipulation and analysis
- SQLAlchemy for database operations
