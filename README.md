# Lead-Evaluation-Tool

## Overview
This project involves analyzing dealer leads from a toolbox dataset and comparing it against a master dataset to evaluate the status of product usage. The script identifies potential leads based on product inquiries and their current usage status, categorizing them into different color-coded groups for easy identification.

## Purpose
The primary goal of the script is to:
- Evaluate dealer leads by comparing their product inquiries to their current product usage.
- Assign a color code to each lead based on their status (e.g., whether they have leads, are canceling, etc.).
- Generate a summary description for each lead, indicating their product usage and inquiries.

## Key Components

### Color Enumeration
The `Colors` class defines the different categories of leads:
- **RED**: No leads identified.
- **GREEN**: Potential leads exist.
- **BLUE**: Potential leads exist, but the dealer also said "no" on a product they already use.

### Product Mapping
The `product_map` dictionary maps the product codes from the toolbox to their respective product names in the master dataset.

### Data Processing
1. **Loading Data**: The script reads the toolbox and master datasets into pandas DataFrames.
2. **Data Cleaning**: It converts dealer codes to strings and removes leading zeroes from the master dataset's dealer codes to ensure proper matching.

### Lead Evaluation
The `evaluate_lead` function processes each row in the toolbox dataset:
- It checks if the dealer code exists in the master dataset.
- It evaluates each product inquiry against the current usage status in the master dataset.
- It determines the lead status and assigns a corresponding color based on the evaluation criteria.

### Result Compilation
The results of the evaluation are compiled, and:
- The toolbox DataFrame is updated with the evaluated leads, colors, and descriptions.
- The final results are saved into a CSV file named `toolbox_copy.csv`.

### Output Files
The script generates multiple CSV files based on lead categories:
- Each category (color) has its own file for easy access and review.

## How to Use
1. Place the `toolbox.csv` and `mastermonth.csv` files in the same directory as the script.
2. Run the script to evaluate leads.
3. The results will be saved in `toolbox_copy.csv`, along with individual files for each lead category.

## Customization
You can customize the script by:
- Modifying the `product_map` dictionary for different product mappings.
- Adjusting the `Colors` enumeration for additional lead categories.
- Changing the range of rows processed by modifying the `start_row` and `end_row` variables.
