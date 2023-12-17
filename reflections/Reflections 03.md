06.10.2023
Thinking about data structures for generative game music.
Attempting to make everything modular.

Nomenclature
- How to create a logical division between different function groups?
layer_layerNo_functionGroupType_functionGroupTypeNo

Layer
Function groups
- Can contain several other functions
- Can contain other function groups
- Examples: sound layer, rhythm module within a sound layer

Data structure
I have started to work out a data structure to host the configuration data for the music generator setup. Types of data that need to be stored:
- Notes: MIDI note number, velocity, other parameters?
- Sound parameters: Configurations for the various sound generator modules
- Module parameters: Configurations of all other modules

It's important that the structure is stabilized early on, to maintain I propose for every module to use a float array for data input that is pre-allocated as a variable. A float variable is 4 kb in C++. For example: Using an array of length 256 would require a mere 1024 kb in RAM, so we can actually store a lot of data 

I realized that MetaSound is not good for generating data, due to various limitations in how variables (e.g., float arrays) are accessed. This becomes especially apparent when trying more complex rhythmic and melodic approaches (e.g., polyphony).
I have identified two possible approaches to tackle this:
1. Create logic for reading/writing float data array variables within MetaSound.
2. Use float data arrays in MetaSound but move all data generation to a separate blueprint.
Approach 1 will still require the creation of some interface to exchange data with the outside world. Approach 2 is also an opportunity to divide the music system into several, less complex components.