# TUGAS PEMOGRAMAN PERTEMUAN 6
NAMA : muhammad hanif ramadhani
KELAS: TI25C5
NIM  : 312510291
Daftar Isi

Kasus 1: Program Pemesanan Tiket Bioskop
Kasus 2: Program Kalkulator Sederhana

Kasus 1: Program Pemesanan Tiket Bioskop
Deskripsi
Program ini menghitung harga tiket bioskop dengan ketentuan:

Tiket Reguler: Rp 50.000
Tiket VIP: Rp 100.000
Diskon 20% untuk member

Algoritma

START
Input tipe tiket (reguler/vip) dari user
Input status member (y/t) dari user
Tentukan harga tiket:

JIKA tipe_tiket = "reguler" MAKA harga = 50000
JIKA tipe_tiket = "vip" MAKA harga = 100000
JIKA TIDAK, harga = 0 (invalid)

Hitung diskon:

JIKA status_member = "y" MAKA diskon = 20%
JIKA TIDAK, diskon = 0%

Hitung total: total = harga - (harga × diskon)
Tampilkan detail pemesanan dan total harga
END

Flowchart
        ┌─────────┐
        │  START  │
        └────┬────┘
             │
        ┌────▼────────────────────┐
        │ Input tipe_tiket        │
        │ Input status_member     │
        └────┬────────────────────┘
             │
        ┌────▼─────────────────┐
        │ tipe_tiket ==        │
        │ "reguler"?           │
        └─┬────────────────┬───┘
      Ya  │                │ Tidak
          │                │
    ┌─────▼─────┐    ┌─────▼─────┐
    │ harga =   │    │ tipe ==   │
    │ 50000     │    │ "vip"?    │
    └─────┬─────┘    └─┬───────┬─┘
          │         Ya │       │ Tidak
          │       ┌────▼────┐  │
          │       │ harga = │  │
          │       │ 100000  │  │
          │       └────┬────┘  │
          │            │    ┌──▼──────┐
          │            │    │ harga = │
          │            │    │ 0       │
          │            │    └──┬──────┘
          └────────┬───┴───────┘
                   │
            ┌──────▼──────────┐
            │ status_member   │
            │ == "y"?         │
            └──┬──────────┬───┘
           Ya  │          │ Tidak
         ┌─────▼────┐  ┌──▼──────┐
         │ diskon = │  │ diskon =│
         │ 0.2      │  │ 0       │
         └─────┬────┘  └──┬──────┘
               └──────┬───┘
                      │
            ┌─────────▼─────────┐
            │ total = harga -   │
            │ (harga × diskon)  │
            └─────────┬─────────┘
                      │
            ┌─────────▼─────────┐
            │ Tampilkan detail  │
            │ dan total harga   │
            └─────────┬─────────┘
                      │
                 ┌────▼────┐
                 │   END   │
                 └─────────┘
Kode Program
python#!/usr/bin/python3

print("="*50)
print("KASUS 1: PROGRAM PEMESANAN TIKET BIOSKOP")
print("="*50)

# Input dari user
tipe_tiket = input("Masukkan tipe tiket (reguler/vip): ").lower()
status_member = input("Apakah Anda memiliki kartu member? (y/t): ").lower()

# Menentukan harga tiket berdasarkan tipe
if tipe_tiket == "reguler":
    harga_tiket = 50000
elif tipe_tiket == "vip":
    harga_tiket = 100000
else:
    print("Tipe tiket tidak valid!")
    harga_tiket = 0

# Menghitung diskon menggunakan operator ternary
diskon = 0.2 if status_member == "y" else 0

# Menghitung total harga
total_harga = harga_tiket - (harga_tiket * diskon)

# Menampilkan hasil
print("\n" + "="*50)
print("DETAIL PEMESANAN")
print("="*50)
print(f"Tipe Tiket     : {tipe_tiket.capitalize()}")
print(f"Harga Tiket    : Rp {harga_tiket:,}")
print(f"Status Member  : {'Ya' if status_member == 'y' else 'Tidak'}")
print(f"Diskon         : {int(diskon * 100)}%")
print(f"Total Bayar    : Rp {int(total_harga):,}")
print("="*50)
Screenshot Hasil Eksekusi
Contoh 1: Tiket Reguler dengan Member
==================================================
KASUS 1: PROGRAM PEMESANAN TIKET BIOSKOP
==================================================
Masukkan tipe tiket (reguler/vip): reguler
Apakah Anda memiliki kartu member? (y/t): y

