Measuring time is essential for life itself and the same can be applied into circuitry. In computers, time is an abstract subject, as multiple factors must be taken into count: :"what is time ?", "which reference do we use ?" and "where does it start ?" among other questions.

Based on this, the default used method, is that for each system, the clock is used to increment a counter and based on operations of clock speed as well as the counter's storage capacity, a simple math gives us the counter's overflow interval, giving us: time.

In a nutshell, a counter with a $2^n$ capacity, increments at each clock tick. At each overflow, it resets and a signal is sent. This signal, is then used, based on our knowledge of the system characteristics, to process time.

#### Arduino UNO
Here are [[Time|examples]], with the Arduino Uno ATMEGA326 specific characteristics.