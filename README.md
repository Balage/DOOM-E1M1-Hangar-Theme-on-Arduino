# DOOM-E1M1-Hangar-Theme-on-Arduino
This is a short section of "At Doom's Gate", also known as the "E1M1 Hangar Theme". It is the very same tune used in the 2016 reboot for the Doomguy collectible action figures when you pick them up.

[![Watch the video](https://img.youtube.com/vi/d0HR-99TC7g/maxresdefault.jpg)](https://youtu.be/d0HR-99TC7g)

The full article is [available here](https://vbstudio.hu/blog/20190330-Playing-DOOM-on-an-Arduino).

## Playing a Tone with Arduino
The Arduino library has a [built in method](https://www.arduino.cc/reference/en/language/functions/advanced-io/tone/) for generating a specific frequency using a PWM square wave. This means the sound will not be as smooth as a perfect sine wave, but that just makes it sound more like an old chiptune. To use actual notes, I made a lookup table for the frequencies using the [tempered scale](https://en.wikipedia.org/wiki/Equal_temperament), having 8 octaves.

The tone() function needs two input parameters: the I/O pin for the speaker, and a frequency. The playback itself works concurrently and goes on indefinitely, until a noTone() call is issued. In this specific implementation the execution is halted until a note is over.

This solution can only produce monophonic tunes. Because the fast parts in the original song are polyphonic, I had to recompose them to sound as close to the original as possible.

## How to install code
- Download and install the [Arduino IDE](https://www.arduino.cc/en/software).
- The Arduino IDE by default stores all Sketches in a folder named **"Arduino"** in your **Documents** folder.
- Download the repository and copy the entire **"DoomHangarTheme"** folder to there.
- Start the Arduino IDE and select **"File"**, **"Sketches"**, and then choose **"DoomHangarTheme"** from the list.

## Improvements
On the video I'm actually using the toneAC() function instead, which can provide twice the volume by alternating the polarity. It's not part of the Arduino core library, but you can [check it out here](https://playground.arduino.cc/Code/ToneAC).

## License
MIT