==================================================
DETAIL PEMESANAN
==================================================
Tipe Tiket     : Reguler
Harga Tiket    : Rp 50,000
Status Member  : Ya
Diskon         : 20%
Total Bayar    : Rp 40,000
==================================================
Contoh 2: Tiket VIP tanpa Member
==================================================
KASUS 1: PROGRAM PEMESANAN TIKET BIOSKOP
==================================================
Masukkan tipe tiket (reguler/vip): vip
Apakah Anda memiliki kartu member? (y/t): t

==================================================
DETAIL PEMESANAN
==================================================
Tipe Tiket     : Vip
Harga Tiket    : Rp 100,000
Status Member  : Tidak
Diskon         : 0%
Total Bayar    : Rp 100,000
==================================================
Penjelasan Kode

Input Data:

Menggunakan .lower() untuk mengkonversi input ke huruf kecil agar tidak case-sensitive


Struktur Kondisi if-elif-else:

Memeriksa tipe tiket yang dipilih
Menentukan harga berdasarkan tipe

Operator Ternary:

diskon = 0.2 if status_member == "y" else 0
Sintaks singkat untuk memberikan nilai diskon

Perhitungan:

Total = harga - (harga × diskon)

Format Output:

Menggunakan f-string untuk format yang rapi
:, untuk menambahkan separator ribuan

Kasus 2: Program Kalkulator Sederhana
Deskripsi
Program kalkulator yang dapat melakukan operasi aritmatika dasar:

Penjumlahan (+)
Pengurangan (-)
Perkalian (*)
Pembagian (/)

Algoritma

START
Input angka pertama dari user
Input angka kedua dari user
Input operator (+, -, *, /) dari user
Proses perhitungan:

JIKA operator = "+" MAKA hasil = angka1 + angka2
JIKA operator = "-" MAKA hasil = angka1 - angka2
JIKA operator = "*" MAKA hasil = angka1 × angka2
JIKA operator = "/" MAKA

JIKA angka2 ≠ 0 MAKA hasil = angka1 ÷ angka2
JIKA TIDAK, tampilkan error

JIKA TIDAK, operator tidak valid

Tampilkan hasil perhitungan
END

Flowchart
        ┌─────────┐
        │  START  │
        └────┬────┘
             │
        ┌────▼─────────────┐
        │ Input angka1     │
        │ Input angka2     │
        │ Input operator   │
        └────┬─────────────┘
             │
        ┌────▼────────┐
        │ operator == │
        │ "+"?        │
        └─┬────────┬──┘
      Ya  │        │ Tidak
    ┌─────▼────┐  │
    │ hasil =  │  │
    │ a1 + a2  │  │
    └─────┬────┘  │
          │    ┌──▼───────┐
          │    │ operator │
          │    │ == "-"?  │
          │    └─┬──────┬─┘
          │   Ya │      │ Tidak
          │ ┌────▼───┐  │
          │ │ hasil= │  │
          │ │ a1-a2  │  │
          │ └────┬───┘  │
          │      │   ┌──▼───────┐
          │      │   │ operator │
          │      │   │ == "*"?  │
          │      │   └─┬──────┬─┘
          │      │  Ya │      │ Tidak
          │      │ ┌───▼───┐  │
          │      │ │ hasil=│  │
          │      │ │ a1*a2 │  │
          │      │ └───┬───┘  │
          │      │     │   ┌──▼───────┐
          │      │     │   │ operator │
          │      │     │   │ == "/"?  │
          │      │     │   └─┬──────┬─┘
          │      │     │  Ya │      │ Tidak
          │      │     │ ┌───▼────┐ │
          │      │     │ │ angka2 │ │
          │      │     │ │ != 0?  │ │
          │      │     │ └─┬────┬─┘ │
          │      │     │Ya │    │No │
          │      │  ┌────▼─┐ ┌─▼───┐│
          │      │  │hasil=│ │Error││
          │      │  │a1/a2 │ └─┬───┘│
          │      │  └────┬─┘   │    │
          │      │       │  ┌──▼────▼──┐
          │      │       │  │ Operator │
          │      │       │  │ Invalid  │
          │      │       │  └──┬───────┘
          └──────┴───────┴─────┘
                 │
          ┌──────▼────────┐
          │ Tampilkan     │
          │ hasil         │
          └──────┬────────┘
                 │
            ┌────▼────┐
            │   END   │
            └─────────┘
