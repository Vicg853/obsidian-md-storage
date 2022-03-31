GraphQl, is currently an open-source query language (since 2015), firstly created by Facebook engineers (holly shit, they are fucking good at this: react, graphql, redux, ...) on 2013. 
The idea behind GraphQl was to fix two main issues that normal APIs present: low scalability and over-fetching...

How so?

... Usually APIs, are "static": if you need to add more data, or parameters, or also remove them, your clients normally must be also modified based on these changes, which can create big issues and requires a lot of maintenance work. GraphQl solves this by not requiring all this: it works similarly to databases queries and uses objects, this way, new data can be added and without almost never affecting other services. Also there is no such problems as multiple and endpoints, and their modifications issues, thanks to its hierarchical structure. 
This way, you are able to fetch only what you need, or add more data to fetch, without disrupting other existing system from fetching their own data

Other solutions it provides:
- Typing: yes, graphql is typed
- Shrinks down complexity on microservices: in case you use microservices, with multiple services, databases, endpoints, you may join them all on a GraphQl server and provide an only interface for all these endpoints.

 ### And the downsides? everything has good and bad things
- Differently as many may think: no, GraphQl is not, a database, it is only a query language, some services like apollo server, may include Databases built-in and configured aong with GraphQl, but GraphQl is just an interface.
- Caching: one of the API advantages, is that we can use endpoints to determine what/when to cache things and control this caching. But in graphql this becomes a little bit more difficult... although there are already some solutions for this problem...
- Rate limiting




