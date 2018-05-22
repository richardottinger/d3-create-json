# d3-create-json
Create json in your d3 program. To install: copy the code from each file to your d3 system.  I'm using d3/linux.  Then flash compile-catalog each subroutine/d3 program.

| File Name                 | Subroutine      | Description |
| ------------------------- |:---------------:| -----------:|
| **test\_d3\_creating\_json** | JSON.EXAMPLE    | Main d3 program that makes calls to the subroutines to generate json.|
| **build\_json\_object\_sub** | BUILD.JSON.OBJECT | calls CREATE.KEY.VALUE.PAIRS and assigns the object to a key that was passed to it. See Example 2|
| **create\_value\_pairs\_sub** | CREATE.KEY.VALUE.PAIRS | Convert dynamic array to json object.|
| **json\_add\_object\_sub** | JSON.ADD.OBJECT | Adds an object to the current json array...closes the array if the last argument is 1 else appends a comma |
| **json\_start\_array\_sub** | JSON.START.ARRAY | Begins a json object and assigns the array to a key|
