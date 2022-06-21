REST nowadays (that being said: 2022), is one of the most commonly used API paradigms. We see it everywhere: "how to create a REST API", "REST and CRUD", "Criação de API REST"....

But in the end, whats a REST API?

Well, for starters, REST paradigm supposes you are using an HTTP protocol, and we have a domain (not required), lets say... https://dinos.dev , which serves an API.
This API provides us with some actions as: querying for dinosaurs, creating dinosaurs (yes, just as Doctor Wu. from Jurassic Park), etc

A REST API, basically means that we are going to follow a certain route format pattern and start our api path with an ``/api`` routes. So, in our case:
- for dinosaur queries: ``/api/dino``
- for dinosaur creation: ``/api/dino``
....

_"Wait?..."_  
... I know, I know, I'm getting there... As you saw, both paths are the same and no, its not a typing mistake (although I'm almost committed to them 🙃). Why?
REST API follow two key things that these endpoints show us:
- Routes are composed of objects you access (so names, no actions)
- And routes use HTTP methods in combination with crud operations (there you, here is your answer)

You don't get it yet?

No worries, that's normal, I'm going to help you giving something you else to work with in a sec: 
- Again, dino query: *``/api/dino``* <- with ``GET`` method
- Again, dino creation: ``/api/dino`` <- with POST method
- A new one, Dino species query: ``/api/dino/my-dino-id/species`` <- with GET
- A new one, Dino id delete: ``/api/dino/my-dino-id`` <- DELETE

So, we could almost compare we are using object keys \['api'\]\['dino'\] ... and we go through different levels and data using simple url paths. 
And to describe what we are actually doing with that data, we use four HTTP method: POST, GET, PUSH, DELETE (a.k.a. CRUD: Create, Read, Update and Delete).

The thing is, I don't like deleting dinos and I'm now removing my ``/api/dino/my-dino-id`` with a DELETE method path... 
Well, that's a breaking change and consumer are going to have issues with that, and with that we get to the last bit (but not least) of the REST characteristics: the api versioning. 
For that we just add a ``v{your-version-num}`` to the path:
- ``/api/v2/dino`` 
Now we are successfully protecting Dinos with our second version 🦖.

### Drawbacks ?
Well, REST is not the all-go solution...
- Even having easy setup, it is not that scalable, and documentations become required, and even with them, it can become the source of your worst nightmares: imagine having a hundred root paths after ``/api/version/`` and each of them having more child routes 🤯...
- And by mentioning documentation.. keeping it, even in smaller APIs, isn't that easy and also it increases research and setup times for consumers. 
- Its operations are limited: let's say I want to archive a dino (no more deleting, just archiving, be good with dinos 😡)... we could use PUT and pass data, but it isn't that obvious... CRUD, can limit us sometimes...
- Roundtrips are also a thing... Lets say you want to get info about a certain Dino: you first have to get all Dino ids, filter it on the requests client-side, make a second request with the requires data with that Dino ID and only then you have the data.
- Excessive data: unless you setup complex pagination and etc... Usually REST request will just vomit everything on you... And you can imagine how nasty things can get (huge response payloads)



