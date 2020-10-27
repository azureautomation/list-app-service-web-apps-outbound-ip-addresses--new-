List App Service web apps outbound IP addresses (New)
=====================================================

            
What is proposed

You'll find in this function an easy way to extract the outbound IP addresses information used by all your App Services in your subscriptions by using the Azure Resource Graph, it is blazing fast compared to the old version scanning all all subscription
 one at a time (50x faster in my case).


 


Old (slower) version: [List all App Service web apps outbound IP addresses used in a subscription (old)](https://gallery.technet.microsoft.com/scriptcenter/List-all-App-Service-web-4d563f14)


 

History

[2019-03-14] Initial version using Azure Resource Graph


 

Overview

 

 

You will end up with an output in the like of:


 


 



PowerShell
Edit|Remove
powershell
Count   IpAddress       Type        Sites
-----   ----            -----       ----
    2   13.85.17.60     Outbound  {sub1-bi-dev-as-webapp, sub2-bi-prod-as-webapp}
    1   13.85.17.60     Possible  {sub3-bi-dev-as-webapp}
    2   13.85.20.144    Outbound  {sub1-bi-prod-as-webapp, sub1-bi-dev-as-webapp}
    1   13.85.20.144    Possible  {sub3-bi-dev-as-webapp}
    2   13.85.22.206    Outbound  {sub2-bi-prod-as-webapp, sub1-bi-dev-as-webapp}
    2   13.85.23.148    Outbound  {sub1-bi-dev-as-webapp, sub2-bi-prod-as-webapp}
    2   13.85.23.243    Outbound  {sub1-bi-dev-as-webapp, sub2-bi-prod-as-webapp}
    1   23.96.184.12    Outbound  {sub1-dev-functions-mmckydd}
    1   23.96.184.209   Outbound  {sub1-dev-functions-mmckydd}
    1   23.96.186.252   Outbound  {sub1-dev-functions-mmckydd}
    1   23.96.187.50    Outbound  {sub1-dev-functions-mmckydd}
    5   23.96.244.71    Outbound  {sub1-stg-webapp-web-n7wfdda, sub1-stg-functions-n7wfdda, sub1-stg-webapp-admin-n7wfdda, sub1-dev-ops-functions-stl4tn5...}

Count   IpAddress       Type        Sites 
------------------ 
    2   13.85.17.60     Outbound  {sub1-bi-dev-as-webapp, sub2-bi-prod-as-webapp} 
    1   13.85.17.60     Possible  {sub3-bi-dev-as-webapp} 
    2   13.85.20.144    Outbound  {sub1-bi-prod-as-webapp, sub1-bi-dev-as-webapp} 
    1   13.85.20.144    Possible  {sub3-bi-dev-as-webapp} 
    2   13.85.22.206    Outbound  {sub2-bi-prod-as-webapp, sub1-bi-dev-as-webapp} 
    2   13.85.23.148    Outbound  {sub1-bi-dev-as-webapp, sub2-bi-prod-as-webapp} 
    2   13.85.23.243    Outbound  {sub1-bi-dev-as-webapp, sub2-bi-prod-as-webapp} 
    1   23.96.184.12    Outbound  {sub1-dev-functions-mmckydd} 
    1   23.96.184.209   Outbound  {sub1-dev-functions-mmckydd} 
    1   23.96.186.252   Outbound  {sub1-dev-functions-mmckydd} 
    1   23.96.187.50    Outbound  {sub1-dev-functions-mmckydd} 
    5   23.96.244.71    Outbound  {sub1-stg-webapp-web-n7wfdda, sub1-stg-functions-n7wfdda, sub1-stg-webapp-admin-n7wfdda, sub1-dev-ops-functions-stl4tn5...}




 

Requirements

Tested with Az.ResourceGraph Version 0.7.x


        
    
TechNet gallery is retiring! This script was migrated from TechNet script center to GitHub by Microsoft Azure Automation product group. All the Script Center fields like Rating, RatingCount and DownloadCount have been carried over to Github as-is for the migrated scripts only. Note : The Script Center fields will not be applicable for the new repositories created in Github & hence those fields will not show up for new Github repositories.
