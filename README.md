# Lab5Web — Praktikum 5: JavaScript Dasar dan Manipulasi HTML

Mata kuliah: Pemrograman Web — Pertemuan 6

# Tujuan

1. Memahami sintaks dasar JavaScript dan cara menyisipkan JavaScript pada HTML.
2. Menggunakan variabel, tipe data, operator, percabangan, perulangan, dan function.
3. Menampilkan informasi melalui console, alert, prompt, dan elemen HTML.
4. Memanipulasi konten serta gaya elemen HTML dengan JavaScript.
5. Membuat interaksi sederhana pada form dan melakukan validasi input.
6. Mendokumentasikan pekerjaan praktikum beserta hasil pengujiannya.

# Struktur Folder

```
lab5_javascript/
├── index.html      # semua latihan, mini project, dan eksperimen
├── script.js       # seluruh logika JavaScript
├── README.md
└── screenshots/    # simpan screenshot hasil di sini
```

# Cara Menjalankan

1. Buka folder `lab5_javascript` di Visual Studio Code.
2. Buka `index.html` di browser (klik dua kali, atau gunakan ekstensi Live Server).
3. Tekan **F12 → Console** untuk melihat output `console.log`.
4. Jalankan tiap latihan sesuai urutan di halaman, lalu ambil screenshot.

# Langkah Kerja dan Hasil

Ganti `screenshots/...png` dengan screenshot Anda sendiri.

| Latihan | Yang dikerjakan | Hasil yang diharapkan | Screenshot |
|---|---|---|---|
| 1 | `textContent` dan `console.log` | Teks halaman menjadi "Hello World" dan pesan yang sama muncul di Console. Halaman menampilkan teks ke pengguna, Console untuk developer. | `screenshots/latihan1.png` |
| 2 | `prompt` + `alert` | Isi nama → "Halo, nama!". Cancel (`null`) dan input kosong → "Nama belum diisi." | `screenshots/latihan2.png` |
| 3 | `operasiDasar(9, 4)` | 13, 5, 36, 2.25, dan sisa bagi 1. Pembagian dan modulus dengan b = 0 ditangani. | `screenshots/latihan3.png` |
| 4 | `if–else` + `Number()` | ≥ 60 "Lulus", < 60 "Belum lulus", kosong/huruf/di luar 0–100 "Input nilai tidak valid." | `screenshots/latihan4.png` |
| 5 | `switch` | Angka 1–5 menampilkan nama bilangan, selain itu "Pilihan tidak tersedia". | `screenshots/latihan5.png` |
| 6 | Form genap/ganjil | 4 → genap, 7 → ganjil, −3 → ganjil, 0 → genap, 2.5 dan kosong → pesan tidak valid. | `screenshots/latihan6.png` |
| 7 | `ubahWarnaLatar(warna)` | Tiga tombol mengubah warna latar dengan satu function. | `screenshots/latihan7.png` |
| 8 | Checkbox + `addEventListener` | Total otomatis berubah (format `id-ID`, mis. 7.500). | `screenshots/latihan8.png` |
| Mini Project | Kalkulator nilai | Hasil tampil di halaman. Input di luar 0–100 ditolak. | `screenshots/miniproject.png` |

## Skenario uji Mini Project

Nilai akhir = tugas × 0,30 + UTS × 0,30 + UAS × 0,40.

| Skenario | Tugas | UTS | UAS | Nilai akhir | Predikat | Status |
|---|---|---|---|---|---|---|
| Nilai tinggi | 90 | 85 | 95 | 90,50 | A | Lulus |
| Nilai sedang | 70 | 65 | 72 | 69,30 | C | Lulus |
| Nilai rendah | 40 | 45 | 50 | 45,50 | E | Belum lulus |

Contoh dari modul (85, 78, 88) menghasilkan nilai akhir 84,10 dengan predikat B dan status Lulus.

# Eksperimen Mandiri

| No. | Tugas | Lokasi |
|---|---|---|
| 1 | Latihan 3 menerima dua nilai dari `prompt` dan dikonversi ke number | Tombol "Input dari prompt", function `operasiDariPrompt()` |
| 2 | Tabel perkalian 7 dari 1 sampai 10 dengan `for` | `tampilkanTabelPerkalian(7)` |
| 3 | `cekGenap(angka)` mengembalikan `true` jika genap | `cekGenap()`, `ujiCekGenap()` |
| 4 | Validasi kolom tidak boleh kosong | Form "Tugas H.7" |
| 5 | Menu Latihan 8 ditambah Nasi Putih (Rp3.000) dan Es Teh (Rp2.000) | Latihan 8 |
| 6 | Tombol sembunyikan/tampilkan elemen | `toggleElemen()` |

> Catatan: penomoran Bagian G pada modul asli melompat dari 1 ke 7. Di sini keenam butir dinomori ulang 1–6.

## Jawaban Pertanyaan (Bagian H)

**1. Perbedaan `console.log()`, `alert()`, `prompt()`, dan `textContent`/`innerHTML`**

- `console.log()` mencetak pesan ke Console browser. Pengguna biasa tidak melihatnya, jadi dipakai untuk debugging.
- `alert()` menampilkan kotak dialog berisi pesan dan menghentikan interaksi sampai ditutup.
- `prompt()` menampilkan dialog yang meminta masukan. Hasilnya string, atau `null` jika dibatalkan.
- `textContent` mengubah isi teks elemen HTML dan aman karena tidak menafsirkan tag. `innerHTML` mengubah isi sebagai HTML sehingga tag ikut diproses. Hindari `innerHTML` untuk data dari pengguna karena berisiko XSS.

