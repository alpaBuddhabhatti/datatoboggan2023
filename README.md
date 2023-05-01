# TrainingDemo

If you have an xml/json file and you would like to proccess file then you can do that very easily using Azure Data Factory or Azure Synapse Analytics Pipeline. Based on complexity of file you can use copy activity only or you need to use mapping data flow.

Following steps need to perform.

1. Following Azure Resources you need for this demo:

         1. Azure Key Valut
         2. Azure Storage Account 
         3. Azure SQL Database
         4. Azure Data Factory.
2. once you above four resources created, you need to store secret to Key Valut.There are 2 secret you will have in your KV.

3. You must give access policy in your Key Valut for your Azure Data Factory so your Azure Data Factory can access your Key Valut's secrets.

4. Set up Git Repo for you ADF and get all files from this Repo.

5. Create container to your storage account 'xmldemo'

6. Upload .xml files which you can doubload from this repo (File1.xml, File2.xml and File3.xml) to above container

7. Create another container called 'xmldemo-out' which store file from execution of pipeline XML001 and XML002

8. Make sure your linked services is working by jsut edit linked services and click on "test connection" button

9. run XML001 and check "xmldemo-out" container.

10. run XML002 and check "xmldemo-out" container.

11. run XML004_dataflow and check your database.

File1.xml is very simple 1-1 mapping so copy activity is workingfor that
File2.xml is simple file so copy activity works for it. it has an array with single item.
File3.xml ia complex one. there are 2 diffrent arrays haivng multiple items
here is output we need from this file. Flattern transformation has been used to convert array item to Row.
This is dataset hold data related to Type plus few more information. Note Flattern Transformation & its properties
![image](https://user-images.githubusercontent.com/64379307/200439277-538aa273-e0e3-457d-b42f-298613ed0dfb.png)

This is dataset hold data related to Languages plus few more information. Note Flattern Transformation & its properties
![image](https://user-images.githubusercontent.com/64379307/200439436-8c7c3a77-766d-4621-ac82-5a880ed2a434.png)
