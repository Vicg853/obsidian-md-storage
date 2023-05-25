Storage is a complicated subject, mainly when talking about physical space limits. There are however ways where we can may partially reduce the space required used by some data, we are therefore talking about compression. 

Compression can also be tricky sometimes, by bringing time complexity, information loss, and other issues to the light. 
There are two core compression types:
> [!abstract] [[#Lossless|Lossless]]
> Information is not lost whatsoever, which can sometimes result in a wider storage space requirements

> [!abstract] [[#Lossy|Lossy]]
> Some information may or not be lost, possibly resulting less used storage space 

There isn't a worst or better one, but just the best for the task: when compressing programs or textual files, lossless can be pretty efficient already, which is anyway necessary, as textual information shouldn't be lost (as it can cause it to become non-understandable). As for videos and images, where the same information isn't repeated as often, lossy does better the job, by achieving higher compression rates most of the time.

#### Lossless
Three of the mostly used lossless compression algorithms are:
- _Redundancy omission_: where redundant information is replaced by something less space consuming at each occurance
- _Entropy coding_: statistical analysis is made on the source, creating a custom code that will from now on represent the file
- _Dictionary encoding_: in a nutshell, we can say that this technique combines the two types mentioned above, by replacing redundant information with a custom code. The information is then coupled with a "dictionary" which defines replaced redundant information.

#### Lossy
