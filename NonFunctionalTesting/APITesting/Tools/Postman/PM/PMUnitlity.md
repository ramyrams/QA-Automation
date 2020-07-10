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
