# Multiple Form Field

There are times when you have to handle multiple form input in Node with Ajax, there are a few things we have to put into consideration as well. Error handling on the server side, Error handling on the client side, type of response to send from server, how the client side should receive and handler those response accordinly.

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
    var $content = $('input[name=body]').val();
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



