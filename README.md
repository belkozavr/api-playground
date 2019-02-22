# api-playground
Demo test cases on BestBuy API (educational playground)

Postman, Newman

## Prerequisites:

Follow the guide to setup postman environment:
 https://learning.getpostman.com/docs/postman/launching_postman/installation_and_updates

```
git clone https://github.com/belkozavr/api-playground.git
cd api-playground
npm install
npm start
cd public/man/OBE_postman_collections
newman run Best-Buy-API-Playground.postman_collection.json -e BestBuyAPI.postman_environment.json -d BestBuyData.csv
```
## Short explanation of selected solution

To automate tests we imported swagger json into Postman. For the new collection we created an environment and basic data set. 
We didn't repeat tests available in the examples. 
Basic test suite structure is provided in Test Cases section below. Almost the same test cases are performed for every endpoint in the collection. Every endpoint has a dedicated folder in the collection. 

// TODO: Improve data set to include specific payload. Improve collection to have less repetitions using endpoint as variable. 


## Test cases:

> endpoints:
> * /products
> * /stores
> * /services
> * /categories
> * /version
> * /healthcheck

* Return all items - no filters

    * Status code is 200
    * Item Scheme is valid
    * Item data is available
    * Default page limit is correct
    * Default skip is correct

* Return all Item - limit output and skip

    * Status code is 200
    * Returned values of skip and limit are correct
    * Item data should be empty when limit is set to zero

* Create a new Item

    * Status code is 201
    * Item data schema is valid
    * Responce contains Item id

* Select Item by id

    * Status code is 200
    * Item data schema is valid

* Update an Item based on ID

    * Status code is 200
    * Item data is updated

* Delete a single Item based on the ID supplied

    * Status code is 200
    * Deleted Item cannot be found

### Specific tests for "/version" and "/healthcheck" endpoints
* Returns the current version of the API Playground being run

    * Status code is 200

* Returns healthcheck information about the system
    * Status code is 200




