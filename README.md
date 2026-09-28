# EPS-TOPIK Vocabulary Quiz

Website statis offline berbasis HTML5, CSS3, dan JavaScript Vanilla. Data kosakata diambil dan disusun dari bagian KOSAKATA pada buku **EPS-TOPIK NEW 한국어 표준교재 1 (rilisan 2024)** yang diunggah pengguna. Struktur buku pada halaman daftar isi mencakup Bab 1–30.

## Struktur
```text
eps-topik-vocabulary-quiz/
├── index.html
├── style.css
├── script.js
├── data/
│   ├── chapters.js
│   └── vocabulary.js
└── README.md
```

## Menjalankan
Karena ini website statis, bisa dibuka langsung dengan `index.html`. Untuk pengujian lokal yang lebih konsisten gunakan server sederhana:

```bash
python -m http.server 8080 --directory .
```
Lalu buka `http://localhost:8080`. Tidak ada backend, database, atau API.

## Fitur
Home, 30 chapter, Vocabulary Explorer, 5 mode quiz, timer OFF/30/60/90 detik, feedback jawaban, hasil & review, flashcards, progress, XP/level, streak, achievement, statistik, dark mode, dan localStorage.

## Penyimpanan
- `epsTopikProgress` — XP, streak, learned/mastered, flashcard status, achievement, dll.
- `epsTopikSettings` — dark mode, timer, jumlah soal, mode quiz.
- `epsTopikQuizHistory` — riwayat quiz dan jawaban.

## Menambahkan vocabulary
Tambahkan item baru ke `VOCAB_GROUPS` dalam `data/vocabulary.js` pada kategori yang sesuai. Sistem akan otomatis membuat ID per bab dan menggunakan kata baru pada Explorer, quiz, flashcard, dan progress.

## Menambahkan bab
Tambahkan satu objek bab di `data/chapters.js` dan satu/lebih group vocabulary dengan `chapter` yang sama. Jumlah vocabulary card dihitung dari data runtime.

## Random Question Generator
1. Memilih vocabulary secara acak tanpa pengulangan dalam satu quiz.
2. Menentukan tipe soal sesuai setting / Mixed.
3. Mengambil distractor dari bab yang sama.
4. Menghapus duplikat pilihan.
5. Mengacak pilihan jawaban.

## Catatan akurasi sumber
Terminologi Korea, pasangan arti Indonesia, kategori, dan beberapa ejaan/terjemahan ditahan sedekat mungkin dengan sumber terjemahan yang diunggah. Beberapa typo/format asli pada terjemahan buku memang dipertahankan agar tidak mengklaim koreksi yang tidak dilakukan. Pertanyaan quiz dibuat baru dari data vocabulary, bukan menyalin latihan textbook.
