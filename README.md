# Climate-Resilient-Agriculture
Assignment for the Project on Climate Resilient Agriculture

## Running the Python Noteboook

For running the python notebook on

1. Colab: upload the rainfall data csv file as ranifall.csv file on colab runtime and run all the cell in notebook
2. Jupyter Notebook: Uploar the rainfall data csv file as ranifall.csv file in same folder as Jupyter Notebook and run all the cell in notebook

## Soil Model

The Class Soil Model, model the soil based on the soil type and maximum uptake value of a crop. The Soil is modelled as follow:

sm(n-1): soil content on the previous day
rain(n): rain today
rainoff(n): alpha * rain(n)
infiltration(n): rain(n) - rainoff(n)

If Infiltraion(n) + sm(n-1) > C, the excess(n) = Infiltraion(n) + sm(n-1) - C goes as rainoff water:
updated:
rainoff(n): excess(n) + rainoff(n)
infiltration(n): rain(n) - rainoff(n){Updated}

Now Crop take water uptake(n), if current soil moisture > max uptake by crop, crop takes the max uptake amount of water else it takes all the avaialble amount of water.

At end, percentage of remaining water goes to ground water such that at end: groundwater(n) = sm(n) * gamama

## Valiadation

The model is validated on the principle that rain water can neither be created nor be destroyed

Hence for Day Equillibirum:

rain(n) = sm(n) - sm(n-1) + runoff(n) + excess(n) + uptake(n) + gw(n)

And for the period in focus equillibirum:

∑rain(n) = sm(n) + ∑runoff(n) + ∑excess(n) + ∑uptake(n) + ∑gw(n)



## Files

PoCRA.ipynb - Python Notebook
rainfall.csv - Input Data
deep.csv - Output Data for Deep Soil type
shallow.csv - Output Data for Shallow Soil type
