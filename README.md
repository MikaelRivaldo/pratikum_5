# Tugas Latihan 

![soal](https://github.com/MikaelRivaldo/pratikum_5/assets/115770247/3ff67d2c-158c-437a-8fa0-ddf1e336ae6b)

# Tugas Buat Table & Lengkapi data pada semua table


# Untuk tb_mahasiwa

![tb_mahasiswa](https://github.com/MikaelRivaldo/pratikum_5/assets/115770247/28dd9872-bb16-47be-bf7a-e6923c3b77c3)

# Untuk tb_dosen

![tb_dosen](https://github.com/MikaelRivaldo/pratikum_5/assets/115770247/7a1ad926-7f9e-4373-ad94-72bce5934c7d)

# Untuk tb_jadwalkrsmahasiswa

![tb_krsmahasiswa](https://github.com/MikaelRivaldo/pratikum_5/assets/115770247/5631d0bd-aa25-4e18-9214-24a924ab84c1)

# Untuk tb_matakuliah

![tb_matakuliah](https://github.com/MikaelRivaldo/pratikum_5/assets/115770247/7f73fdb2-288c-4152-8400-ad2dcaa8861b)

# Untuk tb_jadwalmengajar

![tb_jadwalmengajar](https://github.com/MikaelRivaldo/pratikum_5/assets/115770247/1228fb98-80c8-4409-b306-3759caa2957a)


# 1. Lakukan Join Table Mahasiswa Dan Dosen

# Untuk perintah bisa menggunakan (INNER JOIN)

`SELECT tb_mahasiswa.nim, tb_mahasiswa.nama, tb_mahasiswa.jk, tb_dosen.nama AS "Dosen"
FROM tb_mahasiswa INNER JOIN tb_dosen ON tb_dosen.kd_ds = tb_mahasiswa.kd_ds;`

Hasilnya akan seperti ini :

![jawaban no1](https://github.com/MikaelRivaldo/pratikum_5/assets/115770247/4bd59299-c3c2-4c2c-925e-9719bb740f7c)

>** Note Digunakan untuk menampilkan baris tabel yang memiliki nilai yang sama pada kolom yang terkait.

# Untuk perintah bisa menggunakan (LEFT JOIN)

`SELECT tb_mahasiswa.nim, tb_mahasiswa.nama, tb_mahasiswa.jenis_kelamin, tb_dosen.nama AS "Dosen"
FROM tb_mahasiswa LEFT JOIN tb_dosen ON tb_dosen.kd_ds = tb_mahasiswa.kd_ds;`

Hasilnya akan seperti ini :

![jawaban no2](https://github.com/MikaelRivaldo/pratikum_5/assets/115770247/3043d334-776a-4b67-8d70-f9775030d77b)


>** Note Menampilkan semua data pada table A dan sebagian data pada table B yang bersinggungan dengan table A

# Untuk perintah bisa menggunakan (RIGHT JOIN)

`SELECT tb_mahasiswa.nim, tb_mahasiswa.nama, tb_mahasiswa.jk, tb_dosen.nama AS "Dosen" 
FROM tb_mahasiswa 
RIGHT JOIN tb_dosen ON tb_dosen.kd_ds = tb_mahasiswa.kd_ds;`

Hasilnya akan seperti ini :

![jawaban no3](https://github.com/MikaelRivaldo/pratikum_5/assets/115770247/0e7502fd-0ed3-443b-8cb2-82e080c6bf8c)

>** Note Menampilkan semua data pada table B dan sebagian data pada table A yang bersinggungan dengan table B

# 2 Lakukan join tabel Matakuliah dan Dosen #

# Untuk perintah bisa menggunakan :

`SELECT tb_matakuliah.kd_mk, tb_matakuliah.nama, tb_matakuliah.sks, tb_dosen.nama AS "Dosen Pengampu"
FROM tb_jadwalmengajar
LEFT JOIN tb_matakuliah ON tb_jadwalmengajar.kd_mk = tb_matakuliah.kd_mk
LEFT JOIN tb_dosen ON tb_jadwalmengajar.kd_ds = tb_dosen.kd_ds;`

Hasilnya akan seperti ini :

![jawaban no2](https://github.com/MikaelRivaldo/pratikum_5/assets/115770247/f56b0b0d-fdec-4273-8e51-c1142f2c22fb)

# Untuk perintah bisa menggunakan :

`SELECT tb_jadwalmengajar.hari, tb_jadwalmengajar.jam, tb_jadwalmengajar.ruang, tb_dosen.nama AS "Dosen Pengampu", tb_jadwalmengajar.kd_mk, tb_matakuliah.nama, tb_matakuliah.sks 
FROM tb_jadwalmengajar 
LEFT JOIN tb_matakuliah ON tb_jadwalmengajar.kd_mk = tb_matakuliah.kd_mk 
LEFT JOIN tb_dosen ON tb_jadwalmengajar.kd_ds = tb_dosen.kd_ds;`

Hasilnya akan seperti ini :

![jawaban no2](https://github.com/MikaelRivaldo/pratikum_5/assets/115770247/95a1187a-3201-4f82-bc41-80d606eb9e08)

# 3.Lakukan join tabel KrsMahasiswa, Mahasiswa, Matakuliah, dan Dosen #

# Untuk perintah bisa menggunakan :

`SELECT tb_mahasiswa.nim, tb_mahasiswa.nama AS "nama", tb_matakuliah.nama AS "Matakuliah", tb_matakuliah.sks, tb_dosen.nama AS "Dosen Pengampu"
FROM tb_krsmahasiswa
JOIN tb_mahasiswa ON tb_krsmahasiswa.nim = tb_mahasiswa.nim
JOIN tb_matakuliah ON tb_krsMahasiswa.kd_mk = tb_matakuliah.kd_mk
JOIN tb_dosen ON tb_krsmahasiswa.kd_ds = tb_dosen.kd_ds;`

Hasilnya akan seperti ini :

![jawaban no2](https://github.com/MikaelRivaldo/pratikum_5/assets/115770247/ef7987e9-e698-4651-ab3c-79fffe9a7779)

> ### Join tabel
>  join tabel merujuk pada penggabungan baris-baris data dari dua atau lebih tabel berdasarkan kolom yang memiliki nilai yang sama di setiap tabel. Join tabel memungkinkan kita untuk menggabungkan data dari tabel yang berbeda untuk menghasilkan hasil yang lebih lengkap dan terkait.

> ### Jenis2
> 1. **INNER JOIN** : Menggabungkan baris-baris data dari dua tabel berdasarkan kondisi join yang ditentukan. Hanya baris yang memiliki nilai yang cocok di kedua tabel yang akan dimasukkan ke dalam hasil join.
>
> 2. **LEFT JOIN** : Menggabungkan semua baris dari tabel kiri (left table) dengan baris yang cocok dari tabel kanan (right table) berdasarkan kondisi join. Jika tidak ada nilai yang cocok dalam tabel kanan, kolom-kolom dari tabel kanan akan memiliki nilai NULL dalam hasil join.
>
> 3. **RIGHT JOIN** : Adalah kebalikan dari LEFT JOIN. Ini menggabungkan semua baris dari tabel kanan dengan baris yang cocok dari tabel kiri berdasarkan kondisi join. Jika tidak ada nilai yang cocok dalam tabel kiri, kolom-kolom dari tabel kiri akan memiliki nilai NULL dalam hasil join.
>
> 4. **FULL JOIN** : Menggabungkan semua baris dari kedua tabel, baik dari tabel kiri maupun tabel kanan, berdasarkan kondisi join. Ini akan menghasilkan semua baris dari kedua tabel, dan jika tidak ada nilai yang cocok dalam salah satu tabel, kolom-kolom yang tidak cocok akan memiliki nilai NULL dalam hasil join.
