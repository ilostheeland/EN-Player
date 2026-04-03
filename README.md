# ENHYPEN Music Player

A Spotify-like music player for ENHYPEN's complete discography, organized by era.
Built with vanilla HTML, CSS, and JavaScript. Hosted on GitHub Pages — no server required.

---

## Live Site

Once GitHub Pages is enabled, your site will be at:
```
https://YOUR-USERNAME.github.io/YOUR-REPO-NAME
```

---

## Repo Structure

```
/
├── index.html        ← the player
├── songs.json        ← full discography (eras, albums, song titles)
├── README.md
└── songs/
    ├── Given-Taken.mp3
    ├── Drunk-Dazed.mp3
    └── ... (all your MP3 files go here)
```

---

## Setup

### 1. Create the repo

1. Go to [github.com](https://github.com) and create a new repository.
2. Name it anything — e.g. `enhypen-player`.
3. Set it to **Public**.

### 2. Upload the files

Upload `index.html`, `songs.json`, and `README.md` to the root of the repo.

Then create a `songs/` folder and upload all your MP3 files there.

### 3. Enable GitHub Pages

1. Go to your repo → **Settings** → **Pages**.
2. Under "Source", select **Deploy from a branch**.
3. Choose `main` branch and `/ (root)`.
4. Click **Save**.

GitHub will give you a public URL in about 30 seconds.

---

## MP3 File Naming

Each file in the `songs/` folder must match exactly what is listed in `songs.json`.
The naming convention is: words separated by hyphens, special characters removed.

Examples:

| Song Title                        | Filename                              |
|----------------------------------|---------------------------------------|
| Given-Taken                      | `Given-Taken.mp3`                     |
| Drunk-Dazed                      | `Drunk-Dazed.mp3`                     |
| Let Me In (20 CUBE)              | `Let-Me-In-20-CUBE.mp3`               |
| Intro : Walk the Line            | `Intro-Walk-the-Line.mp3`             |
| Future Perfect (Pass the MIC)    | `Future-Perfect-Pass-the-MIC.mp3`     |
| XO (Only If You Say Yes)         | `XO-Only-If-You-Say-Yes.mp3`          |
| Bad Desire (With or Without You) | `Bad-Desire-With-or-Without-You.mp3`  |
| No Way Back (feat. So!YoON!)     | `No-Way-Back-feat-SoYoON.mp3`         |
| Big Girls Don't Cry              | `Big-Girls-Dont-Cry.mp3`              |

All filenames are listed in `songs.json` under each song's `"file"` field.
If a file is missing, the player shows a brief error toast and skips to the next song.

---

## Controls

| Action       | Control                        |
|-------------|--------------------------------|
| Play / Pause | Click button or press `Space`  |
| Next song    | Click button or press `→`      |
| Previous     | Click button or press `←`      |
| Seek         | Click anywhere on progress bar |
| Mute         | Click speaker icon or press `M`|
| Volume       | Drag the volume slider         |

---

## Adding New Songs

1. Upload the MP3 to the `songs/` folder.
2. Open `songs.json` and add an entry in the correct album block:
   ```json
   { "title": "New Song Title", "file": "New-Song-Title.mp3" }
   ```
3. Commit and push. GitHub Pages updates automatically within seconds.

---

## Notes

- GitHub allows files up to **100 MB** each. Most MP3s are 3–8 MB, so this is not an issue.
- The repo should stay under **1 GB** total. With ~100 songs at ~5 MB each, you are well within limits.
- If you have very large files, look into [Git LFS](https://git-lfs.github.com/).
- The player only works correctly when served over HTTP/HTTPS. Opening `index.html` directly from your local file system will not load `songs.json` due to browser security rules. Use GitHub Pages or a local server like `npx serve`.
