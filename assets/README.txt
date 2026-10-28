BACKGROUND MUSIC
================

music-placeholder.wav
---------------------
This is a TEMPORARY placeholder — a soft drone + bell arpeggio that was
generated mathematically for this project. It is not a recording, it is not
taken from anywhere, and there is no licence attached to it. It exists only so
the music button works while you decide on the real song.

To use your own song
--------------------
1. Put your file in this folder.
2. Name it exactly:  music.mp3
3. That's it. Reload the page.

The player tries assets/music.mp3 first and only falls back to the
placeholder if that file is not there. No code change needed.

Once your song is in place you can delete music-placeholder.wav, but keeping
it costs nothing (431 KB) and means the music button still works if the mp3
ever goes missing.

Tips
----
- Keep it under ~3 MB so the page stays quick on mobile data.
- Something that loops cleanly works best — the track repeats endlessly.
- Instrumental (nadaswaram / thavil / veena / flute) suits the invitation
  better than a vocal track that competes with reading.
- Make sure you have the right to use the track on a public website.

The volume is set to 32%. To change it, find this line in index.html:

    audio.volume = 0.32;
