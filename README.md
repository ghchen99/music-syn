# Embedded Systems Coursework Project

This coursework assignment focuses on the development of a musical keyboard using a microcontroller module, with a specific focus on embedded systems and real-time systems. The project involves creating a keyboard that has various inputs, including 12 keys, 4 control knobs, and a joystick. It also features audio output through two channels and displays information on an OLED display.

## Introduction
The objective of this coursework assignment is to design and implement an embedded system for a musical keyboard using a microcontroller module. The project involves various aspects of embedded systems, including input reading, display output, sound generation, and system optimization.

## Functionality
The completed coursework project encompasses the following functionality:

- Reading inputs from 12 keys, 4 control knobs, and a joystick using a key matrix.
- Displaying input values on an OLED display.
- Generating sound using a sawtooth wave based on the pressed keys.
- Implementing thread-safe data sharing using a mutex and queue.
- Decoding knob rotations to implement volume control.
- Relaying key presses and releases to another keyboard module through a UART connection.
- Measuring the execution time of a task.

## Part 1: Real-Time Systems
The first part of the coursework project focuses on real-time systems and covers the following key areas:

### Key and Knob Input
- Implementing a key matrix to read input values from the 12 keys and 4 control knobs.
- Creating a function to read the input values and display them on the OLED display.
- Defining the microcontroller pin assignments for various components.

### Display Output
- Utilizing the OLED display to show the input values obtained from the key matrix.

### Sound Generation
- Generating sound using a sawtooth wave based on the pressed keys.
- Introducing the concept of a phase accumulator and defining an array of phase step sizes for each note.
- Implementing a main loop to check the state of each key and select the corresponding step size.
- Utilizing an interrupt service routine to update the phase accumulator and generate the output waveform.
- Employing a timer to trigger the interrupt and ensuring the accuracy of sound generation.

## Part 2: Real-Time Systems
The second part of the coursework project builds upon the first part and extends the functionality of the system. This part focuses on the following areas:

### Thread-Safe Data Sharing
- Introducing a mutex to address synchronization issues with the shared variable "keyArray."
- Creating a global handle for a FreeRTOS mutex and initializing it in the setup function.
- Using the mutex to protect accesses to the "keyArray" in the relevant tasks.

### Knob Decoding and Volume Control
- Implementing knob decoding to detect the rotation and direction of rotation based on the state changes of the A and B signals.
- Comparing the state changes to a state transition table to determine the rotation.
- Implementing knob decoding for knob 3 and updating the rotation variable accordingly.
- Displaying the rotation value on the screen.
- Implementing a simple volume control based on the knob rotation and applying a log taper to the output value.
- Testing the volume control by observing the perceived loudness changes.

### Communication Between Keyboard Modules
- Establishing communication between keyboard modules using a UART (serial) connection.
- Defining a simple message format to relay key presses and releases.
- Comparing the state of each key to the previous state and configuring the corresponding message if a key has changed state.
- Placing the messages in a queue for transmission.
- Implementing a task, "msgOutTask()," to retrieve messages from the queue and send them over the serial port.
Enabling the system to receive messages and play the appropriate notes.

## Conclusion
The embedded systems coursework project provides hands-on experience in developing a musical keyboard using a microcontroller module. It covers various aspects of embedded systems, including input reading, display output, sound generation, and system optimization. 
