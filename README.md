feelium-lib
===============

(https://www.npmjs.com/package/feelium-lib)

A javascript Feelium library for node.js and browsers.

## Get Started

feelium-lib  runs on [node](http://nodejs.org/), and can be installed via [npm](https://npmjs.org/):

```bash
npm install feelium-lib
```

## Examples

```javascript
var run = function() {
  var feeliumClient = require('feelium-lib'); 

  var config = {
    protocol: 'http',
    user: 'user',
    pass: 'pass',
    host: '127.0.0.1',
    port: '62019',
  };

  // config can also be an url, e.g.:
  // var config = 'http://user:pass@127.0.0.1:62019';

  var rpc = new feeliumClient(config);
  var jsonRequest = {
      "action":"account-info",
      “account”:”e61965217ft89367f52b43c610fd7e61”
  }
  function showServerInfo(jsonRequest) {
    

      rpc.getAccountInfo(jsonRequest, function(err, accountInfo) {
        if (err) {
          console.error(err);
           
        }else{
            console.log(accountInfo); 
        } 
    });
  }
 
};
```

## License

**Code released under [the MIT license](https://github.com/feelium/feelium-lib/master/LICENSE).**

Copyright 2018 feelium.co.
