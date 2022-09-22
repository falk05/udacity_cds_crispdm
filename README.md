# Udacity Citizen Data Scientist Nanodegree #

Author: Erik Sokolovsky <br>
Date: September 2022 <br>
Public Github repo: https://github.com/falk05/udacity_cds_crispdm.git <br>

**Project Motivation:**
We analyse data gathered from charging stations for electric vehicles installed in a multi-space private parking garage. The intention is to see what insights can be gained from the charging behaviour of the different EV owners.  We attempt to answer the following questions: What can we infer from the charging patterns observed to date? What cost savings could EV owners achieve without changing their vehicle usage pattern? And, can we forecast hourly energy demand from historical charging data and meteorological data?  The blog post published for this project is available on Medium:  


**Results of the analysis:**
1. The charging pattern shows that most of the charging kicks off at about 4pm and much of the overnight charging takes place before 3am.  The different charging patterns exposed by different EV owners will have different long-term effects on battery longevity.
2. EV owners can lower the energy costs for charging their EV by shifting the charging from high-tariff periods to low-tariff periods, without having to change the way they use their vehicle.
3. Energy demand from the EV chargers can be predicted quite well using a non-linear regression model.


**Libraries used:** <br>
**Base libaries used:** <br>
pandas <br>
numpy <br>
datetime <br>

**For data import into pandas dataframe, the following libraries are used** <br>
json <br>
csv <br>
os.read <br>
pandas.io <br>

**For visualization, we use:** <br>
seaborn <br>
matplotlib <br>

**For building the ML regression model, we use:** <br>
sklearn (scikit) <br>
GradientBoostingRegressor <br>
cross_validate <br>
MinMaxScaler <br>
FunctionTransformer <br>


**Description of files contained in the repo:** <br>
`zaptec.ipynb` - the main Jupyter notebook that contains all the gathering, cleaning, analysis, visualization and model building <br>
`anon_response.ipynb` - the Jupyter Notebook that anonymizes the raw data retrieved from Zaptec by removing 
personally identifiable data <br>
`response_anon.json` - the anonymized data from the Zaptec API call to chargehistory  <br>
`ugz_ogd_meteo_h1_2021.csv` and `ugz_ogd_meteo_h1_2022.csv` - open source meteorological data <br>


**Description of data sources** <br>

**Zaptec** is a Norwegian manufacturer of charging stations for Electric Vehicles (EV), for consumer and industrial use <br>

Find the Swagger-based documentation of Zaptec API here:  https://api.zaptec.com/help/index.html <br>

Calling the Zaptec API requires a user token with permissions on a given Zaptec installation. <br>

The request URL for the response data from Zaptec (replace with real installation ID): <br>
DetailLevel = 1 option requests the detailed energy consumption data to be returned <br>
https://api.zaptec.com/api/chargehistory?InstallationId={installationID}&DetailLevel=1 <br>

The integration to the Zaptec API is explained in this document: <br>
https://zaptec.com/downloads/ZapChargerPro_Integration.pdf <br>


The **meteorological data** used is sourced from the opendata.swiss website. <br>
The hourly dataset for the city of Zurich, Switzerland, can be downloaded from:  <br>
https://opendata.swiss/de/dataset/stundlich-aktualisierte-meteodaten-seit-1992 <br>


**Acknowledgments** <br>
For this project, much insight was gained using the Pandas default documentation, stackoverflow and geekforgeeks.
For the ML model, the trigonometric time function pre-processing and other code snippets are adapted from:
https://scikit-learn.org/stable/auto_examples/applications/plot_cyclical_feature_engineering.html

