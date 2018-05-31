# d3-create-json
Create json in your d3 program. 

 * To install 
 	* You can either 
 		* clone this repository to your system
 			* click the "Clone or Download" button & copy the url
 			* on your system change to the directory where you want the directory --> cd projects --> git clone past_url_here
 				* will create d3-create-json directory...in your current directory --> cd d3-create-json	
 		* or just copy/paste the code from the browser for each file to your d3 system.  I'm using d3/linux.  
	* Then flash compile-catalog each subroutine/d3 program.
	* **DEPENDENCY**
		* I called a few string subroutines in the code.  --> [richardottinger/d3-string-subroutines](https://github.com/richardottinger/d3-string-subroutines) 
		
| File Name                 | Subroutine      | Parameters | Description |
| ------------------------- |-----------------| :----------: | ------------|
| **test\_d3\_creating\_json** | JSON.EXAMPLE    | None    | Main d3 program that makes calls to the subroutines to generate json.|
| **json\_add\_pair\_sub** | JSON.ADD.PAIR | KV\_ARRAY, KEY, VALUE, VALUE.FLAG | * Add a key/value pair to the KV\_ARRAY dynamic array. VALUE.FLAG is used to determine if value should be quoted or not. 1=QUOTED, 0=NOT.QUOTED, or ! indicates that the value is boolean, or you can pass "" if you want the value to be tested to determine if quotes need to be added|
| **json\_array\_add\_object\_sub** | JSON.ARRAY.ADD.OBJECT | CURRENT, TOTAL, JSON\_OBJECT, JSON\_ARRAY | Determines whether to PREPEND \[, or APPEND a \], or APPEND a comma to the JSON\_OBJECT, then adds the current JSON\_OBJECT to the JSON\_ARRAY |
| **json\_create\_object\_sub** | JSON.CREATE.OBJECT | KV\_ARRAY, JSON\_OBJECT | Returns a JSON_OBJECT that contains \{key/value pairs\} |

* This program was designed to build the json data structure by appending data in json format to a string as a program is being executed.
* This program was **NOT** designed to convert a large complex dynamic array to a json data structure.
 * But you should be able to loop through your existing dynamic array, and build your json string using these subroutines.
   * you might have to 
		* pull data out of your array
		* create a new dynamic array that represents the \<X,1=key>,\<X,2=value> format for one record at a time.
* alternatively use JSON.ADD.PAIR to help build the dynamic array.
	* Each call to JSON.ADD.PAIR will add a new key/value pair to the next attribute in the dynamic array.  
* convert that new dynamic array to a json object using JSON.CREATE.OBJECT
* Then add that json object to a json array of objects using JSON.ARRAY.ADD.OBJECT
* To create an json **array of objects** : see **Example 1** in JSON.EXAMPLE d3 program
* Create a simple json object that is assigned to a key  **Example 2**
* Create a json object with no key **Example 3**

***Below is the output of JSON.EXAMPLE d3 program***

```
:JSON.EXAMPLE

**************************************************************
EXAMPLE 1: Build an array of employee objects.
             nesting objects...each employee object contains a driver object & a contact object
**************************************************************

{employees:[{"number":875,"first_name":"Ted","last_name":"Kennedy","date_of_birth":"1965-01-08","pho
ne":"9031239999","hire_date":"2007-10-20","driver":{"license_number":54375789,"expires_on":"2019-02-
13","active":true},"contact":{"address":"322 County Road Northwest 1233","city":"Dallas","state":"TX
","zip":23434,"phone":2134566777,"BOOLtest1":1,"BOOLtest2":"true","BOOLtest3":true,"BOOLtest4":true}
},{"number":875,"first_name":"Ted","last_name":"Kennedy","date_of_birth":"1965-01-08","phone":"90312
39999","hire_date":"2007-10-20","driver":{"license_number":54375789,"expires_on":"2019-02-13","activ
e":true},"contact":{"address":"322 County Road Northwest 1233","city":"Dallas","state":"TX","zip":23
434,"phone":2134566777,"BOOLtest1":1,"BOOLtest2":"true","BOOLtest3":true,"BOOLtest4":true}},{"number
":875,"first_name":"Ted","last_name":"Kennedy","date_of_birth":"1965-01-08","phone":"9031239999","hi
re_date":"2007-10-20","driver":{"license_number":54375789,"expires_on":"2019-02-13","active":true},"
contact":{"address":"322 County Road Northwest 1233","city":"Dallas","state":"TX","zip":23434,"phone
":2134566777,"BOOLtest1":1,"BOOLtest2":"true","BOOLtest3":true,"BOOLtest4":true}},{"number":875,"fir
st_name":"Ted","last_name":"Kennedy","date_of_birth":"1965-01-08","phone":"9031239999","hire_date":"
2007-10-20","driver":{"license_number":54375789,"expires_on":"2019-02-13","active":true},"contact":{
"address":"322 County Road Northwest 1233","city":"Dallas","state":"TX","zip":23434,"phone":21345667
77,"BOOLtest1":1,"BOOLtest2":"true","BOOLtest3":true,"BOOLtest4":true}}],"request_timestamp":"05/31/
18 10:32:16AM"}

**************************************************************
EXAMPLE 2: Build a single json employee object
**************************************************************

{"employee":{"number":875,"first_name":"Ted","last_name":"Kennedy","date_of_birth":"1965-01-08","pho
ne":"9031239999","hire_date":"2007-10-20"}}

**************************************************************
EXAMPLE 3: without the employee key
**************************************************************

{"number":875,"first_name":"Ted","last_name":"Kennedy","date_of_birth":"1965-01-08","phone":"9031239
999","hire_date":"2007-10-20"}
:
```


        
        
