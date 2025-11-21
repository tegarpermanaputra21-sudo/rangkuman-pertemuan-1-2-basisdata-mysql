# 📘 Rangkuman Modul Praktikum Basis Data (Bab 1–2)

Rangkuman ini dibuat berdasarkan **Modul Praktikum Basis Data – MySQL**, mencakup materi **Bab 1** (Konversi ERD ke Relasi) dan **Bab 2** (Dasar Database & DDL).  
File ini disusun ulang menjadi format dokumentasi yang rapi dan mudah dipahami.

---

## 📄 Sumber Modul

Modul asli dapat diakses pada file berikut:

[📘 MODUL PRAKTIKUM BASIS DATA.pdf](sandbox:/mnt/data/MODUL%20PRAKTIKUM%20BASIS%20DATA.pdf)

---

# 📚 BAB 1 — Konversi ER Diagram ke Skema Relasi

Bab 1 berisi penjelasan tentang cara mengonversi *Entity Relationship Diagram (ERD)* menjadi **skema relasi**, dan dari skema relasi menjadi **tabel fisik** pada database.

---

## 🔑 Konsep Dasar

### **Entitas (Entity)**
Objek nyata yang dapat diidentifikasi.  
➡️ Dikoversi menjadi **tabel**.

### **Atribut (Attribute)**
Karakteristik pada entitas.  
➡️ Dikoversi menjadi **kolom**.

### **Primary Key (PK)**
Atribut unik sebagai identitas baris.  
➡️ Tetap menjadi PK pada tabel.

### **Relasi (Relationship)**
Hubungan antar entitas.  
➡️ Menjadi **Foreign Key** atau **tabel relasi**.

### **Kardinalitas**
Jenis jumlah hubungan:
- **1 — 1**
- **1 — N**
- **N — M**

---

## 🔄 Aturan Konversi ERD → Relasi

### **1. Entitas Kuat → Tabel**
- Setiap entitas kuat menjadi tabel
- Atribut → kolom
- PK tetap sama

---

### **2. Atribut Komposit**
Atribut yang terdiri dari beberapa bagian → dipecah menjadi kolom terpisah  
Contoh:  
`Alamat → (jalan, kota, provinsi)`

---

### **3. Atribut Multivalue**
Karena dapat berisi banyak nilai → harus dibuat **tabel baru**

---

### **4. Entitas Lemah**
- Menjadi tabel baru  
- PK gabungan (PK entitas kuat + atribut lemah)

---

### **5. Relasi 1 — 1**
FK ditempatkan pada salah satu tabel, biasanya entitas yang lebih lemah.

---

### **6. Relasi 1 — N**
FK diletakkan di entitas pada sisi **N**.

---

### **7. Relasi 1 — N dengan atribut relasi**
Jika relasi memiliki atribut, harus dibuat **tabel relasi**.

---

### **8. Relasi N — M**
Selalu menghasilkan **tabel relasi** yang memuat:
- FK dari dua entitas
- Atribut relasi (jika ada)

---

### **9. Unary Relationship**
Relasi dalam satu entitas:
- 1 — 1 → FK pada tabel yang sama  
- N — M → tabel relasi tambahan

---

### **10. Ternary Relationship**
Hubungan antara 3 entitas → menghasilkan **empat tabel**:
- 3 tabel entitas  
- 1 tabel relasi  

---

### **11. Generalisasi / Spesialisasi (ISA)**
Pendekatan:
- Superclass + Subclass  
- Hanya subclass (menggabungkan semua atribut)

---

### **12. Agregasi**
Relasi kompleks → menghasilkan tabel relasi tambahan.

---

## 🧪 Studi Kasus: Skema Apotik

Konversi ERD Apotik menghasilkan banyak tabel, seperti:
- `pasien`  
- `dokter`  
- `resep`  
- `detail_resep`  
- `obat`  
- `kategori_obat`  
- `pegawai`  
- `pembayaran`  

---

# 📚 BAB 2 — Pengantar Basis Data & DDL MySQL

Bab 2 membahas konsep dasar basis data, DBMS, serta perintah DDL pada MySQL.

---

## 🔑 Konsep Dasar

### **Basis Data**
Kumpulan data yang disusun terstruktur agar mudah diakses dan dikelola.

### **DBMS (Database Management System)**
Software untuk mengelola database, seperti:
- MySQL  
- PostgreSQL  
- MariaDB  
- Oracle  
- SQL Server  

### **MySQL**
DBMS populer dengan karakteristik:
- Open-source  
- Menggunakan SQL  
- Cepat dan stabil  
- Banyak digunakan pada web server  

---

# 💻 Mengakses MySQL via CLI

### **Login MySQL (Windows / XAMPP)**

```bash
cd C:\xampp\mysql\bin
mysql -u root -p
