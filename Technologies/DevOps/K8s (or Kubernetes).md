## What is kubernetes....

<aside> 💡 Kubernetes or as we call k8s, means helmsman or pilot in Greek. It was named like this, because, in the same way a pilot manages all the systems on a plane/boat and other people, Kubernetes does this, by managing and maintaining the cluster

</aside>

Soo... what's Kubernetes? First let's give a quick look into it's 'rival' (just kidding, it's not it's rival, just, a different solution), the monolith. A monolithic architecture is normally composed of a server (virtualized or bare metal) that runs a number of applications (them being: pages, back-ends, APIs, DBs, or anything else basically), together in one environment. So, this technique, is not, problematic, it's a good solution if you are maybe a very small business, with only a simple web page, or system, for only internal use and you don't wan't to spend too much money on big infrastructures. But, it has it flaws: in case the server get's down, or you need to update the application, you basically, well, lose all access and also, it is pretty difficult to scale it up and down (that being sad, it is not impossible, but difficult). And what Kubernetes does, it basically improves and makes shit easier kkkkkk.

Now that we know, why we use Kubernetes, what is it. Kubernetes basically saying, is an container (containers are like mini environments which run applications, using direct systems resources but abstracting the app from the system, like, a smarter VM) orchestrator (and the it's names summarizes it... Kubernetes in Greek, means Pilot, or Captain of the ship more precisely), what it does, is practice what is called a Microservices architecture. Kubernetes in a summary, is a cluster, composed with multiple nodes: nodes are machines, them being virtual machines or physical ones, being controlled by Kubernetes system and run the apps; and well, a cluster, now I think it is pretty obvious what it is kkkkkkkk (if not, it is just a group of nodes). Inside these nodes, a multitude of things are in play: pods (an abstraction of app, container(s), basically your app and it's need, that can be replicated and multiplied), services (the way other pods, systems, services find your multiple pods for a certain app), deployment (it's your app's "image"/"deploy instructions" which contain specifications about your app, where you describe details about it's service, how many replicas, container images, ports and multiple other things), ingress (the way you expose your apps/pods/services to the outside world, either way, you would launch all these container and systems, for you cluster only and well, this way I really don't see how all of this you created is helpful, if no one can access any of it) and the control plane (where the Kubernetes brains are placed, the brains, where all the decisions, pods/services/systems/deployments/ingresses management, keys storage and nodes controls are done. It is located in all nodes, but only the one in the called master nodes, issues all orders and receives instructions).
### More in depth

-   Cluster:
    
    Group of Kubernetes cluster in one or multitude of regions (multi cluster running together is possible)
    
-   Node:
    
    Virtual or physical machine running Kubernetes resources
    
-   For - Master node
    
-   For - Worker node
    
-   Secret and configMap
    
    ConfigMap: Component that can contain configuration data externally from your application (but accessible inside in multiple ways). It can be used for many things, but as an example we can store a database url in it, or other url for something that apps may need to access.
    
    Secret: well, it is almost the same thing as the ConfigMap, but differently from it, it is used for more sensitive information, like for example, credential. So the diference, is that it encrypts this data, instead of leaving it in plain text or readable to anyone. It uses base64 encoding for encryption. !!!! Caution: it is not configured by default in Kubernets, it must be enabled and configured
    
-   Deployment:
    
    App specifications/instructions, that Kubernetes will use to create the resources you need for it (pods, services, ingress, nodePorts and anything else basically) (normally written in YAML file).
    
    In a very simple/basic way, an example is: let's say you have a Blog, with a Database (storing posts) and API (managing /gathering posts data). You will create a deployment for each of these elements (we have a 3 node cluster with a LoadBalancer fo bare matal load balancing only):
    
    -   Blog front-end: you will create a file, where you will define a deployment with a NGINX docker image, that serves the HTML/CSS/JS files of your front-end, you will define that this deployment will have 2 replicas (because, probably it will have lot's of requests with people entering the page, requesting multiple pages and front-end resources) and define which port it will be exposed on + it's tag. Then you will define a service, that will be linked to this specific app by the respective tag and give it a tag to access it. Finally you will define an ingress that will route all root traffic of the domain, to the respective service tag of your deployment
    -   API: just like the front-end, you will create a deployment, with on a NodeJS alpine docker image, that this time is going to receive and give JSON data only and will have 4 replicas that will be exposed in a certain port + contain a tag (as probably request to this API will occur more often: to give a post list, to create posts, to get full post content, to search posts, to edit posts, to manage posts access). Then we will define a service that will have a tag and will connect to pods with an other tag. Then, we will get the same ingress that will be created for the fron-end and we add the rule that, all traffic, containing a prefix "/api" on it's request path to the domain, will redirect request to the corresponding service IP with the respective tag. An additional thing this deployment will have, is that to each pod created, Kubernetes will inject an Env variable that the app will access, and this variable will be based of the secrets containing the DB access credentials
    -   DB: Well have a StatefullSet (a statefullSet is a type of deployment for Statefull applications) (to prevent data inconsistency between different DB instances) containing a... let's use a MySQL docker image and let's replicate it 4 times. The big diferences from this deployment, is that, we will create a volume, to store all the data, as we have to keep this data, on pod fail, change, replication and even node/cluster fail. Well then create a service that just like the other two deployments will have a tag and will give access a respective tag pods. But, this time, well not make this service accessible outside the cluster with an Ingress as Databases should only be accessible to certain resources. And lastly, we will publish the db credentials to Kubernetes secret, so other serices just like the API does can access the DB with credentials.
    
    And there we have, an almost full resilient Kubernetes cluster deployed.
    
-   StatefullSet:
    
    Statefull special deployment for statfull applications, like database, where you can prevent for example data inconsistency in a database. They can be pretty inconvinient sometimes, but are not impossible and there are tools that make them more handy.
    
-   Service: Access to pod(s)
    
    Way to make pods accessible internally. Why? Pods are not static resources, they can be replicated, modified, fail and many other things can happen to them, which basically means, lot of I.P addresses and port changes. to prevent other pods and services to keep track of every pod and pod's address changes, we use services. The service, will keep track of it's respective(s) pods addresses / load balance the traffic between them, this way, your app, is accessible on only one address without compromise, so even when changes are made to pods, you will still have access on the same address and if you have multiple replicas (even on multiple nodes), in the case of one or the majority of them failing, you still have access to others in the same address.
    
-   Pods:
    
    Container abstraction, where your app will literally run, that can run multiple containers (normally not a multitude of apps but maybe apps dependencies, like control proxies/sidecars others) and can be replicated. They give the ability to Kubernetes to handle/manage properly a container.
    
-   Volume