# kartukata

Flashcard app buat latihan Tes Kemampuan Verbal — sinonim dan antonim.

**[Coba langsung →](https://fritzie1860.github.io/kartukata/)**

<!-- TODO: taruh screenshot di sini. Ini bagian yang paling ngaruh.
     Caranya paling gampang: drag file gambar ke kolom komentar issue di GitHub,
     GitHub bakal ngasih URL, terus pakai URL-nya di sini.
     ![kartukata](https://user-images.githubusercontent.com/...)
-->

Aku bikin ini waktu nyiapin tes kemampuan verbal sendiri. Aplikasi flashcard yang ada
kebanyakan pakai kosakata Inggris, atau maksa bikin akun dulu. Yang ini nggak: buka,
langsung latihan.

## Isinya

- **482 pasangan sinonim** dan **1.060 pasangan antonim**
- Atur jumlah kartu per sesi, dari 1 sampai semua
- Kartu diacak tiap sesi, bisa diacak ulang kapan aja
- Klik kartu buat lihat jawaban, animasi flip
- Nggak ada login, nggak ada tracking, nggak ada backend

Menu Analogi masih placeholder — belum digarap.

## Stack

React 19 · Vite 7 · React Router · Framer Motion (animasi kartu) · Tailwind CSS · Lucide icons

Deploy ke GitHub Pages lewat `gh-pages`. Karena ini SPA dan GitHub Pages nggak punya
rewrite rule, langkah build nyalin `index.html` jadi `404.html` supaya refresh di
`/sinonim` nggak bikin halaman 404.

## Jalanin di lokal

```bash
git clone https://github.com/Fritzie1860/kartukata.git
cd kartukata
npm install
npm run dev
```

Buka URL yang muncul di terminal (biasanya `http://localhost:5173`).

Buat deploy:

```bash
npm run deploy
```

## Struktur

```
src/
├── App.jsx                  # routing
├── components/
│   ├── Menu.jsx             # halaman pilih mode
│   ├── Sinonim.jsx          # kartu sinonim
│   ├── Antonim.jsx          # kartu antonim
│   └── Footer.jsx
└── data/
    ├── words-sinonim.js     # 482 pasangan
    └── words-antonim.js     # 1.060 pasangan
```

## Nambah kosakata

Tambahin entry di `src/data/words-sinonim.js` atau `words-antonim.js`:

```js
// words-sinonim.js
{ word: "efusi", synonym: "pencurahan" },

// words-antonim.js
{ word: "prefiks", antonym: "akhiran" },
```

Nggak perlu ngubah apa-apa lagi, jumlah kartu ngikut panjang array.
