

# Create ng project
https://github.com/angular/angular-cli


## Mock a REST API Back-End for Your Angular 10/9 App with JSON-Server and Faker.js

https://www.techiediaries.com/angular-mock-backend/
# Generate fake data with faker :
go to your terminal and let’s create some data for our REST API:

    $ npm run generate

# Finally, run the REST API server using:

    $ npm run server

Your REST API server will be available from the [http://localhost:3000/](http://localhost:3000/) address.

# API endpoints
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

