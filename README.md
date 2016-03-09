## HTTP Questions



__URLs__

* Name all of the parts of the url that you can remember.  In your own words describe what they do.

```Answers
protocol: http:// or https://, used to transfer hypertext 

domain: readable/usable name for IP address

port:  associated with IP address, where info is paassed 

path: after the port, but before the query string, it is like a file path

query string: list of arguments that may modify the request

anchor tag: starts with # and acts as a quick jump

```



* Name the pieces of the following urls:
	* `https://www.google.com/`

  ```Answer
  https:// is the protocol, www.google.com is the domain
  ````

	* `https://workbook.galvanize.com/cohorts/41/learning_experiences/367`

  ```Answer
  https:// is the protocol, www.workbook.galvanize is the domain, cohorts/41/learning_experiences/367 is the file path
  ````

	* `http://locahost:5000/animals/puppies?onlycute=1&size=medium#firstpuppy`

  ```Answer
  https:// is the protocol, localhost is the domain, 5000 is the port, animals/puppies is the file path, everything after ? is the query string
  ````

	* `https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#4xx_Client_Error`

  ```Answer
  https:// is the protocol, en.wikipedia.org is the domain, wiki/List_of_HTTP_status_codes is the file path, #4xx_Client_Error is the anchor tag
  ````


* Can a server use more than 1 port?

```Answer
yes
```

* Why is https different than http?

```Answer
https is secure
```

* How does a server interpret the following url's query paramter.  What data structure does it create on the server?

```Answer
array of data as a query parameter, puppies is the key
```



__HTTP Request/Response__

* Name at least 4 http verbs

```Answer
GET, POST, PUT, DELETE
```

* What is each verb useful for in your own words

```Answer
GET= retieves information from the server,  POST=sends information to the server, PUT=updates information on the server, DELETE= deletes information on the server
```

* What does idempotent mean?

```Answer
there is no difference between doing it once or ten times, you still get the same result
```

* Name the 5 http status code ranges.  What are they used for in general?

```Answer
1XX = still in the process of getting what you want
2XX = everything is good, you got what you wanted
3XX = redirect
4XX = client side error, server side is ok
5XX = server side error
```

* If a server returns a http status code of 301 and a location of `https://www.google.com/`, what does the browser do?

```Answer
redirects you
```

* For the following HTTP headers, decide if the following header is used for requests, responses or both:
	* Accept 
	* Content-type 
	* User-agent
	* Set-cookies
	* Cache-control
	* Cookie

```Answer
Accept for request
Content-type for response
User-agent for request
Set-Cookies for response
Cache-control for response
Cookie for request
```

* Is the following a http request or response?  How do you know for each?

```Answer
1. response, because status code is 200
2. request, because header is DELETE
```


```
HTTP/1.1 200 OK
Access-Control-Allow-Origin: *
Vary: Accept
Content-Type: text/html; charset=utf-8
Content-Length: 722
ETag: W/"2d2-Wu0We9N5g35FXWY+gOATLA"
Date: Tue, 08 Mar 2016 20:37:11 GMT
Connection: keep-alive

<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <link rel="stylesheet" href="/style.css">
    <title>Student Roster</title>
  </head>
  <body>
    <main>
      <h1>Student Roster</h1>
      
        <section>
          <h3>Daenerys Targaryen</h3>
          <span>Student Id: nys8fbohl</span>
          <h4>Hobby: Motherhood</h4>
          <img src="https://i.imgur.com/KlycRG5.jpg" alt="Daenerys Targaryen" />
        </section>
      
        <section>
          <h3>Tyrion Lannister</h3>
          <span>Student Id: njehukbohe</span>
          <h4>Hobby: Traveling</h4>
          <img src="https://i.imgur.com/fFMusdC.png" alt="Tyrion Lannister" />
        </section>
      
    </main>
  </body>
</html>
```

```
DELETE /students/n1vmyrw3x HTTP/1.1
Host: g22-students.herokuapp.com
Accept: application/json
Cache-Control: no-cache
Postman-Token: 0041e3c3-efdb-f0c3-b2f4-2d79f6d0f44b
```

__JSON__

* Describe what JSON is.  What is it used for.

```Answer
JavaScript Object Notation, structure is key value pair hash, data exchange format, it's only a string that represents objects, must be parsed in order for it to have meaning in a program.
```

* Convert the following map into a javascript object then console log the age.

```Answer
var comapnyArr = JSON.parse('{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}');
console.log(companyArr.age);
```


```
{ "company" : "Github", "age": 7, "categories" : "Services,Internet,Software"}
```
* Convert the following to a javascript object.  Console log each company name.

```Answer
var companyArr = JSON.parse('{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},{ "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},{ "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},{ "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}]
}');

companyArr.map(function(){
  console.log(companyArr.Companies.company);
})
```


```
{ "Companies":[ { "company": "Github", "age": 7, "categories": "Services,Internet,Software"},
              { "company": "Airbnb", "age": 6, "categories": "Hotels,Travel"},
              { "company": "Square", "age": 7, "categories": "FinTech,Hardware + Software,Finance"},
              { "company": "Dropbox", "age": 11, "categories": "Cloud Data Services,Storage,Web Hosting"}
            ]
}
```
* The following is javascript.  Convert the object to a string and console log it.

```Answer
var myObj = JSON.parse('{company: "Galvanize",age: 3,categories: "Education"}');
```


```
var myObj = {
  company: "Galvanize",
  age: 3,
  categories: "Education"
};
```
__MISC__

* Describe what DNS is.

```Answer
Domain Name Servers: they maintain directory of domain names and translate them into IP addresses
```


* In the terminal, type `man curl`.  Look at the man page for curl.  What do the following flags do? `-v`, `-X`.  (Hint: to search for a string, type `/` then the text you want, then enter.  To quit the man page, type `q`).

```Answer
-v means verbose, helps for debugging, -X specifies custom request
```

* What is TCP/IP?  How does it interact with HTTP?

```Answer
Transmission Control Protocol, it ensures data gets to and from the server. It breaks down big chunks of data into packets. IP, internet protocol, ensures packets get to the correct place. TCP/IP is a lower level process from HTTP, it receives and send information from/to HTTP
```

* Does HTTP break the data that is being sent into small packets?  If not, what protocol is responsible for it?

```Answer
TCP
```