# Neighborhood Property Listing's

> Node.js app that provides simple API endpoints to querry for property information



## Requirements

An `nvmrc` file is included if using [nvm](https://github.com/creationix/nvm).

- Node 6.13.0
- etc

## Development

### Installing Dependencies

From within the root directory:

```sh
npm install -g webpack
npm install
```
# Getting started with App:

1) npm run seedDB
2) npm run react-dev
3) npm run start

# CRUD  API Routes 
### Listing Routes:


* **URL**: /listings/:listingID
  * **Notes:** Get property listing data from database 
  * **METHOD:** _`GET`_
  * **Example:** `app.get('/listings/25')`
    Gets all data from the database for listing with the ID of 25
  * **URL Params:** `listingsID = [integer]`
  * **Returns:**
  ```javascript
  listing = {
      listings_id INTEGER NOT NULL,
      neighborhoods_id VARCHAR(10) NOT NULL,
      address VARCHAR(50) NOT NULL,
      price INTEGER NOT NULL,
      images TEXT[] NOT NULL,
      state VARCHAR(20) NOT NULL,
      city VARCHAR(50),
      median_zestimate INTEGER NOT NULL,
      baths INTEGER NOT NULL,
      rooms INTEGER NOT NULL,
      listing_status VARCHAR(20) NOT NULL,
      sq_ft INTEGER NOT NULL,
      transitscore DECIMAL NOT NULL,
      walkingscore DECIMAL NOT NULL,
      neighborhood_home_value DECIMAL(4, 2) NOT NULL,
      one_year_prediction decimal(4, 2) NOT NULL
  }
  ```


* **URL**: /neighborhoods/:neighborhoodsID
  * **Notes:** Get all nearby listings within same zipcode that have similar home listing properties(i.e. # of baths, sq-Ft#) based on listingID 
  * **METHOD:** _`GET`_
  * **Example:** `app.get('/neighborhoods/25/')`
    Gets all listings from database that have the neighboorhoodsID of 25
  * **URL Params:** `neighborhoodsID = [integer]`
  * **Returns:**
  ```javascript
  listings = [ {
      listings_id INTEGER NOT NULL,
      neighborhoods_id VARCHAR(10) NOT NULL,
      address VARCHAR(50) NOT NULL,
      price INTEGER NOT NULL,
      images TEXT[] NOT NULL,
      state VARCHAR(20) NOT NULL,
      city VARCHAR(50),
      median_zestimate INTEGER NOT NULL,
      baths INTEGER NOT NULL,
      rooms INTEGER NOT NULL,
      listing_status VARCHAR(20) NOT NULL,
      sq_ft INTEGER NOT NULL,
      transitscore DECIMAL NOT NULL,
      walkingscore DECIMAL NOT NULL,
      neighborhood_home_value DECIMAL(4, 2) NOT NULL,
      one_year_prediction decimal(4, 2) NOT NULL
  }
  ]
  ```




* **URL**: /listings/agents/:agentID
  * **Notes:** POST a listing by a specific agent
  * **METHOD:** _`POST`_
  * **EXAMPLE:** `app.post('/listings/agents/2')`
      Posts a listing to the database by an agent user with ID 2
  * **URL Params:** `agentID = [integer]`
  * **Request Body:**
      ```javascript
      listing = {
        listings_id INTEGER NOT NULL,
        neighborhoods_id VARCHAR(10) NOT NULL,
        address VARCHAR(50) NOT NULL,
        price INTEGER NOT NULL,
        images TEXT[] NOT NULL,
        state VARCHAR(20) NOT NULL,
        city VARCHAR(50),
        median_zestimate INTEGER NOT NULL,
        baths INTEGER NOT NULL,
        rooms INTEGER NOT NULL,
        listing_status VARCHAR(20) NOT NULL,
        sq_ft INTEGER NOT NULL
        }
        ```

* **URL:** /listings/:listingID/
  * **Notes:** UPDATE a listing by a specific agent
  * **METHOD:** _`PUT`_
  * **Example:** `app.put('/listings/25')`
      update a listing on the database with ID 25
  * **URL Params:** `listingID = [integer]`
  * **Request Body:**
      ``` javascript
      listing = {
        listings_id INTEGER NOT NULL,
        neighborhoods_id VARCHAR(10) NOT NULL,
        address VARCHAR(50) NOT NULL,
        price INTEGER NOT NULL,
        images TEXT[] NOT NULL,
        state VARCHAR(20) NOT NULL,
        city VARCHAR(50),
        median_zestimate INTEGER NOT NULL,
        baths INTEGER NOT NULL,
        rooms INTEGER NOT NULL,
        listing_status VARCHAR(20) NOT NULL,
        sq_ft INTEGER NOT NULL
      }
      ```


* **URL**: /listings/:listingID
  * **Notes:** delete a listing with certain listingID
  * **METHOD:** _`DELETE`_
  * **Example:** `app.delete('/listings/25')`
  delete a listing on the database with ID 25 
  * **URL Params:** `listingID = [integer]`
  * **Request Body:**
      None





