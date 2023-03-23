Commands can be quite a complicated subject, they are a special way to summon programs.

There are many ways to use and structure them. We could actually use them anyway we want. For that the _POSIX_ convention was determined. It is used pretty much everywhere nowadays. It states that:
- arguments are plain text elements written in the command line (the program itself also corresponds to one)
- options: options are identified by ``-`` before them, they can be written separately or chained together (and placed in any order when together)
- long options (as extended by GNU): are a newer idea, that makes options more humanly comprehensible, allowing for longer and more understandable labels, that are pretty specific 

They are all forwarded to a program when on its call.

