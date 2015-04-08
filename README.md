# node csv converter
very simple useful converter for mongodb data,easy quick to use.

###Setting up
```
npm install node-csv-converter
```

###Usage

```javascript
var csv_converter = require('node-csv-converter'),
    mongojs = require('mongojs'),
    user = mongojs('User',['collections']);
  
user.collections.find(function(err,document){
    //document is array
    var converter = new csv_converter();
    converter.setField(['Name','Sex','Places','Country','Phone']);
    converter.cws(document,'./user.csv'); //create write stream
});

//about document:
{
  "Name":"MacTaylor",
  "Sex" : "Male",
  "Places":"HK",
  "Country":"TW",
  "Phone":"+886-76558958-8955"
}
//converter will put the right key into the field!

//about undefined or null variable:
{
  "Name":"MacTaylor",
  "Sex" : "Male",
  "Phone":"+886-76558958-8955"
}
//converter will be skipped and still put right key into the field!
```

###Like I said, it is so easy to use
