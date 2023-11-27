# Build a real-time dashboard in Oracle Analytics Cloud with MySQL HeatWave

![mysql heatwave](./images/mysql-heatwave-logo.jpeg " mysql heatwave")

## Introduction

MySQL HeatWave can easily be used for development tasks with existing Oracle services, such as Oracle Cloud Analytics. -> Oracle Analytics Cloud (OAC) provides the industry’s most comprehensive cloud analytics in a single unified platform, including self-service visualization and inline data preparation to enterprise reporting, advanced analytics, and self-learning analytics that deliver proactive insights.

Use MySQL HeatWave with OAC to explore and perform collaborative analytics with your MySQL data.

_Estimated Time:_ 10 minutes


### Objectives

In this lab, you will be guided through the following tasks:

- Create a predictions dataset on OAC using the mysql\_customer\_orders and black_predictions tables
- Create visualizations on OAC using the predictions dataset

### Prerequisites

- An Oracle Trial or Paid Cloud Account
- Some Experience with MySQL Shell
- Completed Lab 9

## Task 1: Create Connection from HeatWave DB to OAC

1. Navigate to Menu > Analytics > Analytics Clouds

2. Select the OAC instance you provisioned to access the OAC console by clicking on Analytics Home Page. Click on the **Analytics Home Page** button.
    ![analytics go home page](./images/analytics-go-home-page.png " analytics go home page")

3. Create a Connection to HeatWave to build a dashboard
    ![analytics home page](./images/analytics-home-page.png " analytics home page")

4. Click the **Create Connection** button
    ![analytics dataset connections](./images/analytics-dataset-connections.png " analytics dataset connections")

5. Search for HeatWave and select HeatWave as the database.
    ![add connection mysql](./images/add-connection-mysql.png " add connection mysql")

6. Specify the connections details
    - Specify the hostname of heatwave-db
    - Use the FQDN information you save in Step 3
    - Port: 3306
    - Database Name: mysql\_customer\_orders
    - Be sure to use the Heatwave DB username and password

    Hit the **Save** button to finish creating the connection.
    ![config add connection mysql](./images/config-add-connection-mysql.png " config add connection mysql")

7. The completed connection will display a "New Dataset" page.

## Task 2: Create a dataset using mysql customer orders and black_predictions tables

1. Click on the arrow beside **heatwaveml_bench** and **mysql\_customer\_orders**. Drag and drop the **products** and **black\_predictions** table from the sidebar into the **New Dataset** page.
    ![drag drop products](./images/drag-drop-products.png " drag drop products")

2. Right click on **products**, click **Join To** and select **black\_predictions**.
    ![join tables](./images/join-tables.png " join tables")

3. Leave the join type as **Inner**, select **Product\_Category\_1** under black\_predictions and **PRODUCT\_ID** under products.
    ![inner join](./images/inner-join.png " inner join")

4. Save the dataset as **predictions**.

## Task 3: Create visualizations using the predictions dataset

1. In the top right corner of the OAC window, click **Create Workbook**
    ![create workbook](./images/create-workbook.png " create workbook")

2. Click the dropdown arrow for **black\_predictions** and **products**. From the **products** list, drag and drop **PRODUCT\_NAME** into the blank canvas. From the **black\_predictions** list, drag and drop **Age** and **Purchase**.
    ![drag drop purchase product name](./images/drag-drop-purchase-product-name.png " drag drop purchase product name")

3. OAC chooses the best-fit visualization for the data provided, which is a bar chart. We will leave this as-is and create a second visualization to compare the purchases by age with the predictions by age.

4. From the **products** list, drag and drop **PRODUCT\_NAME** on the right of the visualization we created in the previous steps. From the **black\_predictions** list, drag and drop **Age** and **Prediction**.
    ![drag drop prediction product name](./images/drag-drop-prediction-product-name.png " drag drop prediction product name")

5. This creates a side-by-side comparison of Purchase by age and product name vs. Predictions by age and product name as shown below.
        ![final-visualization](./images/final-visualization.png " final visualization")

**Congratulations! You have successfully finished this Lab. Please proceed to the next lab.**


## Acknowledgements

- **Author** - Runit Malik, MySQL Cloud Solution Engineer
- **Contributors** - Perside Foster, MySQL Principal Solution Engineer
- **Last Updated By/Date** - Runit Malik, MySQL Cloud Solution Engineer, November 2023