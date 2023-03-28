Circuit's to be useful, need to be able to exchange information and use other's results. Hence the need of a communication highway and the creation of the communication Bus. 

The Bus is a circuit, capable of connecting two circuits together and allowing them to communicate. 

There are two main Bus types:
- [[#Serial|Serial]]
- [[#Parallel|Parallel]]

Even though each one has advantages one over the other, the most important thing is that each one has its purpose and best use cases.

With that, one of the most important concepts to understand about Busses, is that they usually shared by many circuits, so they are able to talk communicate with each other. 
Because of that, we find ourselves with the entail of a circuit controlling whose information is shared on the Bus at which moment. 

In modern systems, we usually have different Bus types coexisting in the same system at the same time and for that, [[Multiplexers & De-multiplexers|multiplexers and de-multiplexers]] are essential to transform multiple channels into a single channel bus and vise-and-versa.

### Bus types
##### Serial
Here, communication is performed in a single cable and in series. In other words, a serial bus, is at the base, composed of a single cable, which transmits each of a byte's bits, one after the other, just like in a queue.

Nowadays, some serial Busses (SATA, USB, ...) are composed of multiple cables, but at the base, they maintain the same behaviour: a bit sequence is sent on a single cable, one bit after the other. 

This approach allows for cheaper and simpler circuits, as they require less resources, with the cost of being slower, as a byte sequence must be split into bits and sent sequentially.

##### Parallel
In parallel circuits however, communication is done in multiple cables. A whole byte is sent at once over multiple cables, one for each bit. 

PCI is one of the current circuitry using this architecture.

This approach also has its disadvantages: it requires more complex and expensive circuitry. Nonetheless it can be substantially faster, as it can send bytes as a whole and therefore, send batches of bytes in the time serial is sending a single one.