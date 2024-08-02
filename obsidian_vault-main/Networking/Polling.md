
2024-07-29 | 08:32

##### Tags: [[Networking]] [[TAGS/Polling|Polling]] [[Webhooks]]


---

Polling is a concept that simply means checking for new data over a fixed interval of time by making API calls at regular intervals to the server. It is used to get real-time updates in applications.

### Short Polling
In a Short Polling the client will send requests to the server in a regular intervals to get the data from the server. If the data is available the server will respond with it. If not, an empty response will be sent back to the client

### Long Polling
In a Long Polling the problem that exists in the Short Polling with sending possibly empty request if the server is not available is solved by holding the request up until the response gets available, & after the response is available the server will send the response back. After getting a response, again the request will be made either immediately or after some period of time and this process will repeat again and again. In simple words, the client will always be in the live connection to the server.

Examples: Taxi driver tracking app, Train tracking app

