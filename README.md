# Ms Loan Granting Contest Notes

Data Transformation and Feature Engineering for Microsoft's Loan Granting Contest using Azure Machine Learning Studio Python Module.

#Data Transformation

    
    import pandas as pd
    import numpy as np

    dataframe1['Monthly Debt']=dataframe1['Monthly Debt'].str.replace('$','')
    dataframe1['Monthly Debt']=dataframe1['Monthly Debt'].str.replace(',','')
    dataframe1['Monthly Debt']=dataframe1['Monthly Debt'].str.strip()

    dataframe1['Maximum Open Credit']=dataframe1['Maximum Open Credit'].replace('#VALUE!',np.nan)


    return dataframe1,
    
#Feature Engineering


    
    import pandas as pdz
    import numpy as np
    
    dataframe1.ix[dataframe1['Current Loan Amount']==99999999,'Current Loan Amount']=np.nan

    dataframe1['Monthly Debt']=dataframe1['Monthly Debt'].astype(float)

    r2 = {'Short Term':'0', 'Long Term':'1'}
    dataframe1['Term']=dataframe1['Term'].map(r2)

    r3 ={'< 1 year':'0', '10+ years':'10', '9 years':'9', '3 years':'3', '2 years':'2', '7 years':'7','6 years':'6', '1 year':'1', '5 years':'5', '4 years':'4', '8 years':'8', 'n/a':np.nan}
    dataframe1['Years in current job']=dataframe1['Years in current job'].map(r3)
    dataframe1['Years in current job']=dataframe1['Years in current job'].astype(float)

    r4={'Rent':'1', 'Home Mortgage':'2', 'Own Home':'3', 'HaveMortgage':'2'}
    dataframe1['Home Ownership']=dataframe1['Home Ownership'].map(r4)

    r5={'Debt Consolidation':'1', 'Home Improvements':'2', 'other':'3', 'Business Loan':'4','small_business':'5', 'Other':'3', 'moving':'6', 'Buy a Car':'7', 'Medical Bills':'8','Buy House':'9', 'Take a Trip':'10', 'vacation':'11', 'major_purchase':'12','Educational Expenses':'13', 'wedding':'14', 'renewable_energy':'15'}
    dataframe1['Purpose']=dataframe1['Purpose'].map(r5)
    dataframe1['Purpose']=dataframe1['Purpose'].astype(float)


    dataframe1['Months since last delinquent']=dataframe1['Months since last delinquent'].str.replace('NA', '')
    dataframe1.ix[dataframe1['Months since last delinquent']=='','Months since last delinquent']=np.nan
    dataframe1['Months since last delinquent']=dataframe1['Months since last delinquent'].astype(float)

    dataframe1['Maximum Open Credit']=dataframe1['Maximum Open Credit'].str.replace('NA', '')
    dataframe1.ix[dataframe1['Maximum Open Credit']=='','Maximum Open Credit']=np.nan
    dataframe1['Maximum Open Credit']=dataframe1['Maximum Open Credit'].astype(float)

    dataframe1['Bankruptcies']=dataframe1['Bankruptcies'].str.replace('NA', '')
    dataframe1.ix[dataframe1['Bankruptcies']=='','Bankruptcies']=np.nan
    dataframe1['Bankruptcies']=dataframe1['Bankruptcies'].astype(float)

    dataframe1['Tax Liens']=dataframe1['Tax Liens'].str.replace('NA', '')
    dataframe1.ix[dataframe1['Tax Liens']=='','Tax Liens']=np.nan
    dataframe1['Tax Liens']=dataframe1['Tax Liens'].astype(float)

    return dataframe1,

