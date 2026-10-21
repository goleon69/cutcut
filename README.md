# cutcut

A tiny MP3 trimmer that runs in your browser. Open an MP3, set where it should start and end, save. No install, works on macOS, Windows and Linux.

**Use it online:** https://goleon69.github.io/cutcut/
**Or offline:** download `cutcut.html` and open it in any modern browser.

## Features

- Waveform with overview and zoom (down to a 0.5 s window)
- Play/Pause, draggable start and end markers, editable time fields
- Lossless cut: original MP3 frames are copied, nothing is re-encoded
- Frame-accurate (about 26 ms at 44.1 kHz)
- Keeps ID3v2, ID3v1 and APE tags; updates the Xing/Info and LAME headers
- Saves as `<name>_cut.mp3`
- Everything happens locally: your audio never leaves your computer

## How it works

Everything is in one file, `cutcut.html` (HTML + CSS + JavaScript, no dependencies).

- Playback uses the Web Audio API on the decoded buffer, for exact positions. The `<audio>` element is avoided because Safari seeks MP3s to estimated positions.
- The cut works on the raw MP3 bitstream: frames are parsed, the selected range is copied, and the Xing/Info header (frame count, byte count, TOC) and LAME tag (delay/padding, length, CRC) are rewritten. A VBRI header is dropped.

## Not included (yet)

Fades, re-encoding, keyboard shortcuts, batch processing. Contributions welcome.

## Contributing

Fork the repo, make your change in `cutcut.html`, open a pull request. Please bump the version shown next to the title.

## License

GPL-3.0. See [LICENSE](LICENSE). You can use, study, change and share cutcut; modified versions you distribute must also be released under GPL-3.0.

Copyright (C) 2026 Leonardo Gon

---

*Italiano:* cutcut è un piccolo programma per tagliare l'inizio e la fine di un file MP3, senza perdita di qualità. Si apre nel browser, senza installare niente.
