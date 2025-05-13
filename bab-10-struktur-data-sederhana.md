---
description: Struktur Data Sederhana
---

# Bab 10

## **Struktur Data Sederhana dalam C++**

**Struktur data** adalah cara untuk mengatur dan menyimpan data agar dapat diakses dan dimanipulasi secara efisien. Struktur data sederhana yang sering digunakan antara lain **Linked List** dan **Hash Map**.

***

#### **1. Linked List (Singly Linked List)**

**Linked List** adalah struktur data yang terdiri dari serangkaian elemen, yang disebut **node**. Setiap **node** menyimpan dua bagian:

* **Data**: Informasi yang disimpan dalam node.
* **Pointer**: Alamat dari node berikutnya dalam linked list (atau null jika itu adalah node terakhir).

Pada **Singly Linked List**, setiap node hanya memiliki satu pointer yang menunjuk ke node berikutnya (tidak seperti doubly linked list yang memiliki dua pointer, satu menunjuk ke node berikutnya dan satu lagi ke node sebelumnya).

**Konsep Node dan Pointer**

* **Node** adalah struktur data yang memiliki dua bagian:
  1. **Data** yang menyimpan nilai.
  2. **Pointer** yang menyimpan alamat node berikutnya.

```cpp
struct Node {
    int data;       // Data
    Node* next;     // Pointer ke node berikutnya
};
```

* **Pointer** adalah variabel yang menyimpan alamat memori dari objek lain. Dalam linked list, pointer digunakan untuk menghubungkan node satu dengan yang lainnya.

***

**Menambahkan Node**

Untuk menambahkan node pada linked list, kita perlu mengalokasikan memori untuk node baru, mengisinya dengan data, dan mengatur pointer untuk menghubungkan node baru tersebut dengan node sebelumnya.

**Contoh Menambahkan Node di Awal Linked List:**

```cpp
#include <iostream>
using namespace std;

struct Node {
    int data;
    Node* next;
};

void tambahNode(Node*& head, int data) {
    Node* newNode = new Node(); // Alokasi memori untuk node baru
    newNode->data = data;       // Menyimpan data
    newNode->next = head;       // Menunjuk ke node sebelumnya (atau null jika list kosong)
    head = newNode;             // Mengatur head ke node baru
}

void tampilkanList(Node* head) {
    Node* temp = head;
    while (temp != nullptr) {
        cout << temp->data << " ";
        temp = temp->next;
    }
    cout << endl;
}

int main() {
    Node* head = nullptr; // Linked list kosong
    tambahNode(head, 10);
    tambahNode(head, 20);
    tambahNode(head, 30);

    tampilkanList(head); // Output: 30 20 10

    return 0;
}
```

**Penjelasan:**

* Fungsi `tambahNode` menambahkan node baru di awal linked list.
* Fungsi `tampilkanList` digunakan untuk menampilkan data yang ada di linked list.

***

**Menampilkan Data dari Linked List**

Untuk menampilkan data dalam linked list, kita akan mulai dari **head** dan mengikuti pointer dari satu node ke node berikutnya hingga kita mencapai node yang tidak memiliki pointer (null).

Contoh di atas sudah mencakup cara menampilkan data dari linked list menggunakan fungsi `tampilkanList` yang mencetak data setiap node dalam linked list.

***

#### **2. Hash Map Sederhana (Simulasi Menggunakan Array dan Struct)**

**Hash Map** adalah struktur data yang menyimpan data dalam pasangan **key-value**, di mana **key** digunakan untuk mengidentifikasi data, dan **value** adalah data itu sendiri.

Hash Map bekerja dengan menggunakan fungsi hash untuk mengonversi **key** menjadi indeks dalam array tempat **value** disimpan. Untuk menangani **collision** (dua key menghasilkan indeks yang sama), teknik seperti chaining atau open addressing bisa digunakan.

Di bawah ini, kita akan membuat simulasi **Hash Map** dengan menggunakan array dan struktur `struct` untuk menyimpan pasangan **key-value**.

**Konsep Key-Value**

Dalam simulasi Hash Map ini, kita akan menggunakan array untuk menyimpan **key-value** dan memetakan **key** ke indeks array menggunakan fungsi hash sederhana.

```cpp
#include <iostream>
#include <string>
using namespace std;

struct HashMap {
    string key;
    int value;
};

class SimpleHashMap {
private:
    static const int SIZE = 10;
    HashMap map[SIZE];

public:
    SimpleHashMap() {
        // Inisialisasi map dengan key kosong
        for (int i = 0; i < SIZE; i++) {
            map[i].key = "";
            map[i].value = -1;
        }
    }

    int hashFunction(string key) {
        int hashValue = 0;
        for (char ch : key) {
            hashValue += ch;  // Menambahkan nilai ASCII setiap karakter
        }
        return hashValue % SIZE;  // Indeks dalam array
    }

    void insert(string key, int value) {
        int index = hashFunction(key);
        map[index].key = key;
        map[index].value = value;
    }

    int get(string key) {
        int index = hashFunction(key);
        if (map[index].key == key) {
            return map[index].value;
        }
        return -1; // Jika tidak ditemukan
    }

    void display() {
        for (int i = 0; i < SIZE; i++) {
            if (map[i].key != "") {
                cout << "Key: " << map[i].key << " -> Value: " << map[i].value << endl;
            }
        }
    }
};

int main() {
    SimpleHashMap hashmap;
    hashmap.insert("apple", 100);
    hashmap.insert("banana", 200);
    hashmap.insert("grape", 300);

    hashmap.display();

    cout << "Value for 'banana': " << hashmap.get("banana") << endl;  // Output: 200

    return 0;
}
```

**Penjelasan:**

* `SimpleHashMap` adalah kelas yang menyimulasikan hash map.
* Fungsi `hashFunction` menghitung nilai hash dari key.
* Fungsi `insert` digunakan untuk memasukkan pasangan key-value ke dalam hash map.
* Fungsi `get` mengembalikan nilai yang sesuai dengan key yang diberikan.
* Fungsi `display` menampilkan seluruh pasangan key-value yang ada dalam map.

***

#### **Ringkasan:**

* **Linked List** adalah struktur data yang terdiri dari node yang terhubung melalui pointer. Setiap node menyimpan data dan alamat node berikutnya.
* **Hash Map** adalah struktur data yang menyimpan data dalam pasangan key-value, menggunakan fungsi hash untuk menentukan lokasi penyimpanan dalam array.
* Pada **Linked List**, operasi seperti penambahan node dan penelusuran data dilakukan dengan mengelola pointer.
* **Hash Map** menggunakan array untuk menyimpan pasangan key-value dan menggunakan fungsi hash untuk menentukan lokasi penyimpanan berdasarkan key.

#### **Latihan Soal : Linked List - Menambahkan Node di Awal**

**Deskripsi:**\
Buatlah program C++ untuk mengimplementasikan **Singly Linked List**. Program harus memiliki fungsi untuk:

1. Menambahkan node baru di awal linked list.
2. Menampilkan seluruh isi linked list.

**Petunjuk:**

* Gunakan fungsi untuk menambahkan node baru di awal linked list.
* Gunakan pointer untuk menghubungkan setiap node.
* Tampilkan seluruh data dari linked list.

**Contoh Output:**

```
Masukkan 3 nilai untuk linked list:
10 20 30

Data Linked List: 
30 20 10
```
