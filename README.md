# Phase-0-Week-5

# Week 5: Regular Expressions (Regex) in JavaScript

## 1. Penjelasan
Regular Expressions (Regex) adalah pola pencarian yang digunakan untuk mencocokkan dan memanipulasi teks. Dalam JavaScript, regex dapat digunakan dengan objek `RegExp` atau metode string seperti `.match()`, `.replace()`, `.test()`, dan `.exec()`.

### Sintaks Dasar Regex
- `/pattern/modifier` atau `new RegExp("pattern", "modifier")`
- Modifier umum:
  - `g` (global): Mencari semua kecocokan dalam teks
  - `i` (case-insensitive): Tidak membedakan huruf besar dan kecil
  - `m` (multiline): Mencocokkan dalam beberapa baris

### Karakter Khusus dalam Regex
- `.` : Mewakili satu karakter apa pun kecuali newline (`\n`)
- `\d` : Mewakili angka (0-9)
- `\w` : Mewakili karakter huruf, angka, dan underscore (`a-z`, `A-Z`, `0-9`, `_`)
- `\s` : Mewakili karakter spasi
- `^` : Menandai awal string
- `$` : Menandai akhir string
- `[]` : Menentukan kumpulan karakter, misalnya `[a-z]` berarti huruf kecil a-z
- `|` : Operator OR dalam regex
- `()` : Menentukan grup dalam pola regex

---

## 2. Contoh Penggunaan
### a. Mengecek format email
```javascript
const emailRegex = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
console.log(emailRegex.test("user@example.com")); // true
console.log(emailRegex.test("user@example")); // false
```

### b. Mengambil semua angka dalam teks
```javascript
const text = "Harga barang ini adalah 150000 dan diskon 20000";
const angka = text.match(/\d+/g);
console.log(angka); // [ '150000', '20000' ]
```

### c. Mengganti format tanggal dari DD-MM-YYYY ke YYYY/MM/DD
```javascript
const tanggal = "25-12-2024";
const newFormat = tanggal.replace(/(\d{2})-(\d{2})-(\d{4})/, "$3/$2/$1");
console.log(newFormat); // "2024/12/25"
```

### d. Validasi nomor telepon
```javascript
const phoneRegex = /^\+?\d{10,13}$/;
console.log(phoneRegex.test("+6281234567890")); // true
console.log(phoneRegex.test("08123abc")); // false
```

---

## 3. Tugas / Assignment
### 1. Validasi Password
Buat regex untuk memvalidasi password dengan ketentuan:
- Minimal 8 karakter
- Harus memiliki huruf besar, huruf kecil, angka, dan simbol
- Tidak boleh ada spasi

### 2. Ekstrak Hashtag dari Teks
Buat regex untuk mengekstrak semua kata yang diawali dengan `#` dari teks berikut:
```
"Saya suka #programming dan #JavaScript, ayo belajar bersama!"
```

### 3. Format Nomor Telepon
Buat regex untuk mengubah format nomor telepon dari:
```
081234567890 -> +62 812-3456-7890
```

Selamat belajar dan semoga berhasil! 🚀

