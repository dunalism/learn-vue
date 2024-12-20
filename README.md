# Eager Loading vs Lazy Loading

## 1. Komponen Langsung (Eager Loading)

### Definisi

Komponen seperti `HomePage` dimuat secara langsung saat aplikasi diinisialisasi. Semua kode untuk komponen ini akan dimasukkan ke dalam bundle utama aplikasi.

### Karakteristik

- **Waktu Muat Awal**: Dapat menyebabkan waktu muat awal yang lebih lama jika ada banyak komponen yang dimuat secara langsung.
- **Lifecycle**: Komponen yang dimuat secara eager akan melalui seluruh lifecycle dari mounting saat aplikasi pertama kali dimuat, meskipun komponen tersebut tidak langsung ditampilkan. Metode seperti `created` dan `beforeMount` akan dipanggil saat aplikasi dimuat.

### Kapan Menggunakan

Gunakan eager loading untuk:

- Komponen yang sangat penting.
- Komponen yang sering digunakan.
- Komponen yang harus selalu tersedia segera setelah aplikasi dimuat (misalnya halaman beranda).

---

## 2. Callback Import (Lazy Loading)

### Definisi

Komponen seperti `() => import("../views/LoginPage.vue")` dimuat secara dinamis hanya ketika rute tersebut diakses.

### Karakteristik

- **Bundle Terpisah**: Menggunakan fitur dynamic import dari JavaScript untuk memuat komponen secara terpisah dalam bundle yang berbeda.
- **Waktu Muat Awal**: Dapat mengurangi ukuran bundle utama dan mempercepat waktu muat awal aplikasi.
- **Lifecycle**: Komponen yang dimuat secara lazy hanya akan melalui lifecycle dari mounting saat rute yang terkait dengan komponen tersebut diakses. Metode seperti `created`, `mounted`, dan `beforeMount` hanya akan dipanggil saat pengguna mengakses rute tersebut.

### Kapan Menggunakan

Gunakan lazy loading untuk:

- Komponen yang jarang diakses.
- Komponen yang tidak kritis (contoh: halaman login atau pengaturan).
- Mengoptimalkan performa aplikasi dengan meminimalkan ukuran bundle utama.

---

## 3. Perbandingan

| **Aspek**           | **Eager Loading**                     | **Lazy Loading**                      |
| ------------------- | ------------------------------------- | ------------------------------------- |
| **Waktu Muat Awal** | Lebih lama                            | Lebih cepat                           |
| **Ukuran Bundle**   | Lebih besar                           | Lebih kecil                           |
| **Lifecycle**       | Semua komponen dimuat di awal         | Komponen dimuat hanya saat diperlukan |
| **Penggunaan**      | Komponen penting dan sering digunakan | Komponen jarang diakses               |

---

## Catatan Tambahan

### Router Navigation

- **`router.push`**: Tidak memicu lifecycle komponen.
- **`router.replace`**: Mengganti rute saat ini tanpa menambah riwayat ke stack. Perlu diperhatikan bahwa pengguna tidak dapat kembali ke riwayat sebelumnya.

### Optional Chaining (?.)

Memungkinkan Anda untuk mengakses properti dari objek yang mungkin `null` atau `undefined` tanpa menyebabkan error.

```javascript
const foo = { someFooProp: "hi" };

console.log(foo.someFooProp?.toUpperCase() ?? "not available"); // "HI"
console.log(foo.someBarProp?.toUpperCase() ?? "not available"); // "not available"
```

### Nullish Coalescing (??)

Digunakan untuk memberikan nilai default pada variabel atau parameter, tetapi hanya ketika nilai tersebut `null` atau `undefined`. Nullish coalescing berbeda dengan operator OR (`||`) karena operator OR akan menganggap nilai falsy lainnya, seperti `0` atau string kosong (`""`), sebagai kondisi yang memicu nilai default.

```javascript
const value = 0;
console.log(value || "default"); // "default" (karena 0 dianggap falsy)
console.log(value ?? "default"); // 0 (karena 0 bukan null atau undefined)
```

---

## Box Model

- **`box-border`**: Padding dan border termasuk dalam ukuran elemen.
- **`box-content`**: Hanya konten yang dihitung dalam ukuran elemen.

---

## Parsing Angka dari String

- **`parseFloat()`**: Mengubah string ke bilangan desimal.
  ```javascript
  parseFloat("32.222"); // 32.222
  ```
- **`parseInt()`**: Mengubah string ke bilangan bulat.
  ```javascript
  parseInt("32.222"); // 32
  ```
