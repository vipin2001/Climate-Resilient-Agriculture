# Climate-Resilient-Agriculture
Assignment for the Project on Climate Resilient Agriculture


## Links

[Report in Google Docs](https://docs.google.com/document/d/1T4DTIi3QMJ5pMc_Z4trxgu615qXwWxIiUQAP3m5w26I/edit?usp=sharing) <br>
[Demo Video](https://drive.google.com/file/d/1CykIO-5i17youm2cSxU59Twcn2UiMhIk/view?usp=sharing)
## Running the Python Noteboook

For running the python notebook on <br>

1. Colab: upload the rainfall data csv file as ranifall.csv file on colab runtime and run all the cell in notebook
2. Jupyter Notebook: Uploar the rainfall data csv file as ranifall.csv file in same folder as Jupyter Notebook and run all the cell in notebook

## Soil Model

The Class Soil Model, model the soil based on the soil type and maximum uptake value of a crop. The Soil is modelled as follow: <br>
 <br>
sm(n-1): soil content on the previous day <br>
rain(n): rain today <br>
rainoff(n): alpha * rain(n) <br>
infiltration(n): rain(n) - rainoff(n) <br>
 <br>
If Infiltraion(n) + sm(n-1) > C, the excess(n) = Infiltraion(n) + sm(n-1) - C goes as runoff water: <br>
updated: <br>
rainoff(n): excess(n) + rainoff(n) <br>
infiltration(n): rain(n) - rainoff(n){Updated} <br>

Now Crop take water uptake(n), if current soil moisture > max uptake by crop, crop takes the max uptake amount of water else it takes all the avaialble amount of water. <br>

At end, percentage of remaining water goes to ground water such that at end: groundwater(n) = sm(n) * gamama <br>

## Valiadation

The model is validated on the principle that rain water can neither be created nor be destroyed.  <br>
 <br>
Hence for Day Equillibirum: <br>
 <br>
rain(n) = sm(n) - sm(n-1) + runoff(n) + excess(n) + uptake(n) + gw(n) <br>
 <br>
And for the period in focus equillibirum: <br>
 <br>
∑rain(n) = sm(n) + ∑runoff(n) + ∑excess(n) + ∑uptake(n) + ∑gw(n) <br>



## Files
 <br>
PoCRA.ipynb - Python Notebook <br>
rainfall.csv - Input Data <br>
deep.csv - Output Data for Deep Soil type <br>
shallow.csv - Output Data for Shallow Soil type <br>
