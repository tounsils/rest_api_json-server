# REST API Back-End for Angular 10/9 App with JSON-Server and Faker.js
REST API back-end for Angular 10/9 application which can be consumed using Angular 10 Http Client even before the real back-end is ready.

Topics : angular rest-api json-server backend-api


## To modify data structure
    see server/generateData.js

## Generate fake data with faker :
go to your terminal and let’s create some data for our REST API:

    $ npm run generate
    // Already added in package.json :
    // "generate": "node ./server/generateData.js > ./server/database.json"


## Finally, run the REST API server using:

    $ npm run server
    // Already added in package.json :
    // "server": "json-server --watch ./server/database.json"

Your REST API server will be available from the [http://localhost:3000/](http://localhost:3000/) address.

## API endpoints
These are the available API endpoints that we ca consume using Angular HttpClient:

    GET /products for getting the products,
    GET /products/<id> for getting a single product by id,
    POST /products for creating a new product,
    PUT /products/<id> for updating a product by id,
    PATCH /products/<id> for partially updating a product by id,
    DELETE /products/<id> for deleting a product by id.

You can make use of the _page and _limit parameters to retrieve pages of data. In the Link header of the HTTP response you'll have the first, prev, next and last links.

# Conclusion

Thanks to json-server you can boost your productivity when developing your Angular 10 front-end without waiting for the back-end features to be ready. Since json-server is based on Express.js, it's even possible to add advanced features to your mocked back-end such as authentication and route protection. Check out this tutorial for an example with authentication or also this npm package.


# More on how to install json-server from npm 

## Install json-server 
Go to your angular project and install json-server from npm:

    $ cd ~/angular-project
    $ npm install --save json-server

## Create server/database.json
Next, create a server/database.json file inside the server folder with the following object:

    {    
        "products": []
    }

## Install Faker.js
We need to add data to this file that will be returned from our REST API endpoints. We can use Faker.js for automatically generating big amounts of data that looks realistic.

Head over to your terminal, go to the root of your Angular project, and install Faker.js from npm:

    $ cd ..
    $ npm install faker --save

## reate server/generateData.js file
Now, create a server/generateData.js file and add the following code:

    var faker = require('faker');

    var database = { products: []};

    for (var i = 1; i<= 300; i++) {
    database.products.push({
        id: i,
        name: faker.commerce.productName(),
        description: faker.lorem.sentences(),
        price: faker.commerce.price(),
        imageUrl: "https://source.unsplash.com/1600x900/?product",
        // 'random' changed to 'datatype' to fix deprecations in faker #149
        // quantity: faker.random.number()
        quantity: faker.datatype.number()
    });
    }

    console.log(JSON.stringify(database));

## adding the generateData and runServer scripts to the package.json
Next, add the generateData and runServer scripts to the package.json file:

    {
    "name": "rest_api_backend_angular",
    "version": "1.0.0",
    "scripts": {
        "ng": "ng",
        "start": "ng serve",
        "build": "ng build",
        "test": "ng test",
        "lint": "ng lint",
        "e2e": "ng e2e",
        "generate": "node ./server/generateData.js > ./server/database.json",
        "server": "json-server --watch ./server/database.json"
    },
    "dependencies": {
        "faker": "^5.5.3",
        "json-server": "^0.17.0"
    }
    }

## Some data generation
Next, go to your terminal and let’s create some data for our REST API:

    $ npm run generateData

## Run the REST API server
Finally, run the REST API server using:

    $ npm run runServer

Your REST API server will be available from the [http://localhost:3000/](http://localhost:3000/) address.

\{^_^}/  Time for a delicious :coffee: :)