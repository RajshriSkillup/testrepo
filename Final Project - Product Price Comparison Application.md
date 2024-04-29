# Final Project - Product Price Comparison Application

## **Estimated Time Needed:** 1.5 hours

- In this final project, you will create microservices and use them in a frontend application.

## Objectives:

After completing this lab, you will be able to:

1. Deploy microservices on Code Engine and create APIs.
2. Use multiple microservices in an integrated frontend application.

**::page{title="Set-up : Deploy Applications"}**

1. Open the Code Engine CLI.

2. Deploy the Microservice for Product Details, which provides API endpoints to retrieve product information.

**build-source** - `https://github.com/ibm-developer-skills-network/dealer_evaluation_backend.git`

**build-context-dir** - `products_list`

**port** - `5000`

```
ibmcloud ce application create --name prodlist --image us.icr.io/${SN_ICR_NAMESPACE}/prodlist --registry-secret icr-secret --port 5000 --build-context-dir products_list --build-source https://github.com/ibm-developer-skills-network/dealer_evaluation_backend.git
```
> Copy the deployment URL and save it in a notepad or other text editor.

> Take a screenshot of the successful deployment and save it as `product_details_deploy.png`.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-CD0250EN-SkillsNetwork/labs/FinalProject_v2/images/prod_list_deploy.png)


3. Deploy the Microservice for Dealer Pricing Details, which provides API endpoints to retrieve dealer pricing information.

> Note: Please use the below parameters for the deploy command

**build-source** - `https://github.com/ibm-developer-skills-network/dealer_evaluation_backend.git`

**build-context-dir** - `dealer_details`

**port** - `8080`

**name** - `dealerdetails`

**image** -  `us.icr.io/${SN_ICR_NAMESPACE}/dealerdetails`

> Copy the deployment URL and save it in a notepad or other text editor.

> Take a screenshot of the successful deployment and save it as `dealer_details_deploy.png`.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-CD0250EN-SkillsNetwork/labs/FinalProject_v2/images/dealer_details_deploy.png)

**::page{title="Modify and Deploy Frontend application"}**

1. In the terminal, go to `/home/projects` directory.

```
cd /home/projects
```

2. Clone the repository https://github.com/ibm-developer-skills-network/dealer_evaluation_frontend.git in your /home/project directory.

> Take a screenshot of the successful git cloning and save it as `git_clone.png`.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-CD0250EN-SkillsNetwork/labs/FinalProject_v2/images/gitclone.png)

3. Change to the `dealer_evaluation_frontend` directory.
  
4. Update the index.html file with the deployment URLs obtained from the microservice deployments. (`http://localhost:5000/` and `http://localhost:8080/`), copy the deployment URLs you copied in the appropriate location. Make sure you end the URLs with a `/`.

> Take a screenshot of the changes and save it as `index_urlchanges.png`.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-CD0250EN-SkillsNetwork/labs/FinalProject_v2/images/indexhtml_changes.png)

5. Deploy the Frontend Microservice by pointing the build-source to the current directory.

**build-source** - `.`

**port** - `5001`

**name** - `frontend`

**image** - `us.icr.io/${SN_ICR_NAMESPACE}/frontend`

> Take a screenshot of the successful deployment and name it `frontend_deploy.png`.


![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-CD0250EN-SkillsNetwork/labs/FinalProject_v2/images/frontend_deploy.png)

6. Click the link to load the homepage. Please note the page takes time to load the first time you access it.

7. Click the link to load the homepage. Please note the page takes time to load the first time you access it.

> Take a screenshot of the homepage showing the products list and name it `homepage.png`.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-CD0250EN-SkillsNetwork/labs/FinalProject_v2/images/homepage_prodlist.png)

8. Select a product from the dropdown to view the dealers supplying the product.

> Take a screenshot showing the selected product and the dealers listed, and name it `product_dealer.png`.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-CD0250EN-SkillsNetwork/labs/FinalProject_v2/images/dealersofproducts.png)

9. Choose a specific dealer for the product and verify the price is displayed.

> Allow 10 to 20 seconds for the page to load.

> Take a screenshot showing the selected product, dealer, and price displayed, and name it `product_dealer_price.png`.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-CD0250EN-SkillsNetwork/labs/FinalProject_v2/images/dealer_product_price.png)

10. Select the `All Dealers` option for a product (ensure the product has multiple dealers) to view pricing from all dealers.

> Take a screenshot showing the selected product, the `All Dealers` option chosen, and prices from all dealers displayed, and name it `product_all_dealers_prices.png`.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-CD0250EN-SkillsNetwork/labs/FinalProject_v2/images/alldealers_pricing.png)

## Congratulations! You have completed the Final project!

## Summary:

In this lab, you created multiple backend microservices on Code Engine and deployed a frontend application that integrates these microservices for product price comparison.
