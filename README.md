# Arduino-GPIO
The Arduino GPIO library has been developed to allow high performance
digital pin access. Most access functions are compiled to a single
instruction and execute in 1-2 clock cycles. The library functions are
more than 10 times faster than the Arduino digital pin functions. In
some cases as much as 60 times faster. Additional support classes are
available for Shift Register Input/Output, and Asychronous Serial
Output. These also demonstrate how the GPIO template class may be used
to construct additional libraries.

```
GPIO<BOARD:D4> pin;  // Construct pin instance.
bool state;

pin.input();         // Set pin to input mode.
pin.input_pullup();  // Set pin to input mode with internal pullup resistor.
pin.output();        // Set pin to output mode.

state = pin.read();  // Read current pin state.
state = pin;         // Shorthand for read.
if (pin) ...         // Use pin as boolean value in conditional expression.
while (!pin) ...     // Await pin state.

pin.write(state);    // Write new pin state.
pin = state;         // Shorthand for write.
pin.high();          // Shorthand for write(HIGH).
pin.low();           // Shorthand for write(LOW).

pin.toggle();        // Toggle pin state.

pin.pulse(width);    // Generate pulse with given width in micro-seconds.

```

## Classes

* [Boards](./src/Board.h)
* [General Purpose Input/Output, GPIO](./src/GPIO.h)
* [Asynchronous Serial Output, ASO](./src/ASO.h)
* [Shift Register Parallel Input, SRPI](./src/SRPI.h)
* [Shift Register Parallel Output, SRPO](./src/SRPO.h)

## Example Sketches

* [Benchmark](./examples/Benchmark)
* [Blink](./examples/Blink)
* [Pulse](./examples/Pulse)
* [ShiftIn](./examples/ShiftIn)
* [ShiftOut](./examples/ShiftOut)
* [SoftwareSerial](./examples/SoftwareSerial)
