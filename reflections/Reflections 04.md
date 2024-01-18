Thinking about how my first attempt at making a generative music system is still the most musical sounding one.
[generative music sequencer + milkdrop (youtube.com)](https://www.youtube.com/watch?v=I117iYdULho)
Sometimes it feels like the most naive approaches yield the best results.
How can I get back there with what I know now?

Inspired by this question, I created two generator units with MetaSounds that will be useful for laying down some basic sounds. They recreate the sounds used in the above attempt.
- Atonal: Plays a sine wave at a random pitch within a custom range around a chosen note.
- Stretcher: Plays a custom audio sample, stretched to a definable duration.

I went on to build a basic music setup, featuring 3 rhythmic layers, a basic synth voice, Atonal, and Stretcher.

Idea for another sound unit:
A four-note sequence aimed at indicating an emotion. Possibly this approach could also be used to generate 1-4-note chords? Only caveat here is that this might end up being rooted too much in Western music theory and tastes.

Started building a UI for controlling the music system in Unreal. Since adjusting the music parameters by hand in MetaSound is no option in a real-time scenario, it's crucial to have accessible and intuitive controls for setting up and saving generative and sound design parameters.

![[Pasted image 20240118175548.png]]

As evident from the picture above, even with a few elements, the system already looks pretty complex. There are so many elements, each with their own feature sets and technical considerations to be made. For now, I will approach this by developing a set of instruments as artistic practice. Each instrument can work more or less on its own. Input parameters should be minimized to keep things simple.

I'm also considering to return to Unity, since there are two possible solutions for having native music generation without clunky interfaces that may or may not work. Also, wrapping my head around Unreal's blueprint system, creating a GUI with it, as well as implementing gameplay is still far less intuitive (and thus slower) for me than in Unity, where I can draw from almost a decade worth of experience.
The first possibility is Procedural Music Sequencer, which was recently made free. The other one is AudioHelm, which I already own. This one, however, is deprecated, so no developer support to be expected here. But it still runs flawlessly on current versions of Unity. Also, it has a powerful synth engine that is certainly able to produce high quality sounds.