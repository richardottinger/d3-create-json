# d3-create-json
Create json in your d3 program. To install: copy the code from each file to your d3 system.  I'm using d3/linux.  Then flash compile-catalog each subroutine/d3 program.

| File Name                 | Subroutine      | Description |
| ------------------------- |-----------------| ------------|
| **test\_d3\_creating\_json** | JSON.EXAMPLE    | Main d3 program that makes calls to the subroutines to generate json.|
| **build\_json\_object\_sub** | BUILD.JSON.OBJECT | Only use this when you want to create an object as assign it to a key. calls CREATE.KEY.VALUE.PAIRS and assigns the object to a key that was passed to it. See Example 2|
| **create\_value\_pairs\_sub** | CREATE.KEY.VALUE.PAIRS | Convert dynamic array to json object.|
| **json\_add\_object\_sub** | JSON.ADD.OBJECT | Precondition: A call to JSON.START.ARRAY must begin the json array...Adds an object to the current json array...closes the array if the last argument is 1 else appends a comma |
| **json\_start\_array\_sub** | JSON.START.ARRAY | Begins a json object and assigns the array to a key|

* This program was designed to build the json data structure by appending data in json format to a string as a program is being executed.
* This program was **not** designed to build a large dynamic array then call a subroutine & magically poof... json then appears.
 * But maybe you can get cleaver and loop through your dynamic array, and build your json string using these subroutines.
      * you might have to pull data out of your array and create a new dynamic array that represents the \<X,key>,\<X,value> format for one record at a time.
* **Remember** to start your json string { ...before a call to BUILD.JSON.OBJECT and also before you start a json array using JSON.START.ARRAY.
* **Remember** to end your json string } ...when you want to end your json structure
* CREATE.KEY.VALUE.PAIRS will return a json object that contains key:value pairs so if that is all you need then you don't need to start/end { } your json string.  See Example 3
* To create an json **array of objects** : see **Example 1** in JSON.EXAMPLE d3 program
 * First begin your array by making a call to **JSON.START.ARRAY** and pass the key that you want the array set to and the variable name of the json string
 * Then build a dynamic array that represents all of the key value pairs for one record. (example: 1 employee or 1 resource)
     * Each Attribute represents one key/value pair. \<X,1>=@:key, \<X,2>=value
         * \<X,1>="[DataTypeCode]:key"  ...replace [DataTypeCode] with one of the characters that identify which data type you want for this field
            * @=**string**
            * \#=**number**
            * !=**boolean** ...value should set to "1" which will converted true in json else false
            * $=**object**
            * : if you just add a colon then data type will default to **string**
    * call CREATE.KEY.VALUE.PAIRS and pass that dynamic array which will be converted to a json object that contains key:value pairs
    * then add that object to the current json array by calling JSON.ADD.OBJECT
                * remember to indicated if this is the last object in the array by passing 1 in the last argument, else a comma will be appended to the object.
        * REMEMBER to end the json string }
* Create a simple json object that is assigned to a key  **Example 2**
        *  Create dynamic array \<X,1>=@:key, \<X,2>=value
        *  Call BUILD.JSON.OBJECT
* Create a json object with no key **Example 3**
        *  Create dynamic array \<X,1>=@:key, \<X,2>=value
        *  Call CREATE.VALUE.PAIRS

```
:JSON.EXAMPLE
**************************************************************

EXAMPLE 1: Build an array of employee objects.  each employee object contains a driver object


{"employees":[{"number":875,"first_name":"Ted","last_name":"Kennedy","date_of_birth":"1965-01-08","p
hone":"9031239999","hire_date":"2007-10-20","driver":{"license_number":54375789,"expires_on":"2019-0
2-13","active":true}},{"number":875,"first_name":"Ted","last_name":"Kennedy","date_of_birth":"1965-0
1-08","phone":"9031239999","hire_date":"2007-10-20","driver":{"license_number":54375789,"expires_on"
:"2019-02-13","active":true}},{"number":875,"first_name":"Ted","last_name":"Kennedy","date_of_birth"
:"1965-01-08","phone":"9031239999","hire_date":"2007-10-20","driver":{"license_number":54375789,"exp
ires_on":"2019-02-13","active":true}},{"number":875,"first_name":"Ted","last_name":"Kennedy","date_o
f_birth":"1965-01-08","phone":"9031239999","hire_date":"2007-10-20","driver":{"license_number":54375
789,"expires_on":"2019-02-13","active":true}}],"request_timestamp":"05/23/18 08:27:45AM"}
**************************************************************


EXAMPLE 2: Build a simple json employee object


{"employee":{"number":875,"first_name":"Ted","last_name":"Kennedy","date_of_birth":"1965-01-08","pho
ne":"9031239999","hire_date":"2007-10-20"}}
**************************************************************

EXAMPLE 3: without the employee key


{"number":875,"first_name":"Ted","last_name":"Kennedy","date_of_birth":"1965-01-08","phone":"9031239
999","hire_date":"2007-10-20"}
:
```
