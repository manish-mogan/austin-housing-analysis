# Visual 2: Living Area vs. Price Relationship

## Overview
This interactive visualization explores how property size and amenities influence housing prices in the Austin area, demonstrating that larger homes with better features and proximity to strong school districts tend to command higher prices.

## Running the Visualization

### Prerequisites
Install required Python packages:
```bash
pip install pandas altair numpy scipy jupyter
```

### Execute the Notebook
1. Open `Visual 2.ipynb` in Jupyter Notebook or JupyterLab
2. Run all cells sequentially
3. The interactive visualization will appear in the final cell

### Alternative: Command Line Execution
```bash
jupyter nbconvert --to notebook --execute "Visual 2.ipynb" --output "Visual 2_output.ipynb"
```

## Visualization Features

### Main Components

#### 1. Scatter Plot (Top)
- **X-axis**: Living Area in square feet
- **Y-axis**: Property Price in USD
- **Data Points**: 15,171 Austin homes
- **Regression Line**: Black dashed line showing price trend
- **R² Annotation**: Shows correlation strength (0.2181)

#### 2. Linked Histogram (Bottom)
- **X-axis**: Property Price in USD (30 bins)
- **Y-axis**: Number of Homes
- **Filtering**: Updates based on scatter plot selection

### Interactive Features

#### Color Coding by School Quality
- 🔴 **Red**: Below Average (0-3 rating) - 893 homes
- 🟠 **Orange**: Average (3-5 rating) - 5,402 homes
- 🔵 **Blue**: Good (5-7 rating) - 5,440 homes
- 🟢 **Green**: Excellent (7-10 rating) - 3,436 homes

#### Hover Tooltips
Move your mouse over any point to see:
- Street address and city
- Living area (sq ft)
- Property price
- Number of bedrooms
- Number of bathrooms
- School rating (0-10 scale)
- Amenity score (0-5)
- Year built

#### Brush Selection
1. Click and drag on the scatter plot to select a region
2. Selected points retain their school quality colors
3. Unselected points turn gray
4. Histogram automatically filters to show only selected homes
5. Click outside selection to reset

## Key Statistics

| Metric | Value |
|--------|-------|
| Total Homes | 15,171 |
| Living Area Range | 378 - 14,000+ sq ft |
| Price Range | $7,750 - $5,000,000+ |
| Correlation (R²) | 0.2181 (weak positive) |
| Price per sq ft | ~$153.53 average increase |

## Insights & Analysis

### Observed Patterns
1. **Positive Correlation**: Larger homes generally command higher prices
2. **School Premium**: Homes near excellent schools (green) often show premium pricing
3. **Market Segments**: Distinct clusters visible for different property types
4. **Price Distribution**: Histogram reveals concentration in mid-range prices

### Use Cases
- **Buyers**: Compare properties by size, price, and school quality
- **Sellers**: Understand pricing relative to living area and location
- **Analysts**: Explore market trends and price distributions
- **Researchers**: Study correlation between property features and prices

## Technical Details

### Data Source
- **File**: `data.csv`
- **Records**: 15,171 properties
- **Location**: Austin, Texas metropolitan area

### Technology Stack
- **Visualization**: Altair 5.5.0 (with JSON data transformer enabled for large datasets)
- **Data Processing**: Pandas 2.3.3
- **Statistics**: SciPy 1.16.2, NumPy 2.3.4
- **Environment**: Python 3.12.3

### Important Note on Data Size
The visualization uses Altair's JSON data transformer (`alt.data_transformers.enable('json')`) to handle the 15,171 property records, which exceeds Altair's default 5,000-row limit. This transformer saves the data to temporary JSON files instead of embedding it directly in the visualization, enabling smooth rendering of large datasets.

### Amenity Score Calculation
The amenity score (0-5) is calculated by counting these features:
- Garage (hasGarage)
- Air Conditioning (hasCooling)
- Heating (hasHeating)
- Spa (hasSpa)
- View (hasView)

## Accessibility
- High-contrast color palette for school quality categories
- Clear legends and annotations
- Large, readable text labels
- Color-blind friendly palette selection

## Notes
- The R² value of 0.2181 indicates a weak positive correlation between living area and price
- This suggests that while size matters, other factors (location, school quality, amenities) significantly influence pricing
- The visualization enables exploration of these multifaceted relationships

## Support
For issues or questions, refer to the main repository documentation.
