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
- Add an HTTP Request Sampler component to the thread group
- Under HTTP Request, change implementation to HTTPClient4
- Fill the prperties of the HTTP Request Sampler component,as follows
- Add request body(json)
- Add an HTTP Header Manager component to the HTTP Request Sampler component(right-click on HTTP)
- Add a request header with the following
  - Name: Content-Type
  - Value: application-json
- Add a View Results Tree Listener to the thread group (right-click on thread group and navigate to Add Listener | View Results Tree)
- Save the test plan


