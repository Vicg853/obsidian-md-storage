Unix follows a concept that files are everything: networking, configs, auth, processes, etc...

But in reality, its the opposite... There is an element, that discern from this concept: file descriptors. 
When you open a file, this file creates a virtual process, that is called a file descriptor, which contains information about this file, a path to its content, edition status, modification functionalities.... 
In case the file opened has some security policy (e.g.: you may need to use ``sudo`` as an example), the system checks for your credentials when opening it and then its descriptor is created.

And here an issue emerges... you can't access a descriptor from another process, following the described path, but descriptors in themselves have no security at all after being opened, as recurrent checks would present sub-optimal for performance.

Linux presents an option that allows users to copy a file content and pass it to a command (usually used for error logs), which, can directly read even a file descriptor...
So here we are, reading an open file descriptor's, without having the credentials for it...

So closing files is one of the smallest practices, but good ones and required to be followed. 


