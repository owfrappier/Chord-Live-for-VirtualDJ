# Changelog

## V2.6 — 2026-10 (keyboard settings)
- **Bass notes in orange** on the keyboard (notes under C3).
- **Clickable legend**: show or hide each part of the notes.
- **Notes sensitivity** (− / +, 0–100 %, 50 % = V2.5): display threshold of the notes, applied instantly without a new analysis; also in the effect's settings (*Notes sensitivity*).
- The window title shows the version.

## V2.5 — 2026-10 (piano keyboard, extended chords)
- **Piano keyboard with falling notes** in the Chord Live window (macOS and Windows): taller window → 88-key keyboard under the chords, the notes heard in the track fall onto it and light their keys as they sound (same zoom as the chords, follows the deck's transposition). Notes are read on the unwhitened spectrum, without the low notes' overtones and the hammer noise.
- **m9 and aug(#11)** on calm tracks (Dm9, Gaug(#11)), read from the notes actually played: the analysis no longer loses a played note surrounded by louder ones (the B of Gaug(#11)).

## V2.4.1 — 2026-10 (chords on the waveform from the first track)
- **Fix — videos**: playing a video no longer moves the waveform chords away from the waveform (VirtualDJ's video window was sometimes taken for its main window).
- **Chord Live AutoStart** (new companion plugin, macOS and Windows): turns Chord Live and its waveform chords on for each deck the first time a track is loaded — no click needed. Turned off on a deck, it stays off until VirtualDJ restarts.
- **Waveform chords on by default** whenever Chord Live is turned on; the layer uses its default position (no adjustment screen popping up), and an invalid saved position is ignored.
- **No more manual adjustment of the waveform layer** (no *drag to move* / OK screen): it always places itself at its default position. Parameter button 7 is kept for skins but has no effect.
- **Windows installer** (`Setup.exe`): installs Chord Live and Chord Live AutoStart in the right VirtualDJ folders, with an uninstaller in Windows Settings. The macOS `.pkg` installs both too.
- **Chord Live Pro skin included** in both installers: **CHORD WINDOW** (opens / closes the window) and **CHORD WAVE** (waveform chords) on each deck.

## V2.3 — 2026-10 (chords in time, to the end of the track)
- **No more drift**: the chord grid (window, waveform, skin texts) follows the same clock as the analysed audio. Before, it was right at the start of a track and fell slightly behind as the track went on.
- **Smoother, on-time scrolling**: between two position updates from VirtualDJ the display keeps moving at the measured speed instead of being pulled back to an old position (it was sometimes a little late).
- **macOS — chords stay on the waveform when another app has the focus**: the layer moves just above VirtualDJ's window instead of disappearing (it never covers the other app).

## V2.2.1 — 2026-10 (fix + piano ostinatos)
- **Playback started right after loading**: chords now go to the end of the track (before, the part VirtualDJ had not decoded yet was taken for the end or for silence — no chords after the beginning until you went back to the start).
- **Neighbour notes over a held chord** (piano ostinato D → G, D → E, D → F): Dsus4 / Dsus2 / Dm beat by beat, only when the pattern repeats bar after bar.
- **Left hand climbing over a pedal** (D–A → D–Bb): the chord of the 4th is shown (Gm, Gm(add9)), then the dominant (A) before falling back.

## V2.2 — 2026-10 (the third you hear)
- **Third heard over the key**: a chord is major or minor according to the third actually played, not to the key's scale (G after D in a minor song when B natural is played). A minor 7th chord without a heard third becomes a dominant 7th (G7, not Gm7).
- **Doubtful third → power chord**: when neither third is really heard, the chord is shown without it (**A5**) instead of guessing.
- **Phantom major third**: the overtone of a low bass note (D2 → F#4) is no longer taken for a played major third; a weak but real minor third wins (Dm instead of D, minor key found). A root played alone in a minor song is shown as **D5**.
- **Piano arpeggios** (calm tracks without drums): chords read from the notes attacked, bar by bar (Absus4, C#m7/B…).
- **First chord** starting just before the first beat is kept.
- **Streaming tracks** (Tidal, Deezer…): the whole track is captured; the end of the download is no longer taken for the end of the track.

## V2.1 — 2026-10 (better chords on tracks with drums)
- **Bass heard through the kick drum**: on tracks with drums, the kick is filtered out of the low end before the analysis, so the bass line is followed better: right chord roots and inversions instead of a chord read from its third (Bbm7 instead of Db, Abmaj7 instead of Cm). Only on tracks with a real kick drum; acoustic tracks (piano, strings, songs) are analysed exactly as before.
- **Half-diminished chords from the bass**: a minor chord over the 6th / major chord over the #4 is shown as the half-diminished chord of the bass (G#m7b5) when the key confirms it; a maj7 without its root over its 7th becomes the diminished chord of the bass (D#m7b5).

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
