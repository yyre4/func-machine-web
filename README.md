# FUNC MACHINE WEB

**▶ Play it live: https://yyre4.github.io/func-machine-web/** — no sign-in, no
download, just press Play.

The PyGamer FUNC MACHINE v2, ported to a single self-contained HTML page
(no build, no samples, all synthesis live in Web Audio), dressed in a
Windows ME theme (teal desktop, silver windows, taskbar with a working
Start button), and expanded where the web allows more room:

- **Tracks:** 4 → 8, still one generator × one engine each, polymeter 1–32 steps.
- **Generators:** the original 5 (EUCLID / PROB / AUTOMATA / WALK / FUNC) plus
  TURING (probabilistic loop that forgets itself), MARKOV (interval-chain
  melody) and LOGISTIC (chaos-map gates/pitch).
- **Engines:** the original 9 × 3 variants, plus DRUM and WAVETABLE. Every
  track now has a full ADSR, lowpass filter with resonance, drive, glide,
  tune, and two engine-specific knobs whose labels change with the engine.
  Delay and Reverb sends are separate per track.
- **Scales:** 12 factory scales plus a custom scale builder (tap the notes).
- **Evolution Lab (the big expansion):** the single EVOLVE knob becomes —
  rate, wildness, check interval, 5 modes (Drift / Jump / Bloom / Decay /
  Orbit), checkboxes for WHAT may evolve (rhythm, pitch, density, length,
  engine, sound knobs, harmony, FX sends), per-track Evolve % and Lock,
  conditional-mutation target (next / random track), a plain-words
  Evolution Log, Undo, Snapshot A/B, and Freeze.
- **Form Director:** the 5 v2 arcs plus SURGE and ORBIT, targets up to
  25 minutes, and a Custom arc editor (add/edit sections, tonic shifts,
  section recall so themes return), with a live section timeline.
- **Master FX:** BPM-synced stereo/ping-pong delay, generated-impulse
  reverb, chorus, drive, master filter, compressor.
- **Export:** record the master bus (WebM download), export every played
  note as a MIDI file, save/load the whole system as JSON, share links
  that carry seed + system in the URL, Web MIDI out on channels 1–8,
  autosave to the browser every 10 s.
- **Ableton / DAW:** Web MIDI out also sends 24 PPQ clock + start/stop.
  On macOS use the built-in IAC Driver as the bridge (Audio MIDI Setup →
  MIDI Studio → IAC Driver → "Device is online"), open this page in
  Chrome/Edge (Safari has no Web MIDI), pick IAC Driver Bus 1 in the
  MIDI out dropdown, and in Ableton's MIDI prefs turn Track on for that
  input — plus Sync if Ableton should follow this page's tempo (then
  enable EXT in Ableton's transport). Give each Ableton track input
  channel 1–8 to match tracks 1–8 here. Turn this page's Master volume
  to 0 if you want it as a silent sequencer brain only.
- **Presets:** the 8 PyGamer factory systems (first 4 tracks are the exact
  factory data incl. seeds; tracks 5–8 are web expansion tracks in the
  same character) plus 4 web-only systems: NEON RAIN, SUBWAY GHOST,
  ORCHARD CIRCUIT, SLOW TELEGRAPH.
- **Step grids are editable:** click a step to force it ON (blue ring),
  force it OFF (red ring), or back to AUTO.

## Verification
Headless test suite (Node, stubbed DOM + Web Audio): seed determinism,
exact Euclidean pattern, CA rule-90 evolution, all 8 generators in range,
in-scale pitch, form-director bar math, 300 mutations staying in bounds,
all 12 presets loading, serialize round-trip, all 11 engines × 3 variants
triggering, transport start/stop, MIDI export — all passing.
NOT yet listened to in a real browser: the first real listen is the real
test, same as the PyGamer builds. Web MIDI needs Chrome/Edge + permission.
Recording downloads WebM (browser-native), not WAV.

## Donations

If you like this and want to support more of it:

- **Bitcoin (BTC):** `bc1qvl6sy99kn9rll3jjzu96vfkmezcfjq6yf58qd9`
- **Ethereum Classic (ETC):** `0x2D4B15760e621af2aC100EC8e39A10D57621E4AC`

(The same addresses are in the donate footer at the bottom of the page,
with copy buttons. The ETC address is the same wallet address previously
listed for Ethereum donations — a 0x address receives on either network;
send ETC on the Ethereum Classic network.)

## Honest limits
One voice per track (a new note cuts the previous one on that track),
like the PyGamer. CHORD plays a real triad in the browser and sends all
three notes' root channel over MIDI as one note per track channel —
MIDI export, however, contains the played root notes per track.
