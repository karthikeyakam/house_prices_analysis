# Ames house_prices_analysis

Analysing Ames, Iowa housing data taken from Kaggle (https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data). You can refer the following post for detailed understanding (https://medium.com/@krishkk238/house-prices-analysis-70a56ea360ab)

## Business Understanding and Environment 
The project was created on Jupyter notebook as a part of Udacity Data Scientist nanodegree program.
The analysis covers the following points:
- How are the Sales trending overtime?
- How is the presence of a Fireplace impacting the Sale Price?
- How is the Sale Price distributed by different Garage Types?

## Libraries used
- pandas
- numpy
- matplotlib
- seaborn
- scipy
- statsmodels
- sklearn

## Data Description
Here's a brief version of what you'll find in the data description file.

- SalePrice - the property's sale price in dollars. This is the target variable that you're trying to predict.
- MSSubClass: The building class
- MSZoning: The general zoning classification
- LotFrontage: Linear feet of street connected to property
- LotArea: Lot size in square feet
- Street: Type of road access
- Alley: Type of alley access
- LotShape: General shape of property
- LandContour: Flatness of the property
- Utilities: Type of utilities available
- LotConfig: Lot configuration
- LandSlope: Slope of property
- Neighborhood: Physical locations within Ames city limits
- Condition1: Proximity to main road or railroad
- Condition2: Proximity to main road or railroad (if a second is present)
- BldgType: Type of dwelling
- HouseStyle: Style of dwelling
- OverallQual: Overall material and finish quality
- OverallCond: Overall condition rating
- YearBuilt: Original construction date
- YearRemodAdd: Remodel date
- RoofStyle: Type of roof
- RoofMatl: Roof material
- Exterior1st: Exterior covering on house
- Exterior2nd: Exterior covering on house (if more than one material)
- MasVnrType: Masonry veneer type
- MasVnrArea: Masonry veneer area in square feet
- ExterQual: Exterior material quality
- ExterCond: Present condition of the material on the exterior
- Foundation: Type of foundation
- BsmtQual: Height of the basement
- BsmtCond: General condition of the basement
- BsmtExposure: Walkout or garden level basement walls
- BsmtFinType1: Quality of basement finished area
- BsmtFinSF1: Type 1 finished square feet
- BsmtFinType2: Quality of second finished area (if present)
- BsmtFinSF2: Type 2 finished square feet
- BsmtUnfSF: Unfinished square feet of basement area
- TotalBsmtSF: Total square feet of basement area
- Heating: Type of heating
- HeatingQC: Heating quality and condition
- CentralAir: Central air conditioning
- Electrical: Electrical system
- 1stFlrSF: First Floor square feet
- 2ndFlrSF: Second floor square feet
- LowQualFinSF: Low quality finished square feet (all floors)
- GrLivArea: Above grade (ground) living area square feet
- BsmtFullBath: Basement full bathrooms
- BsmtHalfBath: Basement half bathrooms
- FullBath: Full bathrooms above grade
- HalfBath: Half baths above grade
- Bedroom: Number of bedrooms above basement level
- Kitchen: Number of kitchens
- KitchenQual: Kitchen quality
- TotRmsAbvGrd: Total rooms above grade (does not include bathrooms)
- Functional: Home functionality rating
- Fireplaces: Number of fireplaces
- FireplaceQu: Fireplace quality
- GarageType: Garage location
- GarageYrBlt: Year garage was built
- GarageFinish: Interior finish of the garage
- GarageCars: Size of garage in car capacity
- GarageArea: Size of garage in square feet
- GarageQual: Garage quality
- GarageCond: Garage condition
- PavedDrive: Paved driveway
- WoodDeckSF: Wood deck area in square feet
- OpenPorchSF: Open porch area in square feet
- EnclosedPorch: Enclosed porch area in square feet
- 3SsnPorch: Three season porch area in square feet
- ScreenPorch: Screen porch area in square feet
- PoolArea: Pool area in square feet
- PoolQC: Pool quality
- Fence: Fence quality
- MiscFeature: Miscellaneous feature not covered in other categories
- MiscVal: $Value of miscellaneous feature
- MoSold: Month Sold
- YrSold: Year Sold
- SaleType: Type of sale
- SaleCondition: Condition of sale

## Evaluate the Results
### How are the Sales trending overtime?
When average Sales is plotted against Year sold, you observe a dip in Sale Price in 2008 through 2010 compared to 2007. I assume that this could be mainly due to the Great Recession lasting from December 2007 to June 2009, which also explains the peak in the sales before 2007.

### How is the presence of a Fireplace impacting the Sale Price? 
As expected, the average Sale Price increases drastically with a presence of one fireplace by around 33% whereas the increase is around 11% from having 2 fireplaces vs one fireplace. Of course, this will not give us the complete insight as there could be many other factors out of which one main factor would be number of rooms or the size of the house which are co-related. So, for further analysis, I have considered to include number of rooms into my analysis with the fireplace.

I have only considered number of rooms greater than 3 and till 7 for a better analysis. As you can see, along the each value of number of rooms, we have there is a drastic increase in Sale Price with one fireplace compared to one without a fireplace. For houses with 3 rooms there is an increase of Sale Price by 28% and for houses with 4 rooms its 23% and with 5 rooms its 24%.

### How is the Sale Price distributed by different Garage Types?
If we distribute the Sale Prices against different Garage Types, we observe that houses with Attached Garage and Built-in Garage have higher mean compared to others. Built-in Garage houses have wider distribution between 1st and 3rd quartile. For Attached Garage houses, there are many outliers to be looked into for our analysis.