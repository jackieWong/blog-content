Title: ajax & 302
Date: 8/21/2014
Tags: JavaScript
Category: Web

### HTTP 302

HTTP 302 response code mean the page is Moved Temporarily.

When server return this code, it will also give an `Location: http://xxx` field, in which browser will find a new URL to send another request.

Also see: [wiki/HTTP 302](http://en.wikipedia.org/wiki/HTTP_302)

### ajax cant get 302 status
	xhr = new XMLHttpRequest();
	xhr.open('get', 'http://10.8.0.1/index.php', false);
	xhr.send();
	
	xhr.status();	//if no error happened, 200
				
But what's in xhr.responseText.

Suppose we have two file: index.php & re.html.

index.php use function header() to redirect to re.html.
	
**index.php**

	<?php
		echo("This is php");
		header("Location: http://10.8.0.1/re.html");
	?>
	
**re.html**

	<p>This is html after redirect</p>

Then the content of xhr.responseText is :`This is html after redirect`

The order is :
`ajax -> browser -> server -> 302 -> browser(redirect) -> server -> browser -> ajax callback`
	
###  ajax readystatus

	xhr = new XMLHttpRequest();	
	xhr.readyState;		//0
	
	xhr.open();
	xhr.readyState;		//1
	
	xhr.send();
	xhr.readyState;		//4
### related links
[cnblogs: jax与302响应](http://www.cnblogs.com/dudu/p/ajax_302_found.html)