# icp4d-mortgage 

In this repositary, you will learn how to use ICP for data using a mortgage dataset. First get access to ICP4D https://www.ibm.com/cloud/garage/cloud-private-experiences/ and then create an environment. 
<br> My reservation: https://icp4d-experiences-01.demo.ibmcloud.com:31843 </br> 



<h2> Creating a machine learning model using Jupyter notebooks </h2>   

<b> <br>The Story: </b> 

<br>The model will be invoked in real time by a web or mobile app available that customers use to apply
for a mortgage. The model enables your company to analyze a mortgage application and decide
whether to approve it in a few seconds with no manual intervention. So it accurately predicts the likelihood of any given client defaulting on their mortgage. 

<b> <br> Steps: </b>

1. <b> Create a Project: </b> 
<br> <t> a. Select project tab from right: </br>
<img src = "https://github.com/anchalbhalla/icp4d-mortgage/blob/master/imgs/Capture.PNG"> </t> 

<br><br> <t> b. Click add project, select analytics project and a name to it 
  <img src = "https://github.com/anchalbhalla/icp4d-mortgage/blob/master/imgs/Capture1.PNG"> </t> 
  
  <br><br> <t> c. We will creating a new project from scratch so select new file, add a description and create the project
  <img src = "https://github.com/anchalbhalla/icp4d-mortgage/blob/master/imgs/Capture2.PNG"> </t>
  
2. Upload the datasets : Mortgage_customer, Mortgage_default, Mortgage_property 
<br><br><t> a. Click on add datasets to add them to this project so we can use it to train our model. 
  <img src = "https://github.com/anchalbhalla/icp4d-mortgage/blob/master/imgs/Capture3.PNG"> </t> 
  <br> This will add all the 4 csv files to this project. The first dataset is a joint dataset of the customer data and the property they want to purchase. The second dataset is the property dataset which has fields like Id of the customer, sales price and its location. The third dataset is the mortgage-default dataset which tells whether the mortgage must be approved or not (Fields: ID, Mortage dafault - yes/no). The last dataset is the customer dataset which has all the information about them like if they have a loan or not, their income, number of credit cards, etc.
 <img src = "https://github.com/anchalbhalla/icp4d-mortgage/blob/master/imgs/Capture4.PNG"> </t> 
 
 
 3. Adding the notebook: MortgageDefault-BuildSave.jupyter.ipynb 
    <br><br><t> a. Click on add notebook, select the 'from file' tab, enter a name for the notebook and upload this notebook.  
     <img src = "https://github.com/anchalbhalla/icp4d-mortgage/blob/master/imgs/Capture5.PNG">   
     In this notebook, the data is first being prepared. It reads from the datasets: customers, default and property and then merges them together. Next, the data is cleansed and the numeric fields are casted to integers. 
     <br>The next step is data exploration , where the data is visualized. The mortgage default is analysed with plotting graphs for residence/income and current employer/current address. 
  <br>Now the pipeline and model will be created using sparkml libraries. The feature set for this model are : "Income", "AppliedOnlineEncoded", "ResidenceEncoded", "YearCurrentAddress", "YearsCurrentEmployer", "NumberOfCards", "CCDebt", "Loans", "LoanAmount", "SalePrice", "Location". And the output column is the MortgageDefault. The alrogithm used here is the random forest classfier to predict the mortgage default.  
  <br>Next comes model evaluation and after you run the notebooks you will see the model will give an accuracy of 0.603175. 
  <br>The last step is saving this model, and once it is saved you will see it under the models tab, as described in the next step. 
  <br>Run all the cells, to see the output: 
  <img src = "https://github.com/anchalbhalla/icp4d-mortgage/blob/master/imgs/Capture6.PNG"> </t>  
  
  
 <br>4. This step involved testing the model which has been deployed by the notebook  
 <img src = "https://github.com/anchalbhalla/icp4d-mortgage/blob/master/imgs/Capture7.PNG"> </t> 
 <br><br><t> a. Click on the model, go to real-time score tab, and you will find that the default testing data is already entered. Click on submit and you see the results from the model. 
  <img src = "https://github.com/anchalbhalla/icp4d-mortgage/blob/master/imgs/Capture8.PNG"> </t> 
  You will find that the model has predicted that the client will not get a mortgage with the confidence of 76% (1- yes, 0-no)
 
<h2> Creating Cognos dashboard visualizations </h2>  

<h3>Creating Bar charts: </h3>

<b> Steps: </b> 

1. Go to Cognos Dashboards tab on left, click 'add cognos dashboards', add a dashboard name and click create
<img src = "https://github.com/anchalbhalla/icp4d-mortgage/blob/master/imgs/Capture9.PNG"> 

2.  Choose a layout for the dashboard, we will go for freeform 
<img src = "https://github.com/anchalbhalla/icp4d-mortgage/blob/master/imgs/Capture10.PNG">

3. Adding datasource 
 <br><br><t> a. Click on datasource, and from the right hand side choose the mortgagejoin.csv to insert to dashboard 
 <img src = "https://github.com/anchalbhalla/icp4d-mortgage/blob/master/imgs/Capture11.PNG"> </t>  
 
 4. Select the dataset to open it 
  <br><br><t> a. Select the columns Income and appliedOnline together (use the Ctrl key) 
   <img src = "https://github.com/anchalbhalla/icp4d-mortgage/blob/master/imgs/Capture12.PNG"> </t>  
   
   <br> b. Drag and drop them and you get a bar chart for these 2 columns
   <img src = "https://github.com/anchalbhalla/icp4d-mortgage/blob/master/imgs/Capture13.PNG"> </t> 
   
   
 
   
   <br><h3>Creating Packed Bubble charts: </h3>

<b> Steps: </b> 

1. Follow the same steps as above till step3

2. Select the columns Sales price and income and drop them onto the dashboard 
  <br><br><t> a. Choose the visualization as packed bubble and change the fields like the image below:
 <img src = "https://github.com/anchalbhalla/icp4d-mortgage/blob/master/imgs/Capture14.PNG"> </t>  

  
 