Kode Program
python#!/usr/bin/python3

print("="*50)
print("KASUS 2: PROGRAM KALKULATOR SEDERHANA")
print("="*50)

# Input dari user
angka1 = float(input("Masukkan angka pertama: "))
angka2 = float(input("Masukkan angka kedua: "))
operator = input("Masukkan operator (+, -, *, /): ")

# Melakukan operasi berdasarkan operator
if operator == "+":
    hasil = angka1 + angka2
    operasi = "Penjumlahan"
elif operator == "-":
    hasil = angka1 - angka2
    operasi = "Pengurangan"
elif operator == "*":
    hasil = angka1 * angka2
    operasi = "Perkalian"
elif operator == "/":
    if angka2 != 0:
        hasil = angka1 / angka2
        operasi = "Pembagian"
    else:
        print("Error: Pembagian dengan nol tidak diperbolehkan!")
        hasil = None
        operasi = "Pembagian"
else:
    print("Operator tidak valid!")
    hasil = None
    operasi = "Tidak Valid"

# Menampilkan hasil
print("\n" + "="*50)
print("HASIL PERHITUNGAN")
print("="*50)
print(f"Operasi  : {operasi}")
print(f"Angka 1  : {angka1}")
print(f"Angka 2  : {angka2}")
if hasil is not None:
    print(f"Hasil    : {hasil}")
print("="*50)
Screenshot Hasil Eksekusi
Contoh 1: Penjumlahan
==================================================
KASUS 2: PROGRAM KALKULATOR SEDERHANA
==================================================
Masukkan angka pertama: 15
Masukkan angka kedua: 7
Masukkan operator (+, -, *, /): +

==================================================
HASIL PERHITUNGAN
==================================================
Operasi  : Penjumlahan
Angka 1  : 15.0
Angka 2  : 7.0
Hasil    : 22.0
==================================================
Contoh 2: Pembagian
==================================================
KASUS 2: PROGRAM KALKULATOR SEDERHANA
==================================================
Masukkan angka pertama: 100
Masukkan angka kedua: 4
Masukkan operator (+, -, *, /): /

==================================================
HASIL PERHITUNGAN
==================================================
Operasi  : Pembagian
Angka 1  : 100.0
Angka 2  : 4.0
Hasil    : 25.0
==================================================
Contoh 3: Error Pembagian dengan Nol
==================================================
KASUS 2: PROGRAM KALKULATOR SEDERHANA
==================================================
Masukkan angka pertama: 50
Masukkan angka kedua: 0
Masukkan operator (+, -, *, /): /
Error: Pembagian dengan nol tidak diperbolehkan!

==================================================
HASIL PERHITUNGAN
==================================================
Operasi  : Pembagian
Angka 1  : 50.0
Angka 2  : 0.0
==================================================
Contoh 4: Perkalian
==================================================
KASUS 2: PROGRAM KALKULATOR SEDERHANA
==================================================
Masukkan angka pertama: 12
Masukkan angka kedua: 5
Masukkan operator (+, -, *, /): *

==================================================
HASIL PERHITUNGAN
==================================================
Operasi  : Perkalian
Angka 1  : 12.0
Angka 2  : 5.0
Hasil    : 60.0
==================================================
Penjelasan Kode

Input Data:

Menggunakan float() untuk menerima bilangan desimal
Input operator sebagai string

Struktur Kondisi if-elif-else:

Memeriksa operator yang dipilih secara berurutan
Setiap kondisi melakukan operasi aritmatika yang sesuai

Validasi Pembagian:

Nested if untuk memeriksa pembagian dengan nol
Mencegah error division by zero

Error Handling:

Menggunakan hasil = None untuk menandai operasi invalid
Menampilkan pesan error yang jelas

Output:

Menampilkan nama operasi, kedua angka, dan hasil
Menggunakan conditional untuk menampilkan hasil hanya jika valid
Cara Menjalankan Program
Clone repository:

bash   git clone [URL_REPOSITORY]
   cd labpy02

Jalankan program:

bash   python3 praktikum2.py

Ikuti instruksi input yang muncul di layar

Struktur Repository
labpy02/
├── praktikum2.py          # File utama program
├── README.md              # Dokumentasi (file ini)
└── screenshots/           # Folder screenshot hasil eksekusi
    ├── tiket_reguler.png
    ├── tiket_vip.png
    ├── kalkulator_tambah.png
    ├── kalkulator_bagi.png
    └── kalkulator_error.png
