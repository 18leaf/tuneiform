# Tuneiform
I want to make the coolest (aesthetically) tuner app that exists. I want to visualize the harmonic series and show the phase differences between a perfectly in-tune note being played.

## Goals
- Detect Note frequency
- Match frequency to some note scale (A = 440hz configurable, configurable temperaments (and different scale lengths, 1:1, 2:1 octave required though))
- Use Fast-Fourier Analysis to obtain frequencies of top-k peaks
- visualize top-k peak differences from expected note freq vs actual note freq
- plot this difference in real-time, such that a perfect match (with some configurable delta ie sensitivity (higher sense = more perfect to lock in)) "locks in"

## Notes
- **Temperament** - Configure the root note.. ie A = 440hz. Specify Interval/Ratio/Cents ... Either Cents or Ratio.. Cents = 100 logarithmic... sometimes ratio is easier ie 1:1, 9:8. etc.. (maybe allow fractional notation as well).. cents need decimal accuracy, as well. Convert a temperament (init with root note + (ratio or cents (must have 1:1, octave and combination of in between notes (man allowed)))). Specify interval from 1:1, a:b, c:d, ... and last 2:1. Where there can be as many ratios between as wanted, but for constrain to a length of 8 -> throw unsupported error.
- **Note Classification** - Notes Range from A-G .. Supported Symbols = ♭ ♯ ♮ 𝄫 𝄪 .. Maybe more in future.. I will only worry about flat/sharp/natural for now and assume 8 note length scale for simplicity.. Future support on backlog
- **Visualization** - the ratio of intonation frequency against root note (only works if assumption = NOT equal temperament AND root note is updated to the current scale being played.. IE fancy temperament root note @ A = 440hz would set a B to be not the same B as equal temperament.. messing up raito detection if playing in scale of B) (only works if assumption = NOT equal temperament AND root note is updated to the current scale being played.. IE fancy temperament root note @ A = 440hz would set a B to be not the same B as equal temperament.. messing up raito detection if playing in scale of B.. since cycle occurs on A... NOT B) could be what is represented.. against the root note..1

## Diagram
![Diagram](https://github.com/18leaf/tuneiform/blob/main/ROUGHDRAFTDIAGRAM.png?raw=true)
