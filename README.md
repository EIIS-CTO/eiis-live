# EIIS Live — sito & download

Landing page (GitHub Pages) che presenta EIIS Live e permette di scaricare il dmg
per Mac. Contenuto di questa cartella:

```
index.html            → la pagina (si pubblica con GitHub Pages)
.nojekyll             → serve a GitHub Pages (non toccare)
assets/icon.png       → icona dell'app usata nella pagina
download/
  EIIS-Live-Guida-Installazione-e-Uso.pdf   → guida PDF (link dalla pagina)
release-dmg/
  EIIS-Live-1.5.0-arm64.dmg   → l'app (93 MB) → va caricata come RELEASE (vedi sotto)
```

> Il dmg (93 MB) **non** va nel repo: GitHub blocca gli upload web oltre 25 MB.
> Si carica come **Release**, e il tasto Download della pagina lo prende da lì.

---

## Come pubblicare (≈5 minuti, tutto dal sito github.com)

### 1. Crea il repository
GitHub → **New repository** → nome es. **`eiis-live`** → Public → Create.

### 2. Carica i file della pagina
Nel repo: **Add file → Upload files** → trascina dentro **tutti** questi elementi
di questa cartella **TRANNE** la cartella `release-dmg`:
- `index.html`
- `.nojekyll`
- la cartella `assets`
- la cartella `download`

Poi **Commit changes**.

### 3. Attiva GitHub Pages
Repo → **Settings → Pages** → *Source*: **Deploy from a branch** → *Branch*: **main** / **/(root)** → **Save**.
Dopo ~1 minuto il sito è online su:
`https://<tuo-utente>.github.io/eiis-live/`

### 4. Carica l'app come Release
Repo → **Releases** (a destra) → **Create a new release**:
- **Tag**: `v1.5.0`
- **Title**: `EIIS Live 1.5.0`
- **Attach binaries**: trascina il file **`release-dmg/EIIS-Live-1.5.0-arm64.dmg`**
- **Publish release**

### 5. Fatto ✅
Il tasto **Download** sulla pagina scarica automaticamente il dmg dall'**ultima
release** (usa l'indirizzo `…/releases/latest/download/EIIS-Live-1.5.0-arm64.dmg`,
costruito da solo in base al nome del tuo repo).

---

## Aggiornare a una versione futura
1. Crea una **nuova Release** con l'ultimo dmg (stesso nome file, oppure aggiorna
   `ASSET` nello `<script>` in fondo a `index.html`).
2. Se cambi numero di versione, aggiorna i testi "1.5.0" in `index.html`.

## Note
- Se usi un **dominio personalizzato** (non `*.github.io`), imposta a mano il link:
  nello `<script>` in fondo a `index.html`, sostituisci la parte automatica con
  `https://github.com/<owner>/<repo>/releases/latest/download/EIIS-Live-1.5.0-arm64.dmg`.
- La pagina è **statica e autonoma** (nessuna dipendenza esterna), tema chiaro/scuro
  automatico, responsive.
