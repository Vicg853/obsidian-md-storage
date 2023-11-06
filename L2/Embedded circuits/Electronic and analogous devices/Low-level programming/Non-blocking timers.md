```c
unsigned long previousMillis = 0;
unsigned long tempo = 250;

void setup() {}

void loop() {
	unsigned long currentMillis = millis();
	bool etatLed = true;

	if(currentMillis - previousMillis > tempo) {
		previousMillis = currentMillis;
		etatLed = !etatLed;
		digitalWrite(DEL, etatLed);
	}
}
```