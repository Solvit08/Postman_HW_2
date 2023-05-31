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
#### 1. Send a request
#### 2. Status code is 200
    pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
    });
#### 3. Parse response body in json
    var resp = pm.response.json();
#### 4. Check that response's name is equal requeste's name
    pm.test('Name check', function() {
    pm.expect(resp.name).to.eql('Vitalik')
    })
#### 5. Check that response's age is equal requeste's age
    pm.test('age check', function() {
    pm.expect(+resp.age).to.eql(27)
    })
#### 6. Check that response's salary is equal requeste's salary
    pm.test('salary check', function() {
    pm.expect(resp.salary).to.eql(5000)
    })
#### 7. Parse request
    var req_name = request.data.name ;
    var req_age = request.data.age;
    var req_salary = request.data.salary
#### 8. Check that response's name is equal requeste's name (name to take from request) 
    pm.test('name request', function() {
    pm.expect(resp.name).to.eql(req_name)
    })
#### 9. Check that response's age is equal requeste's age (age to take from request) 
    pm.test('age request', function() {
    pm.expect(resp.age).to.eql(req_age)
    })
#### 10. Check that response's salary is equal requeste's salary (salary to take from request)  
    pm.test('Salary request', function() {
    pm.expect(resp.salary).to.eql(+req_salary)
    })
#### 11. Output to the console, the family parameter from response.
    console.log(resp.family)
#### 12. Check that u_salary_1_5_year in the response is equal to salary * 4 (take salary from request)
    pm.test('salary', function() {
    pm.expect(resp.family.u_salary_1_5_year).to.eql(req_salary * 4)
    })
# EP_3    
