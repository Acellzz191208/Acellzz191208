---
description: Enkripsi Dasar
---

# Bab 11

## **Enkripsi Dasar**

**Enkripsi** adalah proses mengubah informasi asli (plain text) menjadi bentuk yang tidak dapat dibaca atau dimengerti (cipher text) dengan menggunakan algoritma dan kunci tertentu. Proses ini bertujuan untuk menjaga keamanan data, sehingga hanya pihak yang memiliki kunci yang tepat yang dapat mengembalikannya ke bentuk aslinya (dekripsi).

***

#### **1. Apa Itu Enkripsi?**

Enkripsi adalah teknik dalam kriptografi yang digunakan untuk mengubah pesan atau data asli (plain text) menjadi data yang tidak dapat dibaca atau dipahami oleh orang yang tidak berwenang. Enkripsi menggunakan **algoritma kriptografi** dan **kunci** untuk melakukan transformasi ini.

Enkripsi penting untuk menjaga kerahasiaan data dalam komunikasi digital. Misalnya, saat kita melakukan transaksi online atau mengirim pesan sensitif, enkripsi memastikan bahwa informasi tersebut tidak bisa dibaca oleh pihak yang tidak berhak.

Contoh penerapan enkripsi:

* Menggunakan HTTPS (protokol aman) di situs web.
* Enkripsi pesan pada aplikasi perpesanan (misalnya, WhatsApp).

***

#### **2. Konsep XOR Cipher untuk Enkripsi Sederhana**

**XOR Cipher** adalah metode enkripsi yang sangat sederhana menggunakan operasi **XOR (exclusive OR)**, yang merupakan salah satu operasi logika dasar dalam komputasi. XOR berfungsi untuk membandingkan dua bit dan menghasilkan:

* **0** jika kedua bit yang dibandingkan memiliki nilai yang sama.
* **1** jika kedua bit yang dibandingkan memiliki nilai yang berbeda.

**Operasi XOR** sering digunakan dalam berbagai aplikasi kriptografi karena sifatnya yang mudah dibalik (reversible). Artinya, jika kita mengenkripsi pesan dengan kunci menggunakan XOR, kita dapat mendekripsinya dengan kunci yang sama.

**Bagaimana XOR Bekerja?**

Misalnya, kita ingin mengenkripsi pesan dengan menggunakan operasi XOR. Kita akan mengonversi karakter-karakter dalam pesan menjadi nilai biner (bit), kemudian mengoperasikan XOR dengan kunci yang kita pilih.

Contoh operasi XOR:

* 0 XOR 0 = 0
* 1 XOR 0 = 1
* 0 XOR 1 = 1
* 1 XOR 1 = 0

**Proses Enkripsi XOR:**

1. **Plain text** (misalnya "A") dikonversi menjadi nilai biner. Misalnya, dalam ASCII, "A" memiliki nilai biner **01000001**.
2. Pilih sebuah **kunci** yang juga berupa angka biner (misalnya **01010101**).
3. Operasikan XOR antara **plain text** dan **kunci**:\
   `01000001 XOR 01010101 = 00010100`
4. Hasilnya adalah cipher text dalam bentuk biner, yang tidak dapat dibaca oleh manusia.

**Proses Dekripsi XOR:**

Proses dekripsi menggunakan kunci yang sama. Karena XOR adalah operasi yang reversible (kembali ke nilai awal), kita dapat mendekripsi cipher text dengan cara yang sama:

1. **Cipher text** (misalnya **00010100**) dioperasikan dengan kunci yang sama (misalnya **01010101**).
2. Hasil operasi XOR akan mengembalikan nilai asli.\
   `00010100 XOR 01010101 = 01000001`, yang adalah **A**.

***

**Contoh Implementasi XOR Cipher dalam C++:**

```cpp
#include <iostream>
#include <string>
using namespace std;

// Fungsi untuk enkripsi dan dekripsi menggunakan XOR
string xorCipher(string input, char key) {
    string output = input;
    for (int i = 0; i < input.length(); i++) {
        output[i] = input[i] ^ key;  // Operasi XOR
    }
    return output;
}

int main() {
    string message = "Hello, World!";
    char key = 'K';  // Kunci untuk enkripsi dan dekripsi

    // Enkripsi pesan
    string encrypted = xorCipher(message, key);
    cout << "Encrypted: " << encrypted << endl;

    // Dekripsi pesan
    string decrypted = xorCipher(encrypted, key);
    cout << "Decrypted: " << decrypted << endl;

    return 0;
}
```

**Penjelasan:**

* Fungsi `xorCipher` melakukan operasi XOR antara setiap karakter pesan dengan kunci. Kunci yang digunakan adalah karakter **'K'**.
* Proses enkripsi dan dekripsi sama, hanya membutuhkan kunci yang sama untuk mengembalikan pesan ke bentuk asli.

**Contoh Output:**

```
Encrypted: 1,0*3&
Decrypted: Hello, World!
```

***

#### **Kelebihan dan Kekurangan XOR Cipher**

**Kelebihan:**

* **Sederhana dan Cepat**: XOR cipher sangat mudah diimplementasikan dan cepat dalam prosesnya.
* **Reversible**: Proses enkripsi dan dekripsi menggunakan kunci yang sama, membuatnya mudah dibalik.

**Kekurangan:**

* **Keamanan Lemah**: XOR cipher tidak cukup aman untuk digunakan dalam aplikasi nyata, karena kunci yang digunakan bisa ditebak dengan analisis pola. Terlebih jika kunci yang digunakan pendek atau berulang.
* **Kunci yang Sama untuk Enkripsi dan Dekripsi**: Jika kunci yang digunakan diketahui oleh pihak yang tidak berwenang, maka keamanan data akan terancam.

***

#### **Kesimpulan**

* **Enkripsi** adalah proses untuk mengamankan data dengan mengubahnya menjadi bentuk yang tidak dapat dibaca tanpa kunci yang benar.
* **XOR Cipher** adalah salah satu metode enkripsi yang sederhana, menggunakan operasi XOR untuk mengubah data menjadi cipher text yang tidak dapat dibaca tanpa kunci yang tepat.
* Meskipun XOR Cipher mudah dipahami dan diimplementasikan, enkripsi ini tidak cukup aman untuk aplikasi yang lebih serius, seperti komunikasi atau transaksi yang membutuhkan tingkat keamanan tinggi.

#### **Latihan Soal : Enkripsi dan Dekripsi dengan XOR**

**Deskripsi:**\
Buatlah program C++ untuk mengenkripsi dan mendekripsi pesan menggunakan **XOR Cipher**. Program harus:

1. Menerima sebuah pesan dari pengguna.
2. Menerima sebuah kunci dari pengguna.
3. Mengenkripsi pesan menggunakan kunci yang diberikan.
4. Menampilkan hasil enkripsi.
5. Mendekripsi hasil enkripsi menggunakan kunci yang sama.
6. Menampilkan hasil dekripsi.

**Petunjuk:**

* Gunakan fungsi yang menerima parameter pesan dan kunci.
* Proses enkripsi dan dekripsi menggunakan operasi XOR.

**Contoh Output:**

```
Masukkan pesan: Hello, World!
Masukkan kunci: K

Enkripsi: 1,0*3&
Dekripsi: Hello, World!
```
