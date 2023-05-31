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
#### 4. Check that  name in response is equal  name in request
    pm.test('Name check', function() {
    pm.expect(resp.name).to.eql('Vitalik')
    })
#### 5. Check that age in response is equal age in request
    pm.test('age check', function() {
    pm.expect(+resp.age).to.eql(27)
    })
#### 6. Check that salary in response is equal salary in request
    pm.test('salary check', function() {
    pm.expect(resp.salary).to.eql(5000)
    })
#### 7. Parse request
    var req_name = request.data.name ;
    var req_age = request.data.age;
    var req_salary = request.data.salary
#### 8. Check that name in response is equal  name in request (name to take from request) 
    pm.test('name request', function() {
    pm.expect(resp.name).to.eql(req_name)
    })
#### 9. Check that age in response is equal age in request (age to take from request) 
    pm.test('age request', function() {
    pm.expect(resp.age).to.eql(req_age)
    })
#### 10. Check that salary in response is equal salary in request (salary to take from request)  
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
#### 1. Send a request
#### 2. Status code is 200
    pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
    });
#### 3. Parse response body in json
    var resp = pm.response.json();
#### 4. Parse request    
    var req = pm.request.url.query.toObject();
#### 5. Check that name in response is equal  name in request (name to take from request) 
    pm.test('name check', function() {
    pm.expect(resp.name).to.eql(req.name)
    })
#### 6. Check that age in response is equal age in request (age to take from request) 
    pm.test('age check', function() {
    pm.expect(resp.age).to.eql(req.age)
    } )
#### 7. Check that salary in response is equal salary in request (salary to take from request)  
    pm.test('salary check', function() {
    pm.expect(resp.salary).to.eql(+req.salary)
    })
#### 8. Output the family parameter from response to the console
    console.log(resp.family)
#### 9. Check that the dog parameter has name parameter
    pm.test('dog has name', function() {
    pm.expect(resp.family.pets.dog).to.have.property('name')
    })
#### 10. Check that the dog parameter has age parameter
    pm.test('dog has age', function() {
    pm.expect(resp.family.pets.dog).to.have.property('age')
    })
#### 11. Check that the name parameter has the value Luky
    pm.test('name luky', function() {
    pm.expect(resp.family.pets.dog.name).to.eql('Luky')
    })
#### 12. Check that the age parameter has a value of 4  
    pm.test('luky age', function() {
    pm.expect(resp.family.pets.dog.age).to.eql(4)
    })
# EP_4
#### 1. Send a request
#### 2. Status code is 200
    pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
    });
#### 3. Parse response body in json
    var resp = pm.response.json();
#### 4. Parse request    
    var req = pm.request.url.query.toObject();
#### 5. Check that name in response is equal  name in request (name to take from request) 
    pm.test('name check', function() {
    pm.expect(resp.name).to.eql(req.name)
    })
#### 6. Check that age in response is equal age in request (age to take from request) 
    pm.test('age check', function() {
    pm.expect(resp.age).to.eql(req.age)
    } )
#### 7. Output the salary parameter from request to the console
    console.log(req.salary)
#### 8. Output the salary parameter from response to the console.
    console.log(resp.salary)
#### 9. Output the 0th element of the salary parameter from response to the console.
    console.log(resp.salary[0])
#### 10. Output the 1st element of the salary parameter to the console, the salary parameter from response.
    console.log(resp.salary[1])
#### 11. Output the 2nd element of the salary parameter to the console, the salary parameter from response.    
    console.log(resp.salary[2])
#### 12. Check that the 0th element of the salary parameter is equal to salary from request (salary is taken from request.)
    pm.test('check salary_1', function() {
    pm.expect(resp.salary[0]).to.eql(+req.salary)
    })
#### 13. Check that the 1st element of the salary parameter is equal to salary * 2 from request (salary is taken from request.)
    pm.test('check salary_2', function() {
    pm.expect(+resp.salary[1]).to.eql(req.salary*2)
    })
#### 14. Check that the 2nd element of the salary parameter is equal to salary * 3 from request (salary to take from request.
    pm.test('check salary_3', function() {
    pm.expect(+resp.salary[2]).to.eql(req.salary*3)
    })
