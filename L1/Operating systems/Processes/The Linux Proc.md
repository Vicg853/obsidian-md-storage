In UNIX operating systems, there is a small tip, that makes process analysis pretty simple: the ``/proc`` directory. 

It basically contains folders, named after running program's PIDs. Inside each folder, you can find information such as: program ram usage, files accessed by it, etc.

These files, aren't actually real, they are "virtually" generated and injected by the OS, they aren't actual disk data.