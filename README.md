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

<h2> Creating Cognos dashboard visualizations </h2> 

<b> Steps: </b>
