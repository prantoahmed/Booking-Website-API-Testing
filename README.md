
# Booking Website API

This document explains how to run a API test with Postman.

# Documentation
https://documenter.getpostman.com/view/26883317/2sB34kEJtm

# Summery
I have complated a API test Booking webste.

https://restful-booker.herokuapp.com

<img width="1920" height="1477" alt="Image" src="https://github.com/user-attachments/assets/6555382c-efc3-46bc-a305-3a03976e29db" />

Here in this API new books were orderd list of books were viewed and different tests were performed like GET, POST, PUT,DELETE.

Summery: Test Scripts 4 and Total 7 assertions were done.All of them passed 0 skipped tests.The number of iterration was 1.

# Requirements

Java

https://www.oracle.com/java/technologies/downloads/

Postman

https://www.postman.com/

Node JS

https://nodejs.org/en/


# Summery
I have complated a API test Booking webste.

Here in this API new books were orderd list of books were viewed and different tests were performed like GET, POST, PUT,DELETE.

Summery: Test Scripts 4 and Total 7 assertions were done.All of them passed 0 skipped tests.The number of iterration was 1.
# Automation Test Case
![Automation Test Case](https://github.com/prantoahmed/Rest_API_Automation_1/assets/30936060/a50d1656-7590-4cca-abb3-786ecd8673f8)

# Total Request
<img width="1920" height="16812" alt="Image" src="https://github.com/user-attachments/assets/a3c53695-f19a-4f15-b9d5-ac7dfc24156d" />

# Requirements

Java

https://www.oracle.com/java/technologies/downloads/

Postman

https://www.postman.com/

Node JS

https://nodejs.org/en/

# Assertions Details

## Create User:

    * Pre-request-

    var firstname = pm.variables.replaceIn("{{$randomFirstName}}")
    console.log(firstname)
    pm.environment.set("firstname",firstname)

    var lastname = pm.variables.replaceIn("{{$randomLastName}}")
    console.log(lastname)
    pm.environment.set("lastname",lastname)

    const moment = require("moment")
    const today = moment()

    pm.environment.set("checkin",today.format("YYYY-MM-DD"))

    * Post Response-

    var jsonData = pm.response.json()
    pm.environment.set("ID",jsonData.bookingid)

    pm.test("Successfully request run - 200", function () {
    pm.response.to.have.status(200);
    });

## Token Genarate:

    pm.environment.set("token",tokenData.token)
    pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
    });

## Update:
{
	"firstname": "{{firstname}}",
	"lastname": "{{lastname}}",
	"totalprice": 111,
	"depositpaid": true,
	"bookingdates": {
    	"checkin": "2013-02-23",
    	"checkout": "2014-10-23"
	},
	"additionalneeds": "Breakfast"
}

## Delete User:
    pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
    });

# Create Test Suites

## Using Newman

Newman is a command-line Collection Runner for Postman. It enables you to run and test a Postman Collection directly from the command line.

## Install command
    npm install -g newman

## Run command
    * newman run “Path/CollectionName.json” -e Path/EnvironmentName.json
    * newman run “Collection Link” -e “Path”/EnvironmentName.json

## Create HTML Report

    npm install -g newman-reporter-htmlextra

## Run command
    * newman run “Collection Link” -e “Path”/EnvironmentName.json -r cli,htmlextra
