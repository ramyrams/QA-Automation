


https://github.com/redwebs/Postmanhttps://github.com/JohnnyBarry/postman_utils
https://github.com/etuchscherer/postman2curl

https://github.com/tarunlalwani/postman-utils


```javascript
if (typeof pmutil == "undefined") {
    var url = "https://raw.githubusercontent.com/tarunlalwani/postman-utils/master/pmutils.js";

    if (pm.globals.has("pmutiljs"))
        eval(pm.globals.get("pmutiljs"))
    else {
        console.log("pmutil not found. loading from " + url);
        pm.sendRequest(url, function (err, res) {
            eval(res.text());
            pm.globals.set('pmutiljs', res.text())
        });
    }
}
```

```javascript
pm.myUtility = {
    interpolateVariable: function (str) {
        return str.replace(/\{\{([^}]+)\}\}/g, function (match, $1) {
            // console.log(match)
            let result = match; //default to return the exactly the same matchd variable string
            if ($1) {
                let realone = pm.variables.get($1);
                if (realone) {
                    result = realone
                }
            }
            return result;
        });
    },
    getUrl: function () {
        let url = pm.request.url.getRaw();
        url = this.interpolateVariable(url)
        let {
            Url
        } = require('postman-collection')
        return new Url(url);
    },
    getUrlTest: function () {
        let url = pm.request.url.getRaw();
        url = this.interpolateVariable(url)
        // let {
        //     Url
        // } = require('postman-collection')
        //return new Url(url);
        return pm.request.url.parse(url);
    }
}

pm.myUtility.getUrl().getPath() Work like a charm

```
