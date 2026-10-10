# Pewarisan dan Polimorfisme Geometri – Latihan OOP Java

Latihan pemrograman berorientasi objek (OOP) dalam bahasa Java yang menerapkan konsep pewarisan (*inheritance*), hierarki kelas, dan penggunaan konstanta kelas. Program mengelola bentuk geometri mulai dari bentuk dasar (`Bentuk`), turunan dua dimensi (`BujurSangkar` dan `Lingkaran`), hingga bangun ruang tiga dimensi (`Silinder`).

Tujuan latihan ini adalah memperkuat pemahaman tentang relasi antarkelas, *method overriding*, enkapsulasi, dan pemanggilan konstruktor induk dengan `super`.

---

## 📂 Struktur File

```plaintext
Tugas-PBO-Geometri/
├── Bentuk.java         # Kelas induk: atribut dan metode umum warna
├── BujurSangkar.java   # Turunan Bentuk: sisi dan luas bujur sangkar
├── Lingkaran.java      # Turunan Bentuk: radius, Math.PI, dan luas lingkaran
├── Silinder.java       # Turunan Lingkaran: tinggi dan volume silinder
└── Main.java           # Kelas utama: menu interaktif dengan Scanner
```

---

## 🏗️ Desain dan Relasi Kelas

```plaintext
Bentuk
├── BujurSangkar
└── Lingkaran
    └── Silinder
```

| Kelas | Induk | Atribut Tambahan | Metode Utama |
|---|---|---|---|
| `Bentuk` | – | `warna` | `getWarna()`, `setWarna()`, `printInfo()` |
| `BujurSangkar` | `Bentuk` | `sisi` | `hitungLuas()`, `printInfo()` |
| `Lingkaran` | `Bentuk` | `radius` | `hitungLuas()`, `printInfo()` |
| `Silinder` | `Lingkaran` | `tinggi` | `hitungVolume()`, `printInfo()` |

---

## 🛠️ Prasyarat

- Java Development Kit (JDK) 8 atau lebih baru
- Text editor atau IDE (IntelliJ IDEA, VS Code, Eclipse, dll.)

## ▶️ Cara Menjalankan

1. Simpan kelima file (`Bentuk.java`, `BujurSangkar.java`, `Lingkaran.java`, `Silinder.java`, `Main.java`) dalam satu folder, misalnya `Tugas-PBO-Geometri`.

2. Buka terminal/CMD dan masuk ke folder tersebut:
```bash
   cd path/to/Tugas-PBO-Geometri
```

3. Kompilasi semua file sekaligus:
```bash
   javac *.java
```

4. Jalankan program:
```bash
   java Main
```

---

## 💡 Penjelasan Kode dan Konsep OOP

### 1. `Bentuk.java`
- **Atribut:** `warna` (`String`), bersifat `protected` agar dapat diakses kelas turunan.
- **Konstruktor:** menginisialisasi nilai warna.
- **Metode:**
  - `getWarna()` dan `setWarna(String warna)`: mengambil dan mengubah warna.
  - `printInfo()`: menampilkan informasi dasar bentuk.

### 2. `BujurSangkar.java`
- **Atribut:** `sisi` (`double`).
- **Konstruktor:** menerima `sisi` dan `warna`, lalu meneruskan `warna` ke induk dengan `super(warna)`.
- **Metode:**
  - `hitungLuas()`: menghitung luas bujur sangkar.
  - `printInfo()`: ber-anotasi `@Override`, menampilkan informasi bujur sangkar beserta luasnya.

### 3. `Lingkaran.java`
- **Atribut:**
  - `radius` (`double`): jari-jari lingkaran.
  - `PHI` (`static final double`): konstanta kelas bernilai `3.14`, digunakan untuk perhitungan luas.
- **Konstruktor:** menginisialisasi `radius` dan meneruskan `warna` ke induk via `super(warna)`.
- **Metode:**
  - `hitungLuas()`: menghitung luas dengan rumus π × radius².
  - `printInfo()`: menampilkan informasi lingkaran beserta luasnya.

### 4. `Silinder.java`
- **Atribut:** `tinggi` (`double`).
- **Konstruktor:** menginisialisasi `tinggi`, `radius`, dan `warna` dengan memanggil konstruktor `Lingkaran`.
- **Metode:**
  - `hitungVolume()`: mengalikan hasil `hitungLuas()` dari `Lingkaran` dengan `tinggi`.
  - `printInfo()`: menampilkan informasi silinder beserta volumenya.

### 5. `Main.java`
Menyediakan menu interaktif berbasis teks dengan `java.util.Scanner`. Pengguna dapat membuat objek Bujur Sangkar, Lingkaran, atau Silinder, memasukkan data, dan langsung melihat hasilnya.

---

## 🚀 Hasil Eksekusi

**Menu 1 – Bujur Sangkar**

<img width="362" height="252" alt="Menu 1 - Bujur Sangkar" src="https://github.com/user-attachments/assets/273c84f9-f007-4b88-9e9b-3633b1edc482" />

**Menu 2 – Lingkaran**

<img width="356" height="245" alt="Menu 2 - Lingkaran" src="https://github.com/user-attachments/assets/dba00e4f-23b2-48b8-b7b9-3fa52acaac79" />

**Menu 3 – Silinder**

<img width="441" height="271" alt="Menu 3 - Silinder" src="https://github.com/user-attachments/assets/2b292f3a-2df5-4b14-860e-4ddfac6156bd" />

**Menu 4 – Keluar**

<img width="347" height="205" alt="Menu 4 - Keluar" src="https://github.com/user-attachments/assets/19716039-df27-44bc-8334-fec0961084b0" />

---

## 👩‍💻 Author

| | |
|---|---|
| **Nama** | Ghaitsa Rizky Amalia |
| **NIM** | F1D02510052 |