#### 15. Pass the name variable to the environment 
    pm.environment.set("name", resp.name);
#### 16. Pass the age variable to the environment
    pm.environment.set("age", resp.age);
#### 17. Pass the salary variable to the environment
    pm.environment.set("salary", resp.salary[0]);
#### 18 Write a loop that outputs the list items from the salary parameter to the console in order.
    for(var key in resp.salary){
    console.log(resp.salary[key])
    }
    // 2-й вариант
    for(i=0;i<resp.salary.length; i++){
    console.log(resp.salary[i])
    }
# EP_5
#### 1. Send a request
#### 2. Status code is 200
    pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
    });
#### 3. Parse response body in json
    var resp = pm.response.json();
#### 4. Parse request 
    var req = request.data
#### 5. Check that the json response has the start_qa_salary parameter   
    pm.test('json response', function() {
    pm.expect(resp).to.have.property('start_qa_salary')
    })
#### 6. Check that json response has the parameter qa_salary_after_6_months
    pm.test('json response', function() {
    pm.expect(resp).to.have.property('qa_salary_after_6_months')
    })
#### 7. Check that json response has the parameter qa_salary_after_12_months
    pm.test('json response', function() {
    pm.expect(resp).to.have.property('qa_salary_after_12_months')
    })
#### 8. Check that the json response has the qa_salary_after parameter_1.5_year
    pm.test('json response', function() {
    pm.expect(resp).to.have.property('qa_salary_after_1.5_year')
    })
#### 9. Check that the json response has the qa_salary_after parameter_3.5_years
    pm.test('json response', function() {
    pm.expect(resp).to.have.property('qa_salary_after_3.5_years')
    })
#### 10. Check that the json response has the person parameter
    pm.test('person', function() {
    pm.expect(resp).to.have.property('person')
    })
#### 11. Check that the start_qa_salary parameter is equal to salary from request (salary to take from request)
    pm.test('qa_salary', function() {
    pm.expect(resp.start_qa_salary).to.eql(+req.salary)
    })
#### 12. Check that the qa_salary_after_6_months parameter is equal to salary * 2 from request (salary to take from request)
    pm.test('qa_salary_1', function() {
    pm.expect(resp.qa_salary_after_6_months).to.eql(+req.salary*2)
    })
#### 13. Check that the qa_salary_after_12_months parameter is equal to salary * 2.7 from request (salary to take from request)
    pm.test('qa_salary_2', function() {
    pm.expect(resp.qa_salary_after_12_months).to.eql(+req.salary*2.7)
    })
#### 14.  Check that the parameter qa_salary_after_1.5_year is equal to salary * 3.3 from request (salary is taken from request)
    pm.test('qa_salary_3', function() {
    pm.expect(resp['qa_salary_after_1.5_year']).to.eql(+req.salary*3.3)
    })
#### 15. Check that the parameter qa_salary_after_3.5_years is equal to salary * 3.8 from request (salary is taken from request)
    pm.test('qa_salary_4', function() {
    pm.expect(resp['qa_salary_after_3.5_years']).to.eql(+req.salary*3.8)
    })
#### 16. Check that in the person parameter, the 1st element from u_name is equal to salary from request (salary to take from request)
    pm.test('first property', function() {
    pm.expect(resp.person.u_name[1]).to.eql(+req.salary)
    })
#### 17. Check that the parameter u_age is equal to age from request (age to take from request)
    pm.test(' property', function() {
    pm.expect(resp.person.u_age).to.eql(+req.age)
    })
#### 18. Check that the parameter u_salary_5_years is equal to salary * 4.2 from request (salary pick up from request.)
    pm.test('5 years', function() {
    pm.expect(resp.person.u_salary_5_years).to.eql(+req.salary*4.2)
    })
#### 19. Write a loop that outputs the list items from the person parameter in order to the console.
    for(var i in resp.person) {
    console.log(resp.person[i])
    }
    //2 вариант
    for(i=0;i<resp.person.length;i++) {
    console.log(resp.person[i])
    }

