
* [Newman is a command-line collection runner for Postman](https://github.com/postmanlabs/newman#cli-reporter)


# Reporting
## Postman Newman HTML reporter
https://github.com/DannyDainton/newman-reporter-htmlextra

A couple of other out of the box reporters are also available for you to use with the Newman, these include JSON, JUNIT, Progress and Emojitrain. These give you a different output depending on your needs. They can be specified using the -r <reporter name> command.
  
newman run https://www.getpostman.com/collections/24473d1926b7ff9a8567 -r progress

To use more than one reporter, just simply add a comma and the name of the reporter:
newman run https://www.getpostman.com/collections/24473d1926b7ff9a8567 -r cli,progress,junit


![](https://github.com/DannyDainton/post-con-2019-workshop/raw/master/Assets/Newman/Newman_File_Export.gif)

![](https://github.com/DannyDainton/post-con-2019-workshop/raw/master/Assets/Newman/Newman_Link.gif)

