---
description: Pengenalan
---

# Bab 1

## Apa itu pemrograman?

Pemrograman adalah proses menulis, menguji, dan memelihara kode sumber dari program komputer. Kode sumber ini ditulis dalam bahasa pemrograman yang dapat dipahami oleh komputer. Pemrograman memungkinkan kita untuk memberikan instruksi kepada komputer untuk menyelesaikan tugas tertentu, mulai dari yang sederhana hingga yang kompleks.

## Contoh kode sederhana

Program sederhana yang mencetak "Hello, World!"

```
  #include <iostream>
  using namespace std;
  int main() {
      cout << "Hello, World!" << endl;
      return 0;
  }
  
```

* **Tugas Latihan**: Buat program yang meminta input nama pengguna dan mencetak pesan sapaan, misalnya "Selamat datang, \[nama]!".

## Sejarah dan Perkembangan Bahasa Pemrograman

Sejarah bahasa pemrograman dimulai pada tahun 1940-an dengan bahasa mesin dan assembly. Seiring waktu, bahasa pemrograman tingkat tinggi seperti Fortran, COBOL, dan C muncul, yang memungkinkan pengembangan perangkat lunak yang lebih kompleks. Saat ini, terdapat banyak bahasa pemrograman modern seperti Python, Java, dan JavaScript yang digunakan untuk berbagai aplikasi, dari pengembangan web hingga kecerdasan buatan.

* **Tugas Latihan**: Buat ringkasan tentang satu bahasa pemrograman yang Anda sukai, termasuk fitur utama dan kegunaannya.

## Alur Kerja Program  : Input → Proses → Output

#### **1. Input (Masukan)**

Tahap ini merupakan awal dari alur kerja program, di mana pengguna atau sistem memberikan **data atau informasi** yang dibutuhkan program untuk dijalankan.

**Contoh:**

* Pengguna memasukkan angka ke dalam kalkulator.
* Sistem membaca file teks dari hard disk.
* Aplikasi menerima data dari sensor.

🡒 **Tujuan:** Mengumpulkan data yang akan diolah.

#### **2. Proses**

Setelah input diterima, program akan melakukan **pemrosesan data** sesuai dengan logika atau algoritma yang sudah ditentukan oleh programmer.

**Contoh:**

* Menjumlahkan dua angka.
* Mengurutkan data dari terkecil ke terbesar.
* Menganalisis data dan membuat keputusan.

🡒 **Tujuan:** Mengolah input agar menjadi informasi yang berguna.

#### 3. **Output (Keluaran)**

Ini adalah tahap akhir di mana hasil dari proses ditampilkan atau disimpan. Output bisa berupa informasi visual, suara, file, atau aksi tertentu.

**Contoh:**

* Menampilkan hasil perhitungan ke layar.
* Menyimpan hasil analisis ke dalam file.
* Mengirimkan notifikasi ke pengguna.

🡒 **Tujuan:** Menyampaikan hasil dari proses ke pengguna atau sistem lain.

#### Contoh Sederhana:

Program untuk menjumlahkan dua bilangan:

* **Input:** Pengguna memasukkan angka 5 dan 3.
* **Proses:** Program menjumlahkan 5 + 3.
* **Output:** Program menampilkan hasil 8 ke layar.

**Soal:**\
Sebuah program menerima dua angka dari pengguna, lalu menghitung selisihnya dan menampilkan hasilnya.

* Apa **input**, **proses**, dan **output** dari program ini?

## Struktur Dasar Program c++

#### 1. **Preprocessor Directives**

Bagian ini biasanya terletak di awal program dan digunakan untuk menyertakan file header yang diperlukan.

**Contoh:**

```
#include <iostream>
```

`#include <iostream>`: Menyertakan file header untuk input-output stream (untuk menggunakan `cout` dan `cin`).

#### 2. **Namespace**

Pada umumnya, program C++ menggunakan namespace `std` agar bisa langsung mengakses fitur standar seperti `cout`, `cin`, dan lainnya tanpa menulis `std::` di depannya.

**Contoh:**

```
using namespace std;
```

#### 3. **Fungsi main()**

Semua program C++ dimulai dari fungsi `main()`. Ini adalah titik awal eksekusi program. Fungsi `main()` selalu ada dalam setiap program C++.

**Contoh:**

```
int main() {
    // kode program
    return 0;  // Mengembalikan nilai 0 ke sistem operasi
}
```

Fungsi `main()` selalu mengembalikan nilai bertipe `int`, biasanya `0` untuk menandakan program selesai tanpa error.

#### 4. **Deklarasi dan Inisialisasi Variabel**

Di dalam fungsi `main()`, kita bisa mendeklarasikan variabel dan menginisialisasinya.

**Contoh:**

```
int x = 10; // deklarasi variabel x bertipe integer
```

#### 5. **Pernyataan dan Ekspresi**

Program C++ terdiri dari serangkaian pernyataan atau instruksi yang akan dieksekusi oleh komputer.

**Contoh:**

```
cout << "Hello, World!";  // Menampilkan pesan ke layar
```

Struktur Dasar Program C++ (Contoh Lengkap)

```
#include <iostream>  // Menyertakan library input-output standar

using namespace std;  // Menggunakan namespace std

int main() {  // Fungsi utama program
    int a = 5;    // Deklarasi dan inisialisasi variabel a
    int b = 3;    // Deklarasi dan inisialisasi variabel b

    int sum = a + b;  // Proses: Menjumlahkan a dan b

    cout << "Hasil penjumlahan: " << sum << endl;  // Output hasil

    return 0;  // Mengembalikan nilai 0 (berhasil)
}
```

*   #### **Latihan Soal :**

    **Soal:**\
    Buatlah program C++ yang:

    1. Menyertakan file header yang diperlukan.
    2. Menggunakan namespace `std`.
    3. Menyertakan fungsi `main()`.
    4. Menampilkan pesan **"Selamat Belajar C++!"** di layar.

    **Pertanyaan:**

    * Apa nama file header yang diperlukan untuk input-output?
    * Fungsi apa yang digunakan untuk menampilkan pesan ke layar?

