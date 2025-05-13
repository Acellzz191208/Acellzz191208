---
description: Fungsi
---

# Bab 7

## **Fungsi dalam C++**

Fungsi adalah sekumpulan pernyataan yang dikelompokkan bersama untuk melakukan tugas tertentu. Fungsi memungkinkan kita untuk mengorganisasi kode secara lebih terstruktur, menghindari pengulangan kode, dan meningkatkan keterbacaan serta pemeliharaan program.

***

#### **1. Definisi dan Kegunaan Fungsi**

**Definisi Fungsi:**

Fungsi adalah blok kode yang diberi nama yang dapat dipanggil dari tempat lain dalam program. Fungsi melakukan tugas tertentu dan dapat mengembalikan nilai. Dengan menggunakan fungsi, Anda dapat menulis kode yang lebih modular dan efisien.

**Kegunaan Fungsi:**

* **Modularisasi**: Fungsi membagi program menjadi bagian-bagian kecil yang dapat dipahami dan dikelola dengan lebih mudah.
* **Penghindaran Pengulangan Kode**: Fungsi memungkinkan Anda untuk menulis kode sekali dan menggunakannya berulang kali.
* **Peningkatan Pembacaan Kode**: Fungsi memungkinkan Anda memberi nama pada bagian kode tertentu, membuat program lebih mudah dibaca dan dipahami.
* **Abstraksi**: Dengan menggunakan fungsi, Anda dapat menyembunyikan implementasi dari bagian program lain yang hanya membutuhkan hasil dari fungsi tersebut.

***

#### **2. Deklarasi, Definisi, dan Pemanggilan Fungsi**

**Deklarasi Fungsi:**

Deklarasi fungsi memberi tahu kompiler tentang nama fungsi, jenis nilai yang dikembalikan (return type), dan tipe parameter yang digunakan oleh fungsi tersebut. Deklarasi fungsi biasanya diletakkan di bagian atas program atau sebelum fungsi utama (`main`).

**Sintaks Deklarasi Fungsi:**

```cpp
return_type nama_fungsi(parameter1, parameter2, ...);
```

**Definisi Fungsi:**

Definisi fungsi adalah implementasi dari fungsi yang sudah dideklarasikan. Di sinilah kita menuliskan kode yang akan dijalankan ketika fungsi dipanggil.

**Sintaks Definisi Fungsi:**

```cpp
return_type nama_fungsi(parameter1, parameter2, ...) {
    // kode fungsi
    return nilai;
}
```

**Pemanggilan Fungsi:**

Pemanggilan fungsi dilakukan di dalam fungsi lain (biasanya di dalam fungsi `main`). Fungsi yang telah didefinisikan sebelumnya dipanggil dengan menyebutkan nama fungsi dan memberikan argumen yang diperlukan.

**Contoh Fungsi dengan Deklarasi, Definisi, dan Pemanggilan:**

```cpp
#include <iostream>
using namespace std;

// Deklarasi fungsi
int tambah(int a, int b);

int main() {
    int hasil = tambah(3, 5);  // Pemanggilan fungsi
    cout << "Hasil penjumlahan: " << hasil << endl;
    return 0;
}

// Definisi fungsi
int tambah(int a, int b) {
    return a + b;
}
```

**Penjelasan:**

* **Deklarasi fungsi** `tambah`: Memberitahukan kompiler bahwa ada fungsi `tambah` yang menerima dua parameter `int` dan mengembalikan nilai bertipe `int`.
* **Definisi fungsi** `tambah`: Implementasi kode fungsi yang menjumlahkan dua angka.
* **Pemanggilan fungsi** `tambah`: Fungsi dipanggil dalam `main` dengan mengirimkan nilai `3` dan `5` sebagai argumen.

***

#### **3. Parameter dan Return Value**

**Parameter Fungsi:**

Parameter adalah nilai yang diteruskan ke fungsi saat pemanggilan. Parameter ini digunakan dalam fungsi untuk melakukan operasi atau perhitungan.

* **Parameter Formal**: Tipe data dan nama parameter yang didefinisikan dalam deklarasi atau definisi fungsi.
* **Argument**: Nilai yang diberikan pada saat pemanggilan fungsi.

**Return Value:**

Return value adalah nilai yang dikembalikan oleh fungsi setelah melakukan operasi tertentu. Fungsi yang memiliki `return_type` (selain `void`) mengembalikan nilai ke pemanggilnya.

