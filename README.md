<h1 align="center">Chord Live for VirtualDJ</h1>
<p align="center"><b>V1.8</b> · VirtualDJ plugin · macOS (Apple Silicon) · Windows (x64)</p>
<p align="center"><a href="https://www.paypal.com/paypalme/owfrappier"><b>☕ DONATE (PayPal)</b></a></p>

<p align="center"><img src="screenshot1" alt="Chord Live — current chord, key, tuning and scrolling chords" width="900"></p>
<p align="center"><img src="screenshot2" alt="Chord Live — yellow colour" width="900"></p>
<p align="center"><img src="screenshot3" alt="Chord Live — yellow colour" width="900"></p>
---

🇬🇧 [English](#english) · 🇫🇷 [Français](#français)

---

## English

**Chord Live** is a free VirtualDJ effect that **analyses the loaded track live** and shows its chords while you play, in its own floating window:

- 🎹 **Chords** aligned on VirtualDJ's beat grid (7ths, maj7, dim/dim7, m7b5, 6th and suspended chords, inversions, chromatic bass lines). The current chord in big letters, the next ones **scrolling** under a vertical playhead, like the waveform.
- 🔑 **Key** of the track, and 🎚️ **fine tuning** measured to the cent against A = 440 Hz.
- ✅ **Auto tuning**: the track is brought to A = 440 Hz with `key_smooth` — **the tempo does not change**, with or without Master Tempo, and **your own transposition is kept** (deck at +2 → stays +2, in tune).
- **pitch 0** (tempo back to the original) and **all to 0** (tempo and key back to the original, auto tuning kept) buttons, **zoom** (− / +), **7 colours**, follows the deck's transposition.
- **→ DB / → tags** (right under the key): write the detected key into VirtualDJ's database, or also into the audio file's tag. VirtualDJ itself does the writing (safe, even while it is running), only when you click; the button turns green once VirtualDJ shows the new key.
- **Nothing is written** to your VirtualDJ database or to your files unless you click → DB / → tags. The audio is decoded by **VirtualDJ itself** (every format it can play, videos included), from the original sound before pitch, key and Master Tempo, while the track plays. If the track is not playing, Chord Live reads the original file from disk instead (MP3, AAC/M4A, ALAC, AIFF, WAV, FLAC, Ogg Vorbis, MP4/MOV/M4V audio; Windows also WMA/WMV; other formats if [ffmpeg](https://ffmpeg.org) is installed).

It uses the analysis engine of [Chord Injector for VirtualDJ](https://github.com/owfrappier/Chord-Injector-for-VirtualDJ), which writes chords, tuning and key into the VirtualDJ database for a whole library.

### Install (VirtualDJ closed)

Download the latest version in **[Releases](https://github.com/owfrappier/VIRTUALDJ-CHORDS-PLUGIN/releases/latest)**.

- **macOS (Apple Silicon)**: open `Chord-Live-for-VirtualDJ-…-macOS.pkg` (signed and notarised by Apple) and follow the installer. It installs `ChordLive.bundle` in
  `~/Library/Application Support/VirtualDJ/PluginsMacArm/SoundEffect/` for the logged-in user.
- **Windows**: copy `ChordLive.dll` to
  `%LOCALAPPDATA%\VirtualDJ\Plugins64\SoundEffect\`
  (Windows + R, paste the path; create `SoundEffect` if it does not exist — not in `Visualisation`).
  Older installations may use `Documents\VirtualDJ\Plugins64\SoundEffect\`.

Start VirtualDJ, choose **Chord Live** in the effects of a deck and open its window. The analysis takes a few seconds per track.

💡 **One-click button**: in your skin, edit a custom button (right-click → Edit) and give it the action
`effect_active 'ChordLive' & effect_active 'ChordLive' ? effect_show_gui 'ChordLive' : nothing`
— one click turns Chord Live on for the deck and opens its window, a second click turns it off.

---

## Français

**Chord Live** est un effet VirtualDJ gratuit qui **analyse en direct le morceau chargé** et affiche ses accords pendant que vous jouez, dans sa propre fenêtre flottante :

- 🎹 **Les accords** calés sur la grille de beats de VirtualDJ (7e, maj7, dim/dim7, m7b5, 6te et sus, renversements, lignes de basse chromatiques). L'accord en cours en grand, les suivants qui **défilent** sous une tête de lecture verticale, comme la forme d'onde.
- 🔑 **La tonalité**, et 🎚️ **l'écart de diapason** mesuré au cent près par rapport au La 440.
- ✅ **Auto tuning** (diapason auto) : le morceau est ramené à La = 440 Hz avec `key_smooth` — **le tempo ne change pas**, avec ou sans Master Tempo, et **votre transposition est conservée** (platine à +2 → reste à +2, juste).
- Boutons **pitch 0** (tempo d'origine) et **all to 0** (tempo et tonalité d'origine, diapason auto conservé), **zoom** (− / +), **7 couleurs**, suit la transposition de la platine.
- **→ DB / → tags** (juste sous la tonalité) : écrit la tonalité trouvée dans la base de VirtualDJ, ou aussi dans le tag du fichier audio. C'est VirtualDJ lui-même qui écrit (sans risque, même pendant qu'il tourne), seulement sur clic ; le bouton passe au vert quand VirtualDJ affiche la nouvelle tonalité.
- **Rien n'est écrit** dans votre base VirtualDJ ni dans vos fichiers, sauf si vous cliquez sur → DB / → tags. L'audio est décodé par **VirtualDJ lui-même** (tous les formats qu'il sait lire, vidéos comprises), sur le son original avant pitch, tonalité et Master Tempo, pendant la lecture du morceau. Si le morceau ne joue pas, Chord Live lit le fichier original sur le disque (MP3, AAC/M4A, ALAC, AIFF, WAV, FLAC, Ogg Vorbis, audio des MP4/MOV/M4V ; sous Windows aussi WMA/WMV ; autres formats si [ffmpeg](https://ffmpeg.org) est installé).

Il utilise le moteur d'analyse de [Chord Injector for VirtualDJ](https://github.com/owfrappier/Chord-Injector-for-VirtualDJ), qui écrit accords, diapason et tonalité dans la base VirtualDJ pour toute une bibliothèque.

### Installation (VirtualDJ fermé)

Dernière version dans **[Releases](https://github.com/owfrappier/VIRTUALDJ-CHORDS-PLUGIN/releases/latest)**.

- **macOS (Apple Silicon)** : ouvrez `Chord-Live-for-VirtualDJ-…-macOS.pkg` (signé et notarisé par Apple) et suivez l'installeur. Il installe `ChordLive.bundle` dans
  `~/Library/Application Support/VirtualDJ/PluginsMacArm/SoundEffect/` pour l'utilisateur connecté.
- **Windows** : copiez `ChordLive.dll` dans
  `%LOCALAPPDATA%\VirtualDJ\Plugins64\SoundEffect\`
  (Windows + R, collez le chemin ; créez `SoundEffect` s'il n'existe pas — pas dans `Visualisation`).
  Sur une ancienne installation : `Documents\VirtualDJ\Plugins64\SoundEffect\`.

Lancez VirtualDJ, choisissez **Chord Live** dans les effets d'une platine et ouvrez sa fenêtre. L'analyse prend quelques secondes par morceau.

💡 **Bouton en un clic** : dans votre skin, modifiez un custom button (clic droit → Edit) et donnez-lui l'action
`effect_active 'ChordLive' & effect_active 'ChordLive' ? effect_show_gui 'ChordLive' : nothing`
— un clic active Chord Live sur la platine et ouvre sa fenêtre, un second clic le coupe.

---

© Olivier FRAPPIER 2026 · [DONATE](https://www.paypal.com/paypalme/owfrappier)

*Chord Live for VirtualDJ is a free initiative by a VirtualDJ fan. It is an independent product and is not affiliated with, endorsed by or sponsored by VirtualDJ or Atomix Productions. VirtualDJ is a trademark of Atomix Productions.*

*Idea, design, testing and direction: Olivier Frappier. The C++ code was written with the help of Claude (Anthropic's AI assistant), following his ideas and under his direction. · Idée, conception, tests et direction : Olivier Frappier. Le code C++ a été écrit avec l'aide de Claude (l'assistant IA d'Anthropic), sur ses idées et sous sa direction.*
