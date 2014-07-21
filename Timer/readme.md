++Millisecond Timer

Author: Glenn Burgess July 2014
License: MIT

An asychronous alarm timer, based on an existing clock. May be reset and reused.

Makes use of Arduino Time library. This library implements some functions omitted from the TimeAlarms library, such as enabling asynchronous alarm checking, and also millisecond timers.
The TimeAlarms library allows a global function to be called periodically, but this can only access global variables. A local timer such as Timer can be used to call methods on objects,
or use local variable values.

Example usage:
	include "Timer.h"
	
	Timer t(2500);
	
	// Make use of subsecond timer
	void loop() {
		while (!t.timeUp(false)) delay(100);
		
		Serial.print("Every 500ms");
		
		t.extend(500);
	}
	
 