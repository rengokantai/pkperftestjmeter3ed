# pkperftestjmeter3ed

## Recording Your First Test


## Submitting Forms
More and more websites are embracing RESTful web services, and as such, you will mainly
interact with JSON objects when recording or executing test plans for such applications.
Another area of interest will be recording applications that make heavy use of AJAX to
accomplish business functionality. 

### Capturing simple forms


### Handling file uploads
file must smaller than 1mb, file must in bin folder

### Handling file downloads

You can add a ViewTree Listener and examine the response output after playing back the
recording.



### Posting JSON data
note
- Rest is a simple stateless architecture that generally runs over HTTP/HTTPS.
- Requests and responses are built around the transfer of representations of resources.

- Flexibility is provided by assigning resources their own unique URIs. Since each operation
has a specific meaning, REST avoids ambiquity.


steps:
- Launch Jmeter
- Add a thread group to the test plan
- Add an __HTTP Request Sampler__ component to the thread group
- Under HTTP Request, change implementation to HTTPClient4
- Fill the prperties of the HTTP Request Sampler component,as follows
- Add request body(json)
- Add an HTTP Header Manager component to the HTTP Request Sampler component(right-click on HTTP)
- Add a request header with the following
  - Name: Content-Type
  - Value: application-json
- Add a View Results Tree Listener to the thread group (right-click on thread group and navigate to Add Listener | View Results Tree)
- Save the test plan


### Reading JSON data
steps:
- Launch JMeter.
- Add a thread group to the test plan
- Add a __HTTP Request Sampler__ to the thread group
- Under HTTP Request, change implementation to HttpClient4.
- Fill the properties of the HTTP Request Sampler, as follows
  - server name or IP
  - Method `GET`
  - Path:

### Using JSR223 PostProcessor
When dealing with more complicated JSON structures, you might find that the regular expression exractor doesnot
remove it. You might struggle to come up with the right regular expression to extract all the info you need.

steps:
- Launch JMeter
- Add a thread group
```
eval('var response = ' + prev.getResponseDataAsString()); 
 
vars.put("jokes_cnt", response.value.length); 
 
for (var i = 0; i <= response.value.length; i++)       
{            
    var x = response.value[i]; 
   vars.put("joke_" + i, x.joke); 
} 
```



### Handling XML responses
Another structure you may encounter as you build test plans is XML.  
Some websites may hand off XML as their response to certain calls.  
XML allows you to describe object graphs in a different format than JSON does.
