# Tante Culik Aku Dong Lyrics

## MarkDown
### Lyrics Animation with Python Threads 🎵
> *Status: Terminal Animation Sript Ready*

### 📑 Deskripsi Lagu
File ini berisi konfigurasi lirik untuk lagu yang berjudul **"Tante Culik Aku Dong"**. Skrip Python akan mengeksekusi baris-baris di bawah ini dengan efek pengetikan otomatis yang sinkron.

### 🎤 Lirik & Sinkronisasi
Berikut adalah tabel waktu yang digunakan dalam fungsi `sing_song()`:

| Baris Lirik | Kecepatan Ketik (Speed) | Delay Muncul (Detik) |
| :--- | :---: | :---: |
| "Tante..." | 0.08 | 0.3 |
| "Sudah terbiasa terjadi tante..." | 0.09 | 2.5 |
| "Teman datang cuma kalo butuh saja..." | 0.08 | 5.8 |
| "Coba kalau lagi susah..." | 0.15 | 9.5 |
| "Mereka semua menghilaaaaang..." | 0.15 | 13.5 | 

### 💻 Implementasi Kode (Code)
```
Python
def sing_song():
    lyrics = [
        ("Tante...", 0.08),
        ("Sudah terbiasa terjadi tante...", 0.09),
        ("Teman datang cuma kalo butuh saja...", 0.08),
        ("Coba kalau lagi susah...", 0.15),
        ("Mereka semua menghilaaaaang...", 0.15)
    ]
    delays = [0.3, 2.5, 5.8, 9.5, 13.5]

    threads = []
    for i in range(len(lyrics)):
        lyric_text, speed = lyrics[i]
        t = Thread(target=sing_lyric, args=(lyric_text, delays[i], speed))
        threads.append(t)
        t.start()
        
    for t in threads:
        t.join()

if __name__ == "__main__":
    sing_song()
