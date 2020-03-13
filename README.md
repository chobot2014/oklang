# oklang
it's gonna be ok

-- John Chohon, 2020 --

module syntax

Modules do run code outside of a function when imported

base module syntax
```
ok?
    //some code
ok!
```
```
ok?
    // we don't have positional parameters
    // functions are called with object syntax
    
    // print hello world to the user
    display{message: "hello world'};
ok!
```
```
// you can declare objects
ok?
    let<{something: string}> myObject = {something: "blah"}; 
ok!
```
```
// you can have dynamic types if you don't mind potential runtime errors
ok?
    let myObject = someJsonDeserializer{in: '{"someKey": "someValue"}'};
ok!
```
```
// you can declare arrays
ok?
    let<[string]> someListOfStrings= ["blah1", "blah2"];
ok!
```
```
// you can declare functions
// functions are objects.
// take an object and return an object
OK?    
    // IN_TYPE={}=>OUT_TYPE
    const<{}={}=>{}> someOtherFunction = {}={
        this.display{message: "hey there user, I'm inside a function"};
    }=>{};


    someOtherFunction{};
OK!
```
```
// you can have an iife
OK?
    const<string> randomString = (({<string>thing}={
        let<string> thingToGiveBack = "the thing is " + thing;
     }=>{ thingOut: thingToGiveBack
    }){thing: "apple"}.thingOut);
OK!
```
```
// modules can have imports and exports
OK?{
    <string> personName
}
    let<string> someMessage = "hello " + personName;
    // function calls are not positional
    this.display{message: someMessage};

    export {
        messageGiven: someMessage
    };
OK!{
    <string>messageGiven
}
```
```
OK?
    <string>message = "something"; 
    this.display{message};
OK!
```
```
// modules can have names but must explicitly put the in type
ok?ModuleWithAnExportedFunction{}
    const<{}={}=>{}> someFunc = {}={
        let<string> something = "blah";
    }=>{};

    export {
        exportedFunction: something;
    }
ok!{
    <{}={}=>{}>exportedFunction
}
```
