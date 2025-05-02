## Linear Regression Dataset – Azure Automated ML

# Step 1: Create a Compute Cluster 

- Auto ML in Azure is very computational heavy and a compute cluster is required, this scales depending on computational usage -> under compute select Compute clusters and new 

![Step1](Images/Azure_Auto_ML_Images/1.png) 

- Select a CPU or GPU depending how fast you need Auto ML to finish and computational needs and dataset size 

![Step2](Images/Azure_Auto_ML_Images/2.png) 

- Add a compute name and the minimum and maximum number of nodes - **Note: set minimum nodes to 0, you will not be charged for the Compute cluster until the Compute cluster is in use** 

![Step3](Images/Azure_Auto_ML_Images/3.png) 


## Step2:  Open Automated ML and select “New Automated ML JOB” 

![Step4](Images/Azure_Auto_ML_Images/4.png) 
 
- Fill in the basic info required and next select the task type ‘Regression’ and select the dataset we created earlier for the Designer tool pipeline 

![Step5](Images/Azure_Auto_ML_Images/5.png) 

-Set your Target column and as we split the data 80:20 in our Notebook and Designer we will do the same here 

![Step6](Images/Azure_Auto_ML_Images/6.png) 

![Step7](Images/Azure_Auto_ML_Images/7.png) 

- Select the Compute cluster you created and run the job  -> This will take some time to run maybe 20 minutes 

## Step 3: When the job has finished you can select the Auto ML job under recent Automated ML Jobs and open the job to see the best fit model – under models and child jobs

![Step8](Images/Azure_Auto_ML_Images/8.png) 

- Select the first model and open to see the metrics

![Step9](Images/Azure_Auto_ML_Images/9.png)

- View the metrics

![Step10](Images/Azure_Auto_ML_Images/10.png)

![Step11](Images/Azure_Auto_ML_Images/11.png)
 
  