* Jika fungsi tidak mengembalikan nilai, maka kita gunakan tipe `void`.
* Fungsi yang mengembalikan nilai harus menggunakan kata kunci `return` di dalam tubuh fungsi.

**Contoh Parameter dan Return Value:**

```cpp
#include <iostream>
using namespace std;

// Fungsi dengan parameter dan return value
int kali(int a, int b) {
    return a * b;  // Mengembalikan hasil perkalian
}

int main() {
    int hasil = kali(4, 5);  // Memanggil fungsi dengan 4 dan 5 sebagai argumen
    cout << "Hasil perkalian: " << hasil << endl;
    return 0;
}
```

**Penjelasan:**

* Fungsi `kali` menerima dua parameter, `a` dan `b`, yang digunakan dalam operasi perkalian.
* Fungsi `kali` mengembalikan hasil perkalian `a` dan `b`, yang kemudian ditangkap di dalam `main` dan ditampilkan.

***

#### **4. Fungsi Rekursif (Pengantar)**

**Definisi Fungsi Rekursif:**

Fungsi rekursif adalah fungsi yang memanggil dirinya sendiri untuk menyelesaikan suatu masalah. Fungsi rekursif sering digunakan dalam masalah yang dapat dibagi menjadi sub-masalah yang lebih kecil dan serupa.

**Cara Kerja Fungsi Rekursif:**

* **Basis Kasus**: Syarat penghentian rekursi. Fungsi akan berhenti memanggil dirinya sendiri ketika mencapai kondisi ini.
* **Langkah Rekursif**: Fungsi memanggil dirinya sendiri dengan parameter yang lebih kecil (atau berubah) untuk memecahkan sub-masalah.

**Contoh Fungsi Rekursif (Faktorial):**

Fungsi rekursif yang menghitung faktorial dari suatu angka:

```cpp
#include <iostream>
using namespace std;

// Fungsi rekursif untuk menghitung faktorial
int faktorial(int n) {
    if (n == 0) {  // Basis kasus: faktorial 0 adalah 1
        return 1;
    }
    return n * faktorial(n - 1);  // Langkah rekursif
}

int main() {
    int angka = 5;
    cout << "Faktorial dari " << angka << " adalah: " << faktorial(angka) << endl;
    return 0;
}
```

**Penjelasan:**

* **Basis Kasus**: Ketika `n` sama dengan 0, faktorialnya adalah 1, sehingga rekursi berhenti.
* **Langkah Rekursif**: Fungsi `faktorial` memanggil dirinya sendiri dengan nilai `n - 1` sampai mencapai nilai `0`.

**Output:**

```
Faktorial dari 5 adalah: 120
```

***

#### **Ringkasan:**

1. **Fungsi** adalah blok kode yang diberi nama dan dapat dipanggil untuk melakukan tugas tertentu.
2. **Deklarasi, Definisi, dan Pemanggilan Fungsi**: Fungsi dideklarasikan untuk memberi tahu kompiler, didefinisikan untuk memberikan implementasi, dan dipanggil untuk mengeksekusi tugasnya.
3. **Parameter dan Return Value**: Fungsi dapat menerima parameter untuk digunakan dalam perhitungan dan mengembalikan hasil dengan kata kunci `return`.
4. **Fungsi Rekursif** adalah fungsi yang memanggil dirinya sendiri untuk menyelesaikan masalah, biasanya dengan kasus dasar sebagai penghentian rekursi.

Fungsi adalah konsep dasar yang sangat penting dalam pemrograman untuk modularisasi kode dan memecah masalah menjadi bagian-bagian yang lebih kecil. Fungsi rekursif sangat berguna dalam pemecahan masalah yang bersifat terstruktur berulang.

#### **Latihan Soal : Fungsi Penjumlahan**

**Deskripsi:**\
Buatlah program C++ yang mendefinisikan fungsi **`tambah`** yang menerima dua parameter bertipe integer dan mengembalikan hasil penjumlahan kedua angka tersebut. Program kemudian harus meminta input dari pengguna dan menampilkan hasil penjumlahan menggunakan fungsi tersebut.

**Petunjuk:**

* Deklarasikan dan definisikan fungsi **`tambah`**.
* Minta pengguna untuk memasukkan dua angka.
* Panggil fungsi **`tambah`** dan tampilkan hasilnya.

**Contoh Output:**

```
Masukkan angka pertama: 10
Masukkan angka kedua: 15
Hasil penjumlahan: 25
```
