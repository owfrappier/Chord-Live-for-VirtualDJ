# Changelog

## V1.4 — 2026-10 (first version of Chord Live)
- Live analysis of the loaded track: chords aligned on VirtualDJ's beat grid, key, fine tuning (A = 440 Hz).
- Scrolling chord window (macOS and Windows): current chord in big letters, next chords scrolling under a playhead, beat marks, zoom, 7 colours, follows the deck's transposition.
- **Auto tuning** (`key_smooth`): the track is brought to A = 440 Hz, tempo unchanged, keeping your own transposition (whole semitones).
- **pitch 0** button: resets the pitch fader (tempo), key untouched.
- The **original audio file is read from disk**: pitch, transposition and Master Tempo never affect the analysis. MP3, AAC/M4A, ALAC, AIFF, WAV, FLAC, Ogg Vorbis, audio of MP4/MOV/M4V videos (Windows: also WMA/WMV); other formats (MKV, WEBM, AVI, APE, MPC…) through ffmpeg if installed.
- Beat grid from the VirtualDJ database (read only) or from the track's original BPM; waits for VirtualDJ's BPM on tracks it has never analysed.
- Nothing is written to the VirtualDJ database or to your files.
