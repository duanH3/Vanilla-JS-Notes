# Multiple Form Field

There are times when you have to handle multiple form input in Node with Ajax, there are a few things we have to put into consideration as well. Error handling on the server side, Error handling on the client side, type of response to send from server, how the client side should receive and handler those response accordinly.

# Client side FORM, AJAX
Example we had the following form with 2 inputs on the client side.

```
<form method="post" id="submitform" >
    <input type="text" placeholder="write something" name="title" required>
    <input type="text" placeholder="write something" name="content" required>
    <input type="submit" value="Save">
</form>
```

Basic ajax skeleton for sending data to server with success/error handling

```
$("form#submitform").on('submit', function(e){
    e.preventDefault();   //prevent node default
    
    var $title = $('input[name=title]').val();
    var $content = $('input[name=content]').val();
    var $base64 = $('#base64').attr('src');     //upload base64 image

    $.ajax({
        type: 'post',
        url: '/ajax',
        data : {
          title : $title,
          content : $content,
          base64 : $base64
        },
        dataType: 'json'  //receiving json type
    })
    .done(function (data) {
        // do something with response.message & data on success
    })
    .fail(function (jqXHR, textStatus, errorThrown) {
        // do something with response.message & data on error

        //console.log('1', textStatus);             //error
        //console.log('2', jqXHR.responseJSON);     //all status data in json
        //console.log('3', errorThrown);            //internal error server
    });
});
```

# Server side with EXPRESS package

Upon receving post request, validate input and response if error or success
```
var express = require('express');
var router = express.Router();

router.post('/ajax', function(req, res){

    req.sanitize("title").trim();                                   //remove all empty space
    req.sanitize("content").trim();
    req.checkBody('title','title is required').notEmpty();          //check for empty input
    req.checkBody('content','content is required').notEmpty();    //include error message if error

    let errors = req.validationErrors();                            //compile errors

    if(errors){
        // response with error status 500, followed by json data of the invalid input name and messages.
        res.status('500').json(errors);     //response with error status and compiled error json data

    } else {
        // do something with response.message & data on success
        //res.status('200');
        //res.status('200').json({type: 'ok', title: 'value', body: 'value'})
    }

});

```





