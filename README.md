# d3-create-json
Create json in your d3 program. To install: copy the code from each file to your d3 system.  I'm using d3/linux.  Then flash compile-catalog each subroutine/d3 program.

***UPDATES HAVE BEEN MADE TO TO CODE TODAY 05/30/18 but this README file has not been updated yet***
***THE PLAN IS TO UPDATE this README tomorrow or asap.***
***You can checkout the previous commit if you need to view the previous code or previous readme.***


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
