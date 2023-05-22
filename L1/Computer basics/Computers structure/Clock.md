The clock can be called an orchestrator as its job is to establish and keep track of an interval to make circuits "react". 

It is essential to a certain level, as it prevents circuits from sending miss-synchronized signals one to another, which could cause issues in some cases (such as with [[Flip-flops]], by sending both a set and reset signal).

We refer as the clock's "speed", the interval in which it sends signals for circuits to work and it is measured in $\mathrm{Hz}$ (Hertz), a.k.a. $n$ times per second (e.g.: $1 \mathrm{Hz} = 1$ signal each second).

#### Synchronous and asynchronous
This is a concept, that can even go up to the virtual computer science domain. They define a device that follows the clock's time (synchronous) or one that doesn't (asynchronous).

We may consider for example a network operation, which logically isn't conducted by a local clock: the circuit's response won't necessarily occur at the next clock "tick".

#### Stability
A problem that can often bother hardware conception, is the clock's signals' stability across the entire system as they may arrive sonner for some circuits and later for others as well as the signal not being 100% uniform the entire time. 

This can cause errors and race-conditions between circuits, which changes on a circuit material or composition quality basis. 

If its composition fits the speeds provided by the clock, every circuit should be "up-to-date" with the clock's variations.

It is therefore also important to know that some circuits intentionally have different reaction times. The high and low, as well as the crescent and decrescent are the four main stages we can identify.