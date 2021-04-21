# Solr In Azure Container Instance for Sitecore
How to run Solr in an azure container instance with file persistence

Prereqs:
AZ powershell tools
Azure Storage Explorer

Steps:

1 In your azure RG create a storage account and connect to it with Azure storage explorer

2 in the storage account create 2 fileshares, in my example I use solr-sitecore-configsets and solr-sitecore-data

3 copy the contents of the folder solr-sitecore-configsets and solr-sitecore-data (both in this repo) into each respective azure fileshare

4 change the params in ACI-solr-yamldeploy.yml to suit your environment, make sure to specify a unique dns name label

5 Fire up the script in powershell like this:

Set-AzContext -Subscription "insert-your-sub-id-here"

az container create --resource-group (insert your RG name here) --file ACI-solr-yamldeploy.yml



To Do:
Integrate SSL
Persist Logs

A BIG Shout Out and many big thanks to where the inspiration came from for this Proof of Concept: Dan Cruickshank <dan@getfishtank.ca> 
for all his hard work on getting solr to work within a PAAS azure app service:
https://getfishtank.ca/blog/sitecore-solr-docker-app-service-on-azure

Dans Repos are here:
https://github.com/getfishtank
