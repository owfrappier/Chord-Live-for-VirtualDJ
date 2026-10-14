





<h1 align="center">Chord Live for VirtualDJ</h1>
<p align="center"><b>V2.4.1</b> · VirtualDJ plugin · macOS (Apple Silicon) · Windows (x64)</p>
<p align="center"><a href="https://www.paypal.com/paypalme/owfrappier"><b>☕ DONATE (PayPal)</b></a></p>



https://github.com/user-attachments/assets/30cf052c-5642-44df-9578-b5d9365c8533




<p align="center"><img src="screenshot11.png" alt="Chord Live — current chord, key, tuning and scrolling chords" width="900"></p>
<p align="center"><img src="screenshot12.png" alt="Chord Live — yellow colour" width="900"></p>
<p align="center"><img src="screenshot13.png" alt="Chord Live — yellow colour" width="900"></p>
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
- ▶️ **New in V2.4 — chords on the waveform as soon as a track is loaded**: the small companion plugin *Chord Live AutoStart* turns Chord Live and its waveform chords on for each deck the first time a track is loaded — no click needed (turn it off on a deck and it stays off). The waveform layer uses its default position, with no adjustment screen, and stays on the waveform when a video is played (V2.4.1).
- ⏱️ **New in V2.3 — chords in time to the end of the track**: the chord grid follows the same clock as the analysed audio (no more drift towards the end), scrolls smoothly, and on macOS stays on VirtualDJ's waveform when another app has the focus.
- 🎼 **New in V2.2 — the third you hear**: a chord is shown major or minor from the third actually played, not from the key (G in a minor song when B natural is played). When the third is doubtful, the chord is shown without it (**A5**). A low bass note's overtone is no longer taken for a major third (Dm instead of D, right minor key). **Piano arpeggios** and **ostinatos** (Dsus4 / Dsus2 / Dm, a left hand climbing to Gm) are read note by note, and chords now go to the end of the track even when playback starts right after loading (streaming tracks included).
- 🥁 **New in V2.1 — better chords on tracks with drums**: the kick drum is filtered out of the low end before the analysis, so the bass line — and the right chord root and inversion — comes through. Acoustic tracks are analysed as before. Half-diminished chords (m7b5) are also recognised from the bass.
- 🌊 **New in V2.0 — chords scrolling over VirtualDJ's own waveform**, in sync with the track, on each deck (macOS and Windows). On by default (`effect_button 'ChordLive' 6` turns it on / off); the layer places itself on the deck's waveform band of the VirtualDJ Pro layout and follows window resizing and full screen.
- 🧩 **New in V2.0 — skin integration**: every function and live text (current chord, next 6 chords, beats left, key, tuning, harmonic match with the other deck…) is available to skins and controllers — see [Skin integration](#skin-integration-v20--intégration-dans-un-skin) below. Chord Live keeps working with its window closed.
- **Nothing is written** to your VirtualDJ database or to your files unless you click → DB / → tags. The audio is decoded by **VirtualDJ itself** (every format it can play, videos included), from the original sound before pitch, key and Master Tempo, while the track plays. If the track is not playing, Chord Live reads the original file from disk instead (MP3, AAC/M4A, ALAC, AIFF, WAV, FLAC, Ogg Vorbis, MP4/MOV/M4V audio; Windows also WMA/WMV; other formats if [ffmpeg](https://ffmpeg.org) is installed).

It uses the analysis engine of [Chord Injector for VirtualDJ](https://github.com/owfrappier/Chord-Injector-for-VirtualDJ), which writes chords, tuning and key into the VirtualDJ database for a whole library.

### Install (VirtualDJ closed)

Download the latest version in **[Releases](https://github.com/owfrappier/VIRTUALDJ-CHORDS-PLUGIN/releases/latest)**.

- **macOS (Apple Silicon)**: open `Chord-Live-for-VirtualDJ-…-macOS.pkg` (signed and notarised by Apple) and follow the installer. It installs `ChordLive.bundle` in
  `~/Library/Application Support/VirtualDJ/PluginsMacArm/SoundEffect/` and `ChordLiveAutoStart.bundle` in
  `~/Library/Application Support/VirtualDJ/PluginsMacArm/AutoStart/` for the logged-in user, and the **Chord Live Pro** skin in
  `~/Library/Application Support/VirtualDJ/Skins/`.
- **Windows (x64)**: open `Chord-Live-for-VirtualDJ-…-Windows-Setup.exe` and follow the installer. It installs `ChordLive.dll` in
  `Plugins64\SoundEffect\` and `ChordLiveAutoStart.dll` in `Plugins64\AutoStart\` and the **Chord Live Pro** skin in `Skins\` of your VirtualDJ folder
  (`%LOCALAPPDATA%\VirtualDJ\`, or `Documents\VirtualDJ\` on older installations), and can be removed from Windows Settings → Apps.
  The installer is not code-signed: if Windows shows *Windows protected your PC*, click **More info** → **Run anyway**.
  *Manual install*: copy the two DLLs and `Chord Live Pro.zip` to those folders yourself.
- Then, in VirtualDJ, choose the **Chord Live Pro** skin (Settings → Interface): its **CHORD WINDOW** button opens / closes the Chord Live window, **CHORD WAVE** turns the waveform chords on / off.
  *Optional*: without `ChordLiveAutoStart`, turn Chord Live on yourself in a deck's effects.

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
- ▶️ **Nouveau en V2.4 — les accords sur la forme d'onde dès le chargement d'un morceau** : le petit plugin compagnon *Chord Live AutoStart* allume Chord Live et ses accords sur la forme d'onde sur chaque platine dès le premier morceau chargé — sans clic (si vous le coupez sur une platine, il reste coupé). Le calque prend sa position par défaut, sans écran de réglage, et reste sur la forme d'onde quand une vidéo est lue (V2.4.1).
- ⏱️ **Nouveau en V2.3 — des accords à l'heure jusqu'à la fin du morceau** : la grille d'accords suit la même horloge que l'audio analysé (plus de dérive vers la fin), défile sans à-coups et, sur macOS, reste sur la forme d'onde de VirtualDJ quand une autre application a le focus.
- 🎼 **Nouveau en V2.2 — la tierce qu'on entend** : un accord est affiché majeur ou mineur d'après la tierce vraiment jouée, pas d'après la tonalité (G dans un morceau mineur quand le si naturel est joué). Quand la tierce est douteuse, l'accord est affiché sans elle (**A5**). L'harmonique d'une basse grave n'est plus prise pour une tierce majeure (Dm au lieu de D, bonne tonalité mineure). Les **arpèges** et **ostinatos de piano** (Dsus4 / Dsus2 / Dm, main gauche qui monte vers Gm) sont lus note par note, et les accords vont jusqu'au bout du morceau même quand la lecture est lancée tout de suite après le chargement (streaming compris).
- 🥁 **Nouveau en V2.1 — accords plus justes sur les morceaux avec batterie** : la grosse caisse est filtrée dans le grave avant l'analyse, la ligne de basse — et donc la bonne fondamentale et le bon renversement — ressort. Les morceaux acoustiques sont analysés comme avant. Les accords demi-diminués (m7b5) sont aussi reconnus d'après la basse.
- 🌊 **Nouveau en V2.0 — les accords défilent sur la forme d'onde de VirtualDJ**, en synchro avec le morceau, sur chaque platine (macOS et Windows). Allumées par défaut (`effect_button 'ChordLive' 6` les allume / coupe) ; le calque se place tout seul sur la bande de la forme d'onde de la disposition Pro de VirtualDJ et suit le redimensionnement et le plein écran.
- 🧩 **Nouveau en V2.0 — intégration dans les skins** : toutes les fonctions et les textes en direct (accord en cours, 6 suivants, temps restants, tonalité, diapason, compatibilité avec l'autre platine…) sont disponibles pour les skins et les contrôleurs — voir [Intégration dans un skin](#skin-integration-v20--intégration-dans-un-skin) plus bas. Chord Live fonctionne aussi fenêtre fermée.
- **Rien n'est écrit** dans votre base VirtualDJ ni dans vos fichiers, sauf si vous cliquez sur → DB / → tags. L'audio est décodé par **VirtualDJ lui-même** (tous les formats qu'il sait lire, vidéos comprises), sur le son original avant pitch, tonalité et Master Tempo, pendant la lecture du morceau. Si le morceau ne joue pas, Chord Live lit le fichier original sur le disque (MP3, AAC/M4A, ALAC, AIFF, WAV, FLAC, Ogg Vorbis, audio des MP4/MOV/M4V ; sous Windows aussi WMA/WMV ; autres formats si [ffmpeg](https://ffmpeg.org) est installé).

Il utilise le moteur d'analyse de [Chord Injector for VirtualDJ](https://github.com/owfrappier/Chord-Injector-for-VirtualDJ), qui écrit accords, diapason et tonalité dans la base VirtualDJ pour toute une bibliothèque.

### Installation (VirtualDJ fermé)

Dernière version dans **[Releases](https://github.com/owfrappier/VIRTUALDJ-CHORDS-PLUGIN/releases/latest)**.

- **macOS (Apple Silicon)** : ouvrez `Chord-Live-for-VirtualDJ-…-macOS.pkg` (signé et notarisé par Apple) et suivez l'installeur. Il installe `ChordLive.bundle` dans
  `~/Library/Application Support/VirtualDJ/PluginsMacArm/SoundEffect/` et `ChordLiveAutoStart.bundle` dans
  `~/Library/Application Support/VirtualDJ/PluginsMacArm/AutoStart/` pour l'utilisateur connecté, et le skin **Chord Live Pro** dans
  `~/Library/Application Support/VirtualDJ/Skins/`.
- **Windows (x64)** : ouvrez `Chord-Live-for-VirtualDJ-…-Windows-Setup.exe` et suivez l'installeur. Il installe `ChordLive.dll` dans
  `Plugins64\SoundEffect\` et `ChordLiveAutoStart.dll` dans `Plugins64\AutoStart\` et le skin **Chord Live Pro** dans `Skins\` de votre dossier VirtualDJ
  (`%LOCALAPPDATA%\VirtualDJ\`, ou `Documents\VirtualDJ\` sur une ancienne installation), et se désinstalle depuis Paramètres Windows → Applications.
  L'installeur n'est pas signé : si Windows affiche *Windows a protégé votre ordinateur*, cliquez sur **Informations complémentaires** → **Exécuter quand même**.
  *Installation manuelle* : copiez vous-même les deux DLL et `Chord Live Pro.zip` dans ces dossiers.
- Ensuite, dans VirtualDJ, choisissez le skin **Chord Live Pro** (Paramètres → Interface) : son bouton **CHORD WINDOW** ouvre / ferme la fenêtre Chord Live, **CHORD WAVE** allume / coupe les accords sur la forme d'onde.
  *Facultatif* : sans `ChordLiveAutoStart`, allumez vous-même Chord Live dans les effets d'une platine.

Lancez VirtualDJ, choisissez **Chord Live** dans les effets d'une platine et ouvrez sa fenêtre. L'analyse prend quelques secondes par morceau.

💡 **Bouton en un clic** : dans votre skin, modifiez un custom button (clic droit → Edit) et donnez-lui l'action
`effect_active 'ChordLive' & effect_active 'ChordLive' ? effect_show_gui 'ChordLive' : nothing`
— un clic active Chord Live sur la platine et ouvre sa fenêtre, un second clic le coupe.

---

## Skin integration (V2.0+) · Intégration dans un skin

Every Chord Live function can be used from **any skin, custom button or controller mapping**, with VDJScript. Commands act on the deck they are placed in (`<deck deck="1">` in a skin, or prefix them with `deck 1 …`). Chord Live must be active on that deck: it analyses the track and updates its texts about 10 times per second, with or without its window.
*Toutes les fonctions de Chord Live sont utilisables depuis **n'importe quel skin, custom button ou mapping de contrôleur**, en VDJScript. Les commandes agissent sur la platine où elles sont placées (`<deck deck="1">` dans un skin, ou préfixe `deck 1 …`). Chord Live doit être actif sur cette platine.*

### Activate and show · Activer et afficher
| Command | Action |
|---|---|
| `effect_active 'ChordLive'` | Turn Chord Live on / off on the deck (also a query: lit when active) · *active / coupe* |
| `effect_active 'ChordLive' & effect_active 'ChordLive' ? effect_show_gui 'ChordLive' : nothing` | One-click button: on + window, second click off · *bouton en un clic* |
| `effect_show_gui 'ChordLive'` | Show / hide the Chord Live window (also a query) · *fenêtre on / off* |

### Buttons · Boutons — `effect_button 'ChordLive' N`
| N | Action |
|---|---|
| 1 | Auto tuning on / off (track brought to A = 440 Hz, tempo unchanged) · *diapason auto* |
| 2 | Pitch 0 (original tempo, key untouched) · *tempo d'origine* |
| 3 | All to 0 (original tempo and key, auto tuning kept) · *tout à 0* |
| 4 | Write the detected key to VirtualDJ's database · *tonalité → base* |
| 5 | Write the detected key to the database and the file's tag · *tonalité → tags* |
| 6 | Chords scrolling over the deck's waveform on / off (on by default) · *accords sur la forme d'onde (allumés par défaut)* |
| 7 | (no effect since V2.4: the waveform layer places itself) · *(sans effet depuis la V2.4 : le calque se place tout seul)* |

### Texts · Textes — `get_effect_string 'ChordLive' N`
| N | Content | Example |
|---|---|---|
| 1 | Current chord (with the deck's transposition) · *accord en cours* | `Am7` |
| 2–7 | Next 6 chords · *6 accords suivants* | `F`, `G`, `C/E`… |
| 8 | Beats left in the current chord · *temps restants* | `3` |
| 9–14 | Length in beats of next chords 1–6 · *durée des suivants* | `4` |
| 15 | Key heard (transposition included) · *tonalité entendue* | `Bm` |
| 16 | Comparison with VirtualDJ's key · *comparaison avec VirtualDJ* | `✓ VDJ` / `VDJ: D` |
| 17 | Tuning · *diapason* | `+12.3 c` / `in tune` |
| 18 | Auto tuning state · *état du diapason auto* | `on` / `off` |
| 19 | Analysis status (empty when ready) · *état de l'analyse* | `Decoding with VirtualDJ… 42 %` |
| 20 | Harmonic match with the other deck running Chord Live · *compatibilité* | `✓ B: Em` / `~ B: A` / `✗ B: F` |
| 21 | Match level, for colours · *niveau* | `good` / `ok` / `bad` |
| 22 | Next key change · *prochain changement de tonalité* | `→ C#m 2:31` |
| 23 | Key writing result · *résultat de l'écriture* | `DB ✓`, `tags …` |
| 24 | Waveform chords state · *calque* | `on` / `off` |

### Examples · Exemples
```xml
<!-- current chord, big, with the beats left -->
<textzone><pos x="+0" y="+0"/><size width="120" height="40"/>
  <text fontsize="32" weight="bold" color="#ffd02a" action="get_effect_string 'ChordLive' 1"/></textzone>
<textzone><pos x="+120" y="+4"/><size width="30" height="16"/>
  <text fontsize="12" color="white" action="get_effect_string 'ChordLive' 8"/></textzone>

<!-- auto tuning button, lit when on -->
<button action="effect_button 'ChordLive' 1" query="get_effect_string 'ChordLive' 18 &amp; param_equal 'on'">
  <pos x="+0" y="+50"/><size width="54" height="18"/>
  <off color="#202020"/><selected color="#806000"/>
  <text fontsize="10" weight="bold" color="white" align="center" text="TUNE"/></button>

<!-- harmonic match in green only when compatible -->
<textzone visibility="get_effect_string 'ChordLive' 21 &amp; param_equal 'good'"><pos x="+0" y="+75"/><size width="100" height="14"/>
  <text fontsize="10" weight="bold" color="#3ec46d" action="get_effect_string 'ChordLive' 20"/></textzone>
```

Custom button / mapping: `deck 1 effect_button 'ChordLive' 3` (all to 0 on deck A) · `deck 2 effect_button 'ChordLive' 6` (waveform chords on deck B).

---

© Olivier FRAPPIER 2026 · [DONATE](https://www.paypal.com/paypalme/owfrappier)

*Chord Live for VirtualDJ is a free initiative by a VirtualDJ fan. It is an independent product and is not affiliated with, endorsed by or sponsored by VirtualDJ or Atomix Productions. VirtualDJ is a trademark of Atomix Productions.*

*Idea, design, testing and direction: Olivier Frappier. The C++ code was written with the help of Claude (Anthropic's AI assistant), following his ideas and under his direction. · Idée, conception, tests et direction : Olivier Frappier. Le code C++ a été écrit avec l'aide de Claude (l'assistant IA d'Anthropic), sur ses idées et sous sa direction.*
