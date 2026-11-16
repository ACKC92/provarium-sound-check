# Provarium sound timing check

A one-page test for [Provarium](https://provarium.net)'s player. It plays short test sounds the way Provarium plays rehearsal recordings and measures, on the device itself, when each sound is really heard. It was made to look into the metronome and the recording drifting apart, first reported on iPhones. It runs on any phone, tablet or computer with a browser: two tests, the second started by the same button once the first is done, and one log at the end.

**Open it:** https://ackc92.github.io/provarium-sound-check/

## What it measures
- A recording played on its own (as Provarium's Hazır Kayıt): how long it takes to start, how its clock moves.
- Four recordings through the browser's sound processing (as Ayrık Partiler, MuseScore and MusicXML), in WAV and MP3:
  - how late each is heard after its own clock says,
  - how far apart the four are,
  - gaps and glitches in the sound,
  - what happens when one is put back in step while playing,
  - the same at speed 0.75.
- Eight MP3 recordings at once, as a piece in eight parts, at the device's own sound rate and again at 44,100 Hz: gaps and glitches.
- One "part and rest" recording (stereo, the part on the left, the others on the right), split and mixed again, at speed 1 and 0.75.
- A player of the page's own: eight parts decoded a few seconds ahead in a worker and mixed by the page, at speed 1 and 0.75 (its own stretching): whether the decoding keeps up, how much of the device it takes, gaps and glitches.
- The second test: the screen locked or another app in front for a few seconds while that player plays. Do the sound, the decoding and the page's timers go on?

## Privacy
Nothing is sent anywhere. The page has no analytics and loads nothing but its own files. The results stay on the screen until the person taps Copy or Share. They hold the browser's own description (its version and the device's system version), the device's model and what it's heard through, as the person types or picks them, and the timings.

## Files
- `index.html`: the page.
- `lame.min.js`: [lamejs](https://github.com/zhuker/lamejs) 1.2.1, to make the MP3 test sounds. LGPL-3.0, a port of [LAME](https://lame.sourceforge.io). See `LICENSE-lamejs.txt` and `LICENSE-LGPL-3.0.txt`.
- `mpg123-decoder.min.js`: [mpg123-decoder](https://www.npmjs.com/package/mpg123-decoder) 1.0.3 from [wasm-audio-decoders](https://github.com/eshaz/wasm-audio-decoders), to decode MP3 for the page's own player. MIT, with [mpg123](https://www.mpg123.de) compiled in, LGPL-2.1. See `LICENSE-mpg123-decoder.txt` and `LICENSE-LGPL-2.1.txt`.
