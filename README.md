# PROJECT-2--APi-testing-with-Postman

The goal of a given project is to test the [Restful-Booker](https://restful-booker.herokuapp.com/) API in accordance with the documentation.   

The tests were carried with out using Postman tool. 

The tests cover all endpoints included in the [API documentation](https://restful-booker.herokuapp.com/apidoc/index.html) with methods like **GET, POST, PUT, PATCH, DELETE**.

For more detailed testing, additional scripts have been introduced. Also variables were used to optimize the tests.

Example of the scripts : 

- **CreateBooking** with method **POST** 

```
let responseBody

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
     responseBody = pm.response.json();
});

pm.collectionVariables.set("createdBookingID", responseBody.bookingid);


pm.test("Response time is less than 500ms", function () {
    pm.expect(pm.response.responseTime).to.be.below(500);
});

pm.test("Response body has a JSON format", function () {
    pm.response.to.be.json;
});

pm.test("Response contains required properties", function () {
    var responseBody = pm.response.json();
    pm.expect(responseBody).to.have.property('bookingid');
    pm.expect(responseBody.booking).to.have.property('firstname');
    pm.expect(responseBody.booking).to.have.property('lastname');
    pm.expect(responseBody.booking).to.have.property('totalprice');
    pm.expect(responseBody.booking).to.have.property('depositpaid');
    pm.expect(responseBody.booking).to.have.property('bookingdates');
});
```
--------------------------------------------------------------------------
- Summary raport preview
  
![raport1](https://github.com/user-attachments/assets/1d6f2f23-20d6-44d4-8bbc-c30cc9190684)
![raport2](https://github.com/user-attachments/assets/cb6d520c-e3d7-4ade-a57e-907610ee0a88)


--------------------------------------------------------------------------
**How to run test in Postman**: 

 Clone repository :
 ``` git clone https://github.com/sehsune/PROJECT-2--APi-testing-with-Postman.git```

1. Dowload and instal Postman from https://www.postman.com/downloads/
2. Open Postman
3. Use  *Import* in *My Workspace* tab an select postman collection - **Booking API.postman_collection.json**
4. Run the **Booking API.postman_collection.json** collection 


















