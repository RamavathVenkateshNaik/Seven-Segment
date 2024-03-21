#include <avr/io.h>

#define XNOR(x, y) (!(x) && !(y) || ((x) && (y)))

int main(void) {
    // Set up inputs and output
    DDRB &= ~(1 << PB0); // Input 1 (connected to PB0)
    DDRB &= ~(1 << PB1); // Input 2 (connected to PB1)
    DDRB |= (1 << PB2);  // Output (connected to PB2)

    // Main loop
    while (1) {
        // Read inputs
        uint8_t input1 = (PINB & (1 << PB0)) >> PB0;
        uint8_t input2 = (PINB & (1 << PB1)) >> PB1;

        // Perform XNOR operation
        uint8_t result = XNOR(input1, input2);

        // Write result to output pin
        if (result)
            PORTB |= (1 << PB2);
        else
            PORTB &= ~(1 << PB2);
    }

    return 0;
}
