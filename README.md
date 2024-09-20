# Ingesting-data-from-snowflake-to-blob

![Screenshot 2024-09-20 105524](https://github.com/user-attachments/assets/d73adc3b-e759-4976-ad56-665c9ab64988)

This project outlines how to use the Copy activity in Azure Data Factory and Azure Synapse pipelines to copy data from and to Snowflake and use Data Flow to transform data in Snowflake.
snowflake is cloud cloud-based lightning-fast data warehouse. It has gained a lot of traction since its launch. Many organizations are moving towards snowflake and hence there is a need to shift load and migrate their existing data from on-premise and cloud databases to Snowflake. In this project, we will see various ways to migrate the data to Snowflake using the Microsoft Azure Data Factory.

## There are two ways to connect Azure Data Factory with Snowflake

- Create the ADF pipeline with copy activity having the sink dataset created using the snowflake connector provided by the Azure data factory.
- Connect to Azure blob storage by creating a stage in Snowflake and using Snow pipe to move the data to the Snowflake data warehouse table.

## Project Details
- Create a snowflake account and then create a database(Testdb), Schema(testschema)
 ![image](https://github.com/user-attachments/assets/1cf69aef-d169-49b7-87b8-031aefd18bd0)

- Create a tables(testtable) and wrote a sql query to fill the columns
 ![image](https://github.com/user-attachments/assets/c965d581-c900-4965-8536-dd2900db6bb3)

- This is the table created with id, firstname and lastname
 ![image](https://github.com/user-attachments/assets/b917c08c-c1a2-49e3-a571-9a5e7e136789)

- Create a Azure data factory and create a linked list and select snowflake to fetch data from it.
 ![image](https://github.com/user-attachments/assets/1c64b31a-9be1-48f1-862f-c77788c23726)

- Create a linked list of blob storage and select excel to store data also choose SAS url and token from the storage account created.
 ![image](https://github.com/user-attachments/assets/5eb92aec-c931-42b1-aff3-f2099d354520)

- From the storage account-> container select shared access tokens and copy the url and token
 ![image](https://github.com/user-attachments/assets/fe544da2-75bb-4041-ab42-34a8d748c7d2)

- Create a pipeline by selecting copy data and create a dataset for source and sink. Created a source dataset by selecting snowflake(testtable), the table which I created in snowflake.
 ![image](https://github.com/user-attachments/assets/cb0e2d88-df87-4cda-8a13-ceb6dedf0d6b)

- Create one more dataset for destination to transfer data from snowflake to bob account in csv form.
 ![image](https://github.com/user-attachments/assets/5a5e29bb-e574-47a2-ab35-e30f53c9983d)
![image](https://github.com/user-attachments/assets/52b6649a-861d-4cee-99e1-0ebf01210b15)

- Publish and trigger a pipeline and monitor it once it is succeeded then click on the pipeline
 ![image](https://github.com/user-attachments/assets/a808f477-a785-42e3-b3fe-a0b32852efc1)

- Input
 ![image](https://github.com/user-attachments/assets/0bbddb1e-e42b-45bc-bcec-ad0e81d8a1a3)

- Output details
 ![image](https://github.com/user-attachments/assets/18a86063-c2a4-49a4-acf6-888dca77ec1f)

- The data preview shows the details about source and destination
 ![image](https://github.com/user-attachments/assets/8d39d8ca-407b-436c-933f-40fbcdd44137)

- Now we can see the data my storage account->container->test folder-> csv file
 ![image](https://github.com/user-attachments/assets/52029edc-eb1e-4f3d-b8b6-a0f28dee0c1b)

