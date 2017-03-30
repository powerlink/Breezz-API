<h1 align="center"><img src="https://image.ibb.co/cs6S1F/full_logo.png"></h1>

# Breezz RestAPI

This is an up to date wrapper for the Breezz.io REST API. 
we initially found working with the API to be a bit frustrating and hopefully this wrapper will make everything easy for you.

More information about the Breezz REST API can be found at

http://breezz.io/Support

Please email support@breezz.io if you find any bugs.

## index

+ <a href="#create">Create</a>
+ <a href="#update">Update</a>
+ <a href="#delete">Delete</a>
+ <a href="#query">Query</a>


## Authentication
To make a REST API call, you must include request headers including the Authorization header ==>
Find your <a href="#">TOKENID<a/>

## Create

URL: 
```
https://app.breezz.io/api/record/{ObjectID}
```
Method: 
```
POST
```
Json exemple:
```javascript
{
 "accountname" : "jhon",
 "telephone1" : "+4406339060",
 "idnumber" : "123456",
 "billingcity" : "London"
}
```
More exemple in <a href="https://github.com/breezzcrm/Breezz-API/blob/master/Create/create-readme.md#php">PHP</a> | <a href="https://github.com/breezzcrm/Breezz-API/blob/master/Create/create-readme.md#python">python</a> | <a href="https://github.com/breezzcrm/Breezz-API/blob/master/Create/create-readme.md#aspnet">ASP.NET</a> |


## Update

URL: 
```
https://app.breezz.io/api/record/{ObjectID}/{id}
```
Method: 
```
PUT
```
Json exemple:
```javascript
{
 "accountname" : "jhon",
 "telephone1" : "+4406339060",
 "idnumber" : "123456",
 "billingcity" : "London"
}
```
More exemple in <a href="https://github.com/breezzcrm/Breezz-API/blob/master/Update/update-readme.md#php">PHP</a> | <a href="https://github.com/breezzcrm/Breezz-API/blob/master/Update/update-readme.md#python">python</a> | <a href="https://github.com/breezzcrm/Breezz-API/blob/master/Update/update-readme.md#aspnet">ASP.NET</a> |


## Delete

URL: 
```
https://app.breezz.io/api/record/{ObjectID}/{id}
```
Method: 
```
DELETE
```
More exemple in <a href="https://github.com/breezzcrm/Breezz-API/blob/master/Delete/delete-readme.md#php">PHP</a> | <a href="https://github.com/breezzcrm/Breezz-API/blob/master/Delete/delete-readme.md#python">python</a> | <a href="https://github.com/breezzcrm/Breezz-API/blob/master/Delete/delete-readme.md#aspnet">ASP.NET</a> |


## Query

URL: 
```
https://app.breezz.io/api/query
```
Method: 
```
POST
```

Json exemple:
```javascript
{
"objecttype": 1,
"page_size": 50,
"page_number": 1,
"fields": "accountname,idnumber,telephone1",
"query": "(idnumber  = 12345678) AND (accountname = 'john')",
"sort_by": "accountname",
"sort_type": "desc"
} 
```
More exemple in <a href="https://github.com/breezzcrm/Breezz-API/blob/master/Query/query-readme.md#php">PHP</a> | <a href="https://github.com/breezzcrm/Breezz-API/blob/master/Query/query-readme.md#python">python</a> | <a href="https://github.com/breezzcrm/Breezz-API/blob/master/Query/query-readme.md#aspnet">ASP.NET</a> |


Field | Description | exemple
------|------------ | --------------------
objecttype | the number of object | Accounts=1,	Contact=2,Deals=4 (<a href="#">See more..</a>)
page_size | the number of result per page | Min:1 Max:500
page_number | the page of result | start at: 1
fields | which fields to show on result | for all field: *
query | the query you want search | ((idnumber  = 1234) AND (idnumber  = 5678))
sort_by | Select field to sort by | accountname/idnumber/telephone1
sort_type | Select type to sort | desc/asc

Type of query:

Operator | Description | exemple
------|------------ | --------------------
**=** | find result equal | "query": "(idnumber  **=** 1234)"
**!=** | find result not equal | "query": "(idnumber  **!=** 1234)"
**>** | Greater than | "query": "(age1  **>** age2)"
**<** | Less than | "query": "(age1  **<** age2)"
**<=** | Greater than or equal to | "query": "(age1  **<=** age2)"
**>=** | Less than or equal to | "query": "(age1  **>=** age2)"
**OR** | performs a logical-OR of its bool operands | "query": "((idnumber  = 1234) **OR** (idnumber  = 456789))"
**AND** | performs a logical-AND of its bool | "query": "((idnumber  = 1234) **AND** (accountname  = 'משה'))"
**is-null** | look for NULL values | "query": "(idnumber **is-null** 1234567)"
**is-not-null** | look for not NULL values | "query": "(idnumber **is-not-null** 1234567)"
**start-with** | find if the string start with the string |  "query": "(idnumber **start-with** 1234567)"
**end-with** | find if the string end with the string | "query": "(idnumber **end-with** 1234567)"
**not-start-with** | find if the string not start with the string | "query": "(idnumber **not-start-with** 1234567)"
**not-end-with** | find if the string not end with the string | "query": "(idnumber **not-end-with** 1234567)"

You can combining the AND and OR Conditions

**Note**

+ AND & OR conditions allow you to test multiple conditions.
+ Don't forget the order of operation parentheses!

 Go to your <a href="http://breezz.io">Breezz account</a> and let's start!
