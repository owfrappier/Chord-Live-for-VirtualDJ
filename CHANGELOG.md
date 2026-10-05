# Changelog

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
