# Create a azure service bus triggered function for HERE API "places" 

Create a service bus triggered "places" function  - <a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fnavinmistry%2Fhere_azure%2Farm_templates%2Fservicebus_cosmosdb_fn_places%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>
<a href="http://armviz.io/#/?load=https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fnavinmistry%2Fhere_azure%2Farm_templates%servicebus_cosmosdb_fn_places%2Fazuredeploy.json" target="_blank">
    <img src="http://armviz.io/visualizebutton.png"/>
</a>


This template does the following thing 
	1. creates a servicebus namespace
	2. creates a cosmos DB (SQL) instance
	1. creates a standard storage account
	2. creates a function app
	3. deploys a servicebus trigger function for HERE places API

This template is for unidirectional journey where request will be received on servicebus queue.
incoming message to service bus triggers places function which internally will call actual here "places" api.
result for this function call will be stored in Cosmos DB instance which is created as part of this template.

Storage into CosmosDB will be in a database ID called "HERE_API_LOGS" and container ID called "places"

