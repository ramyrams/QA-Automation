https://stackoverflow.com/questions/1133770/convert-a-string-to-an-integer/1133814#1133814

https://medium.com/@vdespa/demystifying-postman-variables-how-and-when-to-use-different-variable-scopes-66ad8dc11200

https://www.moesif.com/blog/api-guide/api-design-guidelines/#nested-or-sub-resources
https://www.merixstudio.com/blog/best-practices-rest-api-development/
https://code-maze.com/top-rest-api-best-practices/
https://blog.florimond.dev/restful-api-design-13-best-practices-to-make-your-users-happy



https://learning.getpostman.com/docs/postman/environments_and_globals/variables_complete_reference/


# Form content types

These are different Form content types defined by W3C. If you want to send simple text/ ASCII data, then x-www-form-urlencoded will work. This is the default.

But if you have to send non-ASCII text or large binary data, the form-data is for that.

You can use Raw if you want to send plain text or JSON or any other kind of string. Like the name suggests, Postman sends your raw string data as it is without modifications. The type of data that you are sending can be set by using the content-type header from the drop down.

Binary can be used when you want to attach non-textual data to the request, e.g. a video/audio file, images, or any other binary data file.

### Request body

While constructing requests, you would be dealing with the request body editor a lot. Postman lets you send almost any kind of HTTP request (If you can't send something, let us know!). The body editor is divided into 4 areas and has different controls depending on the body type.

### form-data

multipart/form-data is the default encoding a web form uses to transfer data. This simulates filling a form on a website, and submitting it. The form-data editor lets you set key/value pairs (using the key-value editor) for your data. You can attach files to a key as well. Do note that due to restrictions of the HTML5 spec, files are not stored in history or collections. You would have to select the file again at the time of sending a request.

### urlencoded

This encoding is the same as the one used in URL parameters. You just need to enter key/value pairs and Postman will encode the keys and values properly. Note that you can not upload files through this encoding mode. There might be some confusion between form-data and urlencoded so make sure to check with your API first.

### raw

A raw request can contain anything. Postman doesn't touch the string entered in the raw editor except replacing environment variables. Whatever you put in the text area gets sent with the request. The raw editor lets you set the formatting type along with the correct header that you should send with the raw body. You can set the Content-Type header manually as well. Normally, you would be sending XML or JSON data here.

### binary

binary data allows you to send things which you can not enter in Postman. For example, image, audio or video files. You can send text files as well. As mentioned earlier in the form-data section, you would have to reattach a file if you are loading a request through the history or the collection.
