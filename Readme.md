Install JSON Server

npm install -g json-server
Create a db.json file with some data

{
    "employees": [
        {
            "id": 1,
            "first_name": "Arjun",
            "last_name": "Bisht",
            "email": "arjun@gmail.com"

        },
        { 
            "id": 2,
            "first_name": "Amit",
            "last_name": "Rawat",
            "email": "amit@gmail.com"
        },
        {
            "id": 3,
            "first_name": "Kirpal",
            "last_name": "Ramola",
            "email": "kirpal@gmail.com"
        }
    ]
}
Start JSON Server

json-server --watch db.json
Now if you go to http://localhost:3000/employees/1, you'll get

{
            "id": 1,
            "first_name": "Arjun",
            "last_name": "Bisht",
            "email": "arjun@gmail.com"
}
if you make POST, DELETE requests, changes will be automatically saved to db.json

it's possible to extend URLs with further parameters
https://localhost:3000/employees?first_name=Arjun
for request we use Postman user interface

First, let’s initialize a new NPM project in the current repository:
$ npm init

Next, install Faker.js by using the NPM package faker:
$ npm install faker
Faker.js is installed to the node_modules folder. Create another file employees.js

We’re implementing the function generateEmployees() to generate a JSON object containing 50 employees. To obtain the fake data for first name, last name and email we’re using the following methods from the Faker.js library:
faker.name.firstName()
faker.name.lastName()
faker.internet.email()

JSON server requires that we finally export the generateEmploees() function which is responsible for fake data generation. This is done by using the following line of code:

module.exports = generateEmployees

Having added that export, we're able to pass file employee.js directly to the json-server command:
$ json-server employees.js