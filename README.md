# pratikum5

Richie Pranata 

312410451

TI.24.A.5
# Pengenalan Program
``` pyhton
print("\nProgram Input Nilai")
print("===================")
```
Baris ini mencetak judul program ke layar.
# Class Student
``` Pyhton
class Student:
    def __init__(self, nim, nama, tugas, uts, uas):
        self.nim = nim
        self.nama = nama
        self.tugas = tugas
        self.uts = uts
        self.uas = uas
        self.akhir = self.calculate_final_grade()

    def calculate_final_grade(self):
        return round((self.tugas * 0.3) + (self.uts * 0.35) + (self.uas * 0.35), 2)
```
Class Student merepresentasikan data seorang mahasiswa.

__init__ adalah metode khusus untuk menginisialisasi atribut mahasiswa, yaitu:

nim: Nomor Induk Mahasiswa.

nama: Nama mahasiswa.

tugas, uts, uas: Nilai tugas, UTS, dan UAS.

akhir: Nilai akhir, dihitung dengan metode calculate_final_grade.

calculate_final_grade adalah metode untuk menghitung nilai akhir menggunakan bobot:

Tugas: 30%

UTS: 35%

UAS: 35%

# Fungsi Utility

``` pyhton
def display_menu():
    print("\n[(L)ihat, (T)ambah, (U)bah, (H)apus, (C)ari (K)eluar]: ", end=' ')
```
Fungsi ini menampilkan menu pilihan kepada pengguna.

# display_students
``` pyhton
def display_students(students):
    print("\nDaftar Nilai")
    print("=" * 84)
    print(f"| {'NO':<3} | {'NIM':<10} | {'NAMA':<30} | {'TUGAS':<6} | {'UTS':<4} | {'UAS':<4} | {'AKHIR':<5} |")
    print("=" * 84)
    if not students:
        print(f"| {'TIDAK ADA DATA':^80} |")
    else:
        for i, student in enumerate(students, start=1):
            print(f"| {i:<3} | {student.nim:<10} | {student.nama:<30} | {student.tugas:<6} | {student.uts:<4} | {student.uas:<4} | {student.akhir:<5} |")
    print("=" * 84)
```
Menampilkan data mahasiswa yang tersimpan dalam list students dalam format tabel.

Jika data kosong, akan menampilkan pesan "TIDAK ADA DATA".

# find_student_index

``` pyhton
def find_student_index(students, nim):
    for index, student in enumerate(students):
        if student.nim == nim:
            return index
    return None
```
Mencari indeks mahasiswa dalam daftar students berdasarkan NIM. Jika tidak ditemukan, mengembalikan None.

# Fungsi main
``` pyhton
students = []
```
students adalah list yang digunakan untuk menyimpan data mahasiswa dalam bentuk objek Student.

# Tambah Data (T)
```pyhton
nim = input("\nNIM: ")
nama = input("Nama: ")
tugas = int(input("Nilai Tugas: "))
uts = int(input("Nilai UTS: "))
uas = int(input("Nilai UAS: "))
students.append(Student(nim, nama, tugas, uts, uas))
```
# Lihat Data (L)
``` pyhton
display_students(students)
```
Menampilkan data mahasiswa dalam bentuk tabel.

# Ubah Data (U)
``` pyhton
nim = input("\nMasukkan NIM mahasiswa yang akan diubah: ")
index = find_student_index(students, nim)
if index is not None:
    nama = input("Nama baru: ")
    tugas = int(input("Nilai Tugas baru: "))
    uts = int(input("Nilai UTS baru: "))
    uas = int(input("Nilai UAS baru: "))
    students[index] = Student(nim, nama, tugas, uts, uas)
    print("Data mahasiswa berhasil diubah.")
else:
    print("Mahasiswa dengan NIM tersebut tidak ditemukan.")
```
Mencari mahasiswa berdasarkan NIM menggunakan find_student_index.

Jika ditemukan, mengganti data mahasiswa sesuai input baru.

# Hapus Data (H)
``` pyhton
nim = input("\nMasukkan NIM mahasiswa yang akan dihapus: ")
index = find_student_index(students, nim)
if index is not None:
    del students[index]
    print("Data mahasiswa berhasil dihapus.")
else:
    print("Mahasiswa dengan NIM tersebut tidak ditemukan.")
```
Mencari dan menghapus mahasiswa berdasarkan NIM.

# Cari Data (C)
``` pyhton
nim = input("\nMasukkan NIM mahasiswa yang dicari: ")
index = find_student_index(students, nim)
if index is not None:
    student = students[index]
    print(f"\nNIM: {student.nim}\nNama: {student.nama}\nNilai Tugas: {student.tugas}\nNilai UTS: {student.uts}\nNilai UAS: {student.uas}\nNilai Akhir: {student.akhir}")
else:
    print("Mahasiswa dengan NIM tersebut tidak ditemukan.")
```
Mencari mahasiswa berdasarkan NIM dan menampilkan detailnya.

# Keluar Program (K)
``` pyhton
elif choice == 'k':
    break
```
Menghentikan program.

# Eksekusi Program
``` pyhton
if __name__ == "__main__":
    main()
```
Menjalankan fungsi main jika file dijalankan langsung

# Flowchart
![foto](https://raw.githubusercontent.com/rich-pro12/foto1/330072d109974874ff0c6e870091b516ff550232/FLOWCHART%20PRATIKUM-5.png)

# Hasil Eksekusi
![Foto]()












