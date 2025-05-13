---
description: Array (Tipe Data Terstruktur)
---

# Bab 6

## **Array (Tipe Data Terstruktur) dalam C++**

**Array** adalah tipe data terstruktur yang digunakan untuk menyimpan beberapa nilai dengan tipe data yang sama dalam satu variabel. Sebagai contoh, jika Anda ingin menyimpan banyak nilai angka bulat (misalnya 5 nilai), Anda dapat menggunakan array alih-alih mendeklarasikan 5 variabel terpisah.

***

#### **1. Definisi Array**

Array adalah kumpulan data yang memiliki **ukuran tetap** dan **berjenis data yang sama**. Setiap elemen dalam array diakses menggunakan **indeks** yang dimulai dari 0.

**Contoh:**

Jika Anda ingin menyimpan 5 angka bulat, maka Anda bisa membuat array dengan tipe data `int`:

```cpp
int angka[5];
```

Array ini akan menyimpan 5 elemen bertipe `int`, dan elemen pertama berada di indeks `0`, elemen kedua di indeks `1`, dan seterusnya.

***

#### **2. Deklarasi dan Inisialisasi Array**

Deklarasi array dilakukan dengan menyebutkan tipe data array, nama array, dan jumlah elemen yang ingin disimpan.

**Sintaks Deklarasi:**

```cpp
TipeData NamaArray[Ukuran];
```

* **TipeData**: Jenis data yang akan disimpan di dalam array (misalnya `int`, `float`, `char`).
* **NamaArray**: Nama variabel array.
* **Ukuran**: Jumlah elemen yang akan disimpan dalam array.

**Contoh Deklarasi Array:**

```cpp
int angka[5];  // Array bertipe integer dengan 5 elemen
```

**Inisialisasi Array:**

Array dapat diinisialisasi saat deklarasi atau setelahnya.

**Inisialisasi pada saat deklarasi:**

```cpp
int angka[5] = {1, 2, 3, 4, 5};
```

Array ini memiliki 5 elemen dengan nilai yang telah ditentukan, yaitu 1, 2, 3, 4, dan 5.

**Inisialisasi sebagian elemen:**

```cpp
int angka[5] = {1, 2};  // Elemen ke-3, ke-4, dan ke-5 akan diinisialisasi ke 0
```

**Inisialisasi tanpa menyebutkan ukuran:**

Jika Anda tidak menyebutkan ukuran array, maka array akan otomatis disesuaikan dengan jumlah elemen yang diberikan dalam kurung kurawal.

```cpp
int angka[] = {1, 2, 3, 4, 5};  // Ukuran array otomatis menjadi 5
```

***

#### **3. Akses Elemen Array**

Setiap elemen dalam array dapat diakses dengan menggunakan **indeks**. Indeks dimulai dari `0` untuk elemen pertama, `1` untuk elemen kedua, dan seterusnya.

**Sintaks Akses Elemen:**

```cpp
NamaArray[indeks]
```

**Contoh Akses Elemen Array:**

```cpp
int angka[5] = {1, 2, 3, 4, 5};
cout << angka[0];  // Output: 1
cout << angka[3];  // Output: 4
```

* **`angka[0]`** mengakses elemen pertama dari array, yaitu `1`.
* **`angka[3]`** mengakses elemen keempat dari array, yaitu `4`.

***

#### **4. Perulangan Array**

Untuk mengakses atau memanipulasi semua elemen dalam array, kita sering kali menggunakan **perulangan** (looping), seperti `for loop`, `while loop`, atau `do-while loop`.

**Contoh Perulangan dengan `for loop`:**

Misalkan kita ingin menampilkan semua elemen dalam array menggunakan perulangan.

```cpp
#include <iostream>
using namespace std;

int main() {
    int angka[5] = {1, 2, 3, 4, 5};
    
    // Menggunakan for loop untuk menampilkan semua elemen array
    for (int i = 0; i < 5; i++) {
        cout << angka[i] << " ";
    }
    return 0;
}
```

**Output:**

```
1 2 3 4 5
```

**Penjelasan:**

* Perulangan `for` dimulai dari indeks `0` dan berjalan hingga indeks `4` (karena ukuran array adalah 5).
* `angka[i]` digunakan untuk mengakses setiap elemen dalam array berdasarkan nilai `i` (indeks).

***

#### **Ringkasan:**

1. **Definisi Array**: Array adalah struktur data yang menyimpan sejumlah nilai yang memiliki tipe data yang sama.
2. **Deklarasi dan Inisialisasi Array**: Array dideklarasikan dengan menyebutkan tipe data, nama array, dan ukuran array. Array bisa diinisialisasi dengan nilai tertentu.
3. **Akses Elemen Array**: Elemen array diakses menggunakan indeks yang dimulai dari `0`.
4. **Perulangan Array**: Untuk mengakses atau memanipulasi semua elemen dalam array, kita dapat menggunakan perulangan seperti `for loop`.

Dengan menggunakan array, kita dapat menyimpan dan mengolah banyak data dalam satu variabel, yang sangat berguna dalam pemrograman.

#### **Latihan Soal 1: Menampilkan Elemen Array**

**Deskripsi:**\
Buatlah program C++ yang menerima input 5 angka dari pengguna dan menyimpannya dalam array. Kemudian, tampilkan semua elemen array yang telah diinputkan.

**Petunjuk:**

* Deklarasikan array dengan ukuran 5.
* Gunakan `for loop` untuk menerima input angka.
* Gunakan `for loop` untuk menampilkan semua elemen array.

**Contoh Output:**

```
Masukkan angka 1: 10
Masukkan angka 2: 20
Masukkan angka 3: 30
Masukkan angka 4: 40
Masukkan angka 5: 50
Elemen array yang dimasukkan: 10 20 30 40 50
```
