# Changelog

## V2.0 — 2026-10 (chords on the waveform, skin integration)
- **Chords scrolling over VirtualDJ's own waveform** (macOS and Windows): a transparent layer on each deck's waveform band, in sync with the track; clicks go through to VirtualDJ. Adjusted once per deck (position, size, scale); it follows window resizing and full screen.
- **Works with its window closed**: the analysis, auto tuning and texts keep running as long as Chord Live is active on the deck.
- **Skin integration**: 7 buttons (`effect_button 'ChordLive' 1..7`) and 24 live texts (`get_effect_string 'ChordLive' 1..24`) — current chord, next 6 chords with their length in beats, beats left, key heard, comparison with VirtualDJ's key, tuning, harmonic match with the other deck, next key change… Full list at the end of the README.

## V1.8 — 2026-10
- **Audio decoded by VirtualDJ itself** (from the original sound, before pitch / key / Master Tempo): every format VirtualDJ plays, videos included, and faster. Fallback to the file on disk when the track is not playing.
- **→ DB / → tags** buttons, right under the key: write the detected key into VirtualDJ's database or also into the file's tag, done by VirtualDJ itself; green when confirmed, red if not.
- **all to 0** button (tempo and key back to the original, auto tuning kept); **pitch 0** and **all to 0** flash green when clicked.
- Interface in English; the analysis summary line is gone (only progress and errors are shown).

## V1.7 — 2026-10 (minor keys)
- **Dominant chord in minor keys**: when the leading tone is heard, the V chord is shown major as it is played (E / E7 in A minor, not Em).

## V1.6 — 2026-10 (better chord detection)
- **Repetitions**: a chorus or verse that comes back several times is analysed together with all its repetitions, so it gets the same, more reliable chords every time.
- **Key changes that go up** (a semitone or a tone near the end of the song): detected, chords favoured in the new key, and the key shown in the window follows the song.
- **Chromatic inner lines** (Cm → Cm/B → Cm7/Bb → Am7b5, even when the line is not in the bass).
- **Clear bass outside the chord**: when the melody hides the chord, the bass decides (Fm7 over a G bass → Eb/G).
- macOS: signed and notarised **.pkg installer**.

## V1.4 — 2026-10 (first version of Chord Live)
- Live analysis of the loaded track: chords aligned on VirtualDJ's beat grid, key, fine tuning (A = 440 Hz).
- Scrolling chord window (macOS and Windows): current chord in big letters, next chords scrolling under a playhead, beat marks, zoom, 7 colours, follows the deck's transposition.
- **Auto tuning** (`key_smooth`): the track is brought to A = 440 Hz, tempo unchanged, keeping your own transposition (whole semitones).
- **pitch 0** button: resets the pitch fader (tempo), key untouched.
- The **original audio file is read from disk**: pitch, transposition and Master Tempo never affect the analysis. MP3, AAC/M4A, ALAC, AIFF, WAV, FLAC, Ogg Vorbis, audio of MP4/MOV/M4V videos (Windows: also WMA/WMV); other formats (MKV, WEBM, AVI, APE, MPC…) through ffmpeg if installed.
- Beat grid from the VirtualDJ database (read only) or from the track's original BPM; waits for VirtualDJ's BPM on tracks it has never analysed.
- Nothing is written to the VirtualDJ database or to your files.
