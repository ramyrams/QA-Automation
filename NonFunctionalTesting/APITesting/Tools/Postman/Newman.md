
* [Newman is a command-line collection runner for Postman](https://github.com/postmanlabs/newman#cli-reporter)

https://github.com/postmanlabs/newman
https://github.com/DannyDainton/newman-reporter-htmlextra
https://ravivamsi.github.io/postmanframework/

# Reporting
## Postman Newman HTML reporter
https://github.com/DannyDainton/newman-reporter-htmlextra

A couple of other out of the box reporters are also available for you to use with the Newman, these include JSON, JUNIT, Progress and Emojitrain. These give you a different output depending on your needs. They can be specified using the -r <reporter name> command.
  
newman run https://www.getpostman.com/collections/24473d1926b7ff9a8567 -r progress

To use more than one reporter, just simply add a comma and the name of the reporter:
newman run https://www.getpostman.com/collections/24473d1926b7ff9a8567 -r cli,progress,junit

npm install -g newman-reporter-<reporter name>

## Sample Report

### newman-reporter-html
https://www.npmjs.com/package/newman-reporter-html
$ npm install -g newman-reporter-html
* https://newman-htmlextra-reports.s3.eu-west-2.amazonaws.com/postmanHTMLReport.html

### newman-reporter-htmlextra
https://www.npmjs.com/package/newman-reporter-htmlextra
$ npm install -g newman-reporter-htmlextra
* https://newman-htmlextra-reports.s3.eu-west-2.amazonaws.com/Full_Report.html


![](https://github.com/DannyDainton/post-con-2019-workshop/raw/master/Assets/Newman/Newman_File_Export.gif)

![](https://github.com/DannyDainton/post-con-2019-workshop/raw/master/Assets/Newman/Newman_Link.gif)

