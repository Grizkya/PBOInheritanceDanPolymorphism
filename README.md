# Pewarisan dan Polimorfisme Geometri OOP Exercise

Tugas ini merupakan latihan pemrograman berorientasi objek (OOP) dalam bahasa Java yang menerapkan konsep pewarisan (*inheritance*), hierarki kelas, serta pemanfaatan konstanta kelas. Program ini mengelola berbagai bentuk geometri mulai dari bentuk dasar (`Bentuk`), turunan dua dimensi (`BujurSangkar` dan `Lingkaran`), hingga bangun ruang tiga dimensi (`Silinder`). Tugas ini dikembangkan untuk memperkuat pemahaman mengenai relasi antar kelas, metode *overriding*, enkapsulasi, serta penggunaan konstruktor induk melalui kata kunci `super`.

---

## 📂 Struktur File dan Folder
Plaintext

Tugas-PBO-Geometri/
│
├── Bentuk.java         # Kelas induk yang mengelola atribut dan metode umum warna
├── BujurSangkar.java   # Kelas turunan dari Bentuk untuk mengelola sisi dan luas bujur sangkar
├── Lingkaran.java      # Kelas turunan dari Bentuk untuk mengelola radius, konstanta Math.PI, dan luas lingkaran
├── Silinder.java       # Kelas turunan dari Lingkaran untuk mengelola tinggi dan volume silinder
└── Main.java           # Kelas utama (main) yang menyediakan menu interaktif dengan Scanner untuk pengujian

---

## 🏗️ Desain & Relasi Kelas (UML Relationship)
Arsitektur program ini menerapkan konsep *Inheritance* (Pewarisan) dalam OOP:

- **`Bentuk`** berfungsi sebagai kelas super (*superclass*) yang memiliki atribut dasar `warna` beserta getter, setter, dan metode `printInfo()`.
- **`BujurSangkar`** memperluas (*extends*) kelas `Bentuk`, menambahkan atribut `sisi`, perhitungan luas, serta penyesuaian metode `printInfo()`.
- **`Lingkaran`** memperluas (*extends*) kelas `Bentuk`, menambahkan atribut `radius`, konstanta `Math.PI`, perhitungan luas, serta penyesuaian metode `printInfo()`.
- **`Silinder`** memperluas (*extends*) kelas turunan `Lingkaran`, menambahkan atribut `tinggi`, perhitungan volume berbasis luas alas lingkaran, serta penyesuaian metode `printInfo()`.

---

## 🛠️ Prasyarat & Cara Menjalankan (Prerequisites & Usage)
Pastikan perangkat komputer Anda telah terinstal perangkat lunak berikut sebelum menjalankan program:

- Java Development Kit (JDK) versi 8 atau versi terbaru.
- Text editor atau IDE pilihan Anda (seperti IntelliJ IDEA, VS Code, atau Eclipse).

**Langkah-langkah Kompilasi dan Eksekusi via Terminal/CMD:**
1. Simpan kelima file kelas (`Bentuk.java`, `BujurSangkar.java`, `Lingkaran.java`, `Silinder.java`, dan `Main.java`) ke dalam satu direktori folder yang sama (misalnya `Tugas-PBO-Geometri`).
2. Buka terminal atau Command Prompt, lalu arahkan direktori ke folder tersebut:
   ```bash
   cd path/to/Tugas-PBO-Geometri

```

3. Kompilasi seluruh berkas kode sumber Java secara bersamaan:
```bash
javac *.java

```


4. Jalankan program utama melalui kelas eksekusi `Main`:
```bash
java Main

```



---

## 💡 Penjelasan Kode & Konsep OOP

1. **`Bentuk.java`**
* **Atribut:** `warna` (tipe data `String`) dengan hak akses `protected` agar dapat diakses langsung oleh kelas-kelas turunannya.
* **Konstruktor:** Menginisialisasi nilai warna pada objek bentuk.
* **Metode Utama:**
* `getWarna()` & `setWarna(String warna)`: Mengambil dan mengubah informasi warna.
* `printInfo()`: Menampilkan informasi dasar bentuk berwarna.




2. **`BujurSangkar.java`**
* **Atribut:** `sisi` (tipe data `double`).
* **Konstruktor:** Menerima parameter sisi dan warna, serta meneruskan parameter warna ke kelas induk menggunakan `super(warna)`.
* **Metode Utama:**
* `hitungLuas()`: Menghitung luas bujur sangkar.
* `printInfo()`: Menggunakan anotasi `@Override` untuk menampilkan informasi spesifik bujur sangkar beserta hasil perhitungan luasnya.




3. **`Lingkaran.java`**
* **Atribut:** `radius` (tipe data `double`) serta pemanfaatan konstanta bawaan Java `Math.PI` untuk akurasi perhitungan.
* **Konstruktor:** Menginisialisasi radius dan mewariskan atribut warna ke kelas induk via `super(warna)`.
* **Metode Utama:**
* `hitungLuas()`: Menghitung luas lingkaran menggunakan rumus $\pi \times radius^2$.
* `printInfo()`: Menampilkan informasi lingkaran beserta hasil luasnya.




4. **`Silinder.java`**
* **Atribut:** `tinggi` (tipe data `double`).
* **Konstruktor:** Menginisialisasi `tinggi`, `radius`, dan `warna` dengan memanggil konstruktor kelas induknya (`Lingkaran`).
* **Metode Utama:**
* `hitungVolume()`: Menghitung volume silinder dengan mengalikan hasil `hitungLuas()` dari kelas `Lingkaran` dengan `tinggi`.
* `printInfo()`: Menampilkan informasi silinder beserta volume akhirnya.




5. **`Main.java`**
* Menyediakan menu interaktif berbasis teks menggunakan `java.util.Scanner` yang memungkinkan pengguna memilih pembuatan objek (Bujur Sangkar, Lingkaran, atau Silinder), memasukkan input dinamis, dan melihat hasil eksekusi program secara langsung.



---

## 🚀 Hasil Eksekusi (Output)

Ketika program `Main.java` dijalankan dan menu interaktif dioperasikan, contoh keluaran pada terminal adalah sebagai berikut:

Menu 1 (Bujur Sangkar)
<img width="362" height="252" alt="image" src="https://github.com/user-attachments/assets/273c84f9-f007-4b88-9e9b-3633b1edc482" />

Menu 2 (Lingkaran)
<img width="356" height="245" alt="image" src="https://github.com/user-attachments/assets/dba00e4f-23b2-48b8-b7b9-3fa52acaac79" />

Menu 3 (Silinder)
<img width="441" height="271" alt="image" src="https://github.com/user-attachments/assets/2b292f3a-2df5-4b14-860e-4ddfac6156bd" />

Menu 4 (Keluar)
<img width="347" height="205" alt="image" src="https://github.com/user-attachments/assets/19716039-df27-44bc-8334-fec0961084b0" />

---

## 👩‍💻 Author

Nama: Ghaitsa Rizky Amalia

NIM: F1D02510052
