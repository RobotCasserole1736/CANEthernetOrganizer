# CAN Ethernet Organizer

<img width="765" height="489" alt="image" src="https://github.com/user-attachments/assets/f6c0bc85-7c23-4923-9acc-24b0a2665dd8" />

## Sources 

[Circuit Board Design](https://easyeda.com/editor#project_id=c0b92af93ce74d5ca46f8dad5e09f08a)

[Case Design](https://cad.onshape.com/documents/a56cdedbed96c5c3cf9e883b/w/beced8c700cd4dec7f4b0609/e/cf17f949576d780bc52e495e?renderMode=0&uiState=68a6605f6cbc22313f9dbde9)

## Quickstart

1. Mount adapters near swerve modules, or other modules
2. Connect a 5v (sensor line) source to one module.
3. Connect CAN source to one end (roboRIO or SystemCore)
4. Connect CAN termination to the other end (usually the PDP)
5. All other TERM and LOOP switches should be off (Loop is unused)
6. Connect all modules with standard RJ45 ethernet

Any 5v supply that is put into the 5/G pins is distributed to all modules. Green lights on the module indicate they are getting power.

Ensure any CAN wires coming off of the organizer and going to a sensor or motor are less than 1 ft in length.

5v max - 12v will cause the LED to burn out.

## Termination

In the Summer 2025 revision of the boards, the loopback and CAN termination was not implemented well. Only one permutation is supported:

At the RIO end of the chain, set the LB_TERM switch to ON
At the far end of the chain, set the LOOPBACK switch to ON

All other switches should be off.

There should _not_ be a PDP or other terminating resistor anywhere in the chain.