**2. Perbedaan `let` dan `const`**

`let` menyatakan variabel yang nilainya boleh ditetapkan ulang. `const` tidak boleh ditetapkan ulang setelah diberi nilai awal.

```js
let umur = 20;
umur = 21;          // boleh

const nama = "Rani";
nama = "Sari";      // TypeError: Assignment to constant variable
```

**3. Perbedaan `==` dan `===`**

`==` membandingkan nilai setelah konversi tipe otomatis. `===` membandingkan nilai dan tipe tanpa konversi, sehingga lebih aman.

```js
5 == "5"    // true
5 === "5"   // false
0 == false  // true
0 === false // false
```

**4. Fungsi `if–else` dan `switch`**

Keduanya adalah percabangan untuk memilih blok kode berdasarkan kondisi.

- `if–else` dipakai untuk kondisi logis atau rentang nilai, misalnya `nilai >= 60`.
- `switch` dipakai untuk memilih satu tindakan dari beberapa nilai pasti, misalnya menu "1", "2", "3". `break` mencegah eksekusi berlanjut ke `case` berikutnya.

**5. Fungsi parameter dan `return`**

Parameter adalah variabel penerima data masukan ketika function dipanggil, sehingga function bisa dipakai ulang dengan data berbeda. `return` mengembalikan hasil ke pemanggil dan menghentikan eksekusi function.

```js
function hitungLuas(panjang, lebar) {   // panjang, lebar = parameter
  return panjang * lebar;               // return = hasil
}
hitungLuas(8, 4); // 32
```

**6. Memilih elemen dengan `document.getElementById()`**

Method ini mencari elemen yang atribut `id`-nya sama dengan string yang diberikan, lalu mengembalikan objek elemen tersebut, atau `null` jika tidak ditemukan. Karena `id` harus unik, hasilnya satu elemen. Objek itu bisa diubah isi atau gayanya.

```js
const el = document.getElementById("pesan");
el.textContent = "Halo, JavaScript!";
el.style.color = "blue";
```

**7. Script validasi form (nama tidak kosong, nilai 0–100)**

Lihat blok "Tugas H.7 + Eksperimen 4" di bagian akhir `script.js`.

```js
document.getElementById("formValidasi").addEventListener("submit", (event) => {
  event.preventDefault();
  const nama = document.getElementById("namaForm").value;
  const nilai = document.getElementById("nilaiForm").value;
  const hasil = document.getElementById("hasilValidasi");

  if (nama.trim() === "") { hasil.textContent = "Nama tidak boleh kosong."; return; }
  const angka = Number(nilai);
  if (nilai.trim() === "") { hasil.textContent = "Nilai tidak boleh kosong."; return; }
  if (Number.isNaN(angka) || angka < 0 || angka > 100) {
    hasil.textContent = "Nilai harus berupa angka antara 0 dan 100.";
    return;
  }
  hasil.textContent = "Data valid.";
});
```

## Pengumpulan

1. Buat repository baru bernama `Lab5Web`.
2. Salin `index.html`, `script.js`, `README.md`, dan folder `screenshots/`.
3. Commit dan push:
   ```bash
   git init
   git add .
   git commit -m "Praktikum 5: JavaScript dasar dan manipulasi HTML"
   git branch -M main
   git remote add origin https://github.com/<username>/Lab5Web.git
   git push -u origin main
   ```
# PNG
   <img width="1920" height="1080" alt="Cuplikan layar 2026-11-01 193953" src="https://github.com/user-attachments/assets/4360d67c-9381-46b3-9fc5-8e9f14b8b7f6" />
<img width="1920" height="1080" alt="Cuplikan layar 2026-11-01 193935" src="https://github.com/user-attachments/assets/1bb69bd7-23aa-46d4-a830-260ad7515292" />
<img width="1920" height="1080" alt="Cuplikan layar 2026-11-01 193915" src="https://github.com/user-attachments/assets/7e630559-bc08-4cdd-b782-e4d558e28fee" />
<img width="1920" height="1080" alt="Cuplikan layar 2026-11-01 193859" src="https://github.com/user-attachments/assets/b4cee05a-1784-4ea9-8ff2-060cf00e2d0c" />
<img width="1920" height="1080" alt="Cuplikan layar 2026-11-01 193741" src="https://github.com/user-attachments/assets/b0f57d2e-c071-43db-92e6-2630e4b6c911" />
<img width="1920" height="1080" alt="Cuplikan layar 2026-11-01 193704" src="https://github.com/user-attachments/assets/0dd40d89-f70e-4fc5-ab9f-456631eebc41" />
<img width="1920" height="1080" alt="Cuplikan layar 2026-11-01 193640" src="https://github.com/user-attachments/assets/3200bb48-52d9-4613-ac9c-d34618ffbdf2" />
<img width="1920" height="1080" alt="Cuplikan layar 2026-11-01 193551" src="https://github.com/user-attachments/assets/84fed3a0-6dff-4bfe-8ccf-ea3c24a600b0" />
<img width="1920" height="1080" alt="Cuplikan layar 2026-11-01 193516" src="https://github.com/user-attachments/assets/5953fbb5-5b9a-4071-8bbf-f1ea7b44186f" />
