# Pertemuan 12 - File I/O dan Error Handling
- Nama: Tantri Widya Solehati
NIM: 2225250114
Kelas: 3F
## Tujuan
Membaca, memvalidasi, mengolah, dan menulis data file dengan Python.
## Format File Input
NIM,nilai
## Cara Menjalankan
python3 tugas/rekap_nilai_file.py
## Error yang Ditangani
- FileNotFoundError
- ValueError
## Test Case
| Kasus | Kondisi | Hasil yang diharapkan | Hasil aktual | Status |
|-------|---------|-----------------------|--------------|--------|
| Normal | Semua baris valid | Semua record diproses dan rekap benar. | Semua record diproses dan rekap benar. | Sesuai |
| File hilang | nilai.txt tidak tersedia | Pesan file tidak ditemukan; program tidak crash. | Pesan file tidak ditemukan; program tidak crash. | Sesuai |
| Nilai invalid | A004,abc | Baris invalid dilewati/dilaporkan; record lain tetap diproses. | Baris invalid dilewati/dilaporkan; record lain tetap diproses. | Sesuai |
| Baris kosong | Ada baris kosong | Baris kosong dilewati. | Baris kosong dilewati. | Sesuai |
| Batas lulus | Nilai 60 | Dihitung sebagai lulus. | Dihitung sebagai lulus. | sesuai |
## Refleksi
- Satu error yang ditemukan yaitu ketika file yang ingin dibaca tidak ditemukan.
```Python
try:
with open(nama_file, "r", encoding="utf-8") as file:
...
except FileNotFoundError:
print(f"File tidak ditemukan: {nama_file}")
```
Cara program menanganinya
1. Program menggunakan blok try-except:
2. Program mencoba membuka file dengan open().
3. Jika file ada, proses pembacaan berjalan normal.
4. Jika file tidak ada, Python menghasilkan FileNotFoundError.
Blok except FileNotFoundError menangkap error tersebut sehingga program tidak langsung berhenti (crash).
5. Program menampilkan pesan:
File tidak ditemukan: data/nilai.txt
6. Fungsi kemudian mengembalikan list kosong:
```Python
return data
karena variabel data sejak awal bernilai:
```Python
data = []