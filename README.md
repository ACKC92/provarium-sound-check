# Provarium sound timing check

A one-page test for [Provarium](https://provarium.net)'s player. It plays short test sounds the way Provarium plays rehearsal recordings and measures, on the phone itself, when each sound is really heard. It was made to look into the metronome and the recording drifting apart on iPhones.

**Open it:** https://ackc92.github.io/provarium-sound-check/

## What it measures
- A recording played on its own (as Provarium's Hazır Kayıt): how long it takes to start, how its clock moves.
- Four recordings through the browser's sound processing (as Ayrık Partiler, MuseScore and MusicXML), in WAV and MP3:
  - how late each is heard after its own clock says,
  - how far apart the four are,
  - gaps in the sound,
  - what happens when one is put back in step while playing,
  - the same at speed 0.75.
- The extra test: what the timers, the screen and the sound do while another app is in front.

## Privacy
Nothing is sent anywhere. The page has no analytics and makes no network requests after it loads. The results stay on the screen until the person taps Copy or Share. They hold the browser's own description (its version and the phone's system version), the model and headphones the person types or picks, and the timings.

## Files
- `index.html`: the page.
- `lame.min.js`: [lamejs](https://github.com/zhuker/lamejs) 1.2.1, to make the MP3 test sound. LGPL-3.0, a port of [LAME](https://lame.sourceforge.io). See `LICENSE-lamejs.txt` and `LICENSE-LGPL-3.0.txt`.
