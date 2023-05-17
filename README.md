# Postman_HW_2
# EP_1
#### 1. Send a request
#### 2. Status code is 200
    pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
    });
#### 3. Check that the correct string is coming to the body
    pm.test("Body is correct", function () {
    pm.response.to.have.body("This is the first responce from server!ss");
    });

# EP_2
