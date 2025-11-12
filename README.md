# project-database

--nama:Mukhtada al khadar
--nim:D0224332
--kelas: D informatika

MariaDB [(none)]> CREATE DATABASE toko;
Query OK, 1 row affected (0.005 sec)

MariaDB [(none)]> USE toko;
Database changed

==========================
-- Membuat tabel
==========================

MariaDB [toko]> CREATE TABLE produk (
    ->     id_produk INT AUTO_INCREMENT PRIMARY KEY,
    ->     nama VARCHAR(50),
    ->     kategori VARCHAR(30),
    ->     harga INT,
    ->     stok INT
    -> );
Query OK, 0 rows affected (0.021 sec)

MariaDB [toko]> CREATE TABLE pelanggan (
    ->     id_pelanggan INT AUTO_INCREMENT PRIMARY KEY,
    ->     nama VARCHAR(50),
    ->     email VARCHAR(50),
    ->     alamat VARCHAR(100),
    ->     hp VARCHAR(20)
    -> );
Query OK, 0 rows affected (0.010 sec)

MariaDB [toko]> CREATE TABLE transaksi (
    ->     id_transaksi INT AUTO_INCREMENT PRIMARY KEY,
    ->     id_pelanggan INT,
    ->     id_produk INT,
    ->     jumlah INT,
    ->     tanggal DATE,
    ->     FOREIGN KEY (id_pelanggan) REFERENCES pelanggan(id_pelanggan),
    ->     FOREIGN KEY (id_produk) REFERENCES produk(id_produk) );
Query OK, 0 rows affected (0.023 sec)

===========================================================
-- Mengisi data ke tabel dan Menampilkan seluruh isi tabel
===========================================================

MariaDB [toko]> INSERT INTO produk (nama, kategori, harga, stok) VALUES
    -> ('Mouse', 'IT', 80000, 20),
    -> ('Keyboard', 'IT', 120000, 15),
    -> ('Laptop', 'IT', 7500000, 10),
    -> ('Monitor', 'IT', 1500000, 8),
    -> ('Speaker', 'IT', 300000, 12),
    -> ('Kabel', 'Aksesoris', 50000, 30),
    -> ('Flashdisk', 'Aksesoris', 70000, 25),
    -> ('Headset', 'Aksesoris', 200000, 18),
    -> ('Powerbank', 'Aksesoris', 150000, 14),
    -> ('Webcam', 'IT', 250000, 10),
    -> ('SSD', 'IT', 1100000, 6),
    -> ('HDD', 'IT', 950000, 8),
    -> ('Tripod', 'Aksesoris', 100000, 10),
    -> ('Tas', 'Aksesoris', 90000, 15),
    -> ('Mousepad', 'Aksesoris', 40000, 25);
Query OK, 15 rows affected (0.020 sec)
Records: 15  Duplicates: 0  Warnings: 0

MariaDB [toko]> select * from produk;
+-----------+-----------+-----------+---------+------+
| id_produk | nama      | kategori  | harga   | stok |
+-----------+-----------+-----------+---------+------+
|         1 | Mouse     | IT        |   80000 |   20 |
|         2 | Keyboard  | IT        |  120000 |   15 |
|         3 | Laptop    | IT        | 7500000 |   10 |
|         4 | Monitor   | IT        | 1500000 |    8 |
|         5 | Speaker   | IT        |  300000 |   12 |
|         6 | Kabel     | Aksesoris |   50000 |   30 |
|         7 | Flashdisk | Aksesoris |   70000 |   25 |
|         8 | Headset   | Aksesoris |  200000 |   18 |
|         9 | Powerbank | Aksesoris |  150000 |   14 |
|        10 | Webcam    | IT        |  250000 |   10 |
|        11 | SSD       | IT        | 1100000 |    6 |
|        12 | HDD       | IT        |  950000 |    8 |
|        13 | Tripod    | Aksesoris |  100000 |   10 |
|        14 | Tas       | Aksesoris |   90000 |   15 |
|        15 | Mousepad  | Aksesoris |   40000 |   25 |
+-----------+-----------+-----------+---------+------+
15 rows in set (0.007 sec)

MariaDB [toko]> INSERT INTO pelanggan (nama, email, alamat, hp) VALUES
    -> ('Ani', 'ani@mail.com', 'Jl. Mawar', '0811'),
    -> ('Budi', 'budi@mail.com', 'Jl. Melati', '0812'),
    -> ('Cici', 'cici@mail.com', 'Jl. Dahlia', '0813'),
    -> ('Doni', 'doni@mail.com', 'Jl. Kenanga', '0814'),
    -> ('Eka', 'eka@mail.com', 'Jl. Flamboyan', '0815'),
    -> ('Fani', 'fani@mail.com', 'Jl. Cempaka', '0816'),
    -> ('Gina', 'gina@mail.com', 'Jl. Sakura', '0817'),
    -> ('Hadi', 'hadi@mail.com', 'Jl. Nusa', '0818'),
    -> ('Ira', 'ira@mail.com', 'Jl. Mawar', '0819'),
    -> ('Joko', 'joko@mail.com', 'Jl. Merpati', '0820'),
    -> ('Kiki', 'kiki@mail.com', 'Jl. Anggrek', '0821'),
    -> ('Lina', 'lina@mail.com', 'Jl. Pahlawan', '0822'),
    -> ('Mira', 'mira@mail.com', 'Jl. Kenari', '0823'),
    -> ('Nino', 'nino@mail.com', 'Jl. Kamboja', '0824'),
    -> ('Oka', 'oka@mail.com', 'Jl. Cemara', '0825');
Query OK, 15 rows affected (0.022 sec)
Records: 15  Duplicates: 0  Warnings: 0

MariaDB [toko]> select * from pelanggan;
+--------------+------+---------------+---------------+------+
| id_pelanggan | nama | email         | alamat        | hp   |
+--------------+------+---------------+---------------+------+
|            1 | Ani  | ani@mail.com  | Jl. Mawar     | 0811 |
|            2 | Budi | budi@mail.com | Jl. Melati    | 0812 |
|            3 | Cici | cici@mail.com | Jl. Dahlia    | 0813 |
|            4 | Doni | doni@mail.com | Jl. Kenanga   | 0814 |
|            5 | Eka  | eka@mail.com  | Jl. Flamboyan | 0815 |
|            6 | Fani | fani@mail.com | Jl. Cempaka   | 0816 |
|            7 | Gina | gina@mail.com | Jl. Sakura    | 0817 |
|            8 | Hadi | hadi@mail.com | Jl. Nusa      | 0818 |
|            9 | Ira  | ira@mail.com  | Jl. Mawar     | 0819 |
|           10 | Joko | joko@mail.com | Jl. Merpati   | 0820 |
|           11 | Kiki | kiki@mail.com | Jl. Anggrek   | 0821 |
|           12 | Lina | lina@mail.com | Jl. Pahlawan  | 0822 |
|           13 | Mira | mira@mail.com | Jl. Kenari    | 0823 |
|           14 | Nino | nino@mail.com | Jl. Kamboja   | 0824 |
|           15 | Oka  | oka@mail.com  | Jl. Cemara    | 0825 |
+--------------+------+---------------+---------------+------+
15 rows in set (0.000 sec)

MariaDB [toko]> INSERT INTO transaksi (id_pelanggan, id_produk, jumlah, tanggal) VALUES
    -> (1, 1, 1, '2025-11-01'),
    -> (2, 2, 1, '2025-11-01'),
    -> (3, 3, 1, '2025-11-02'),
    -> (4, 4, 1, '2025-11-02'),
    -> (5, 5, 2, '2025-11-03'),
    -> (6, 6, 1, '2025-11-03'),
    -> (7, 7, 2, '2025-11-04'),
    -> (8, 8, 1, '2025-11-04'),
    -> (9, 9, 1, '2025-11-05'),
    -> (10, 10, 1, '2025-11-05'),
    -> (11, 11, 1, '2025-11-06'),
    -> (12, 12, 1, '2025-11-06'),
    -> (13, 13, 1, '2025-11-07'),
    -> (14, 14, 1, '2025-11-07'),
    -> (15, 15, 1, '2025-11-08');
Query OK, 15 rows affected (0.010 sec)
Records: 15  Duplicates: 0  Warnings: 0

MariaDB [toko]> select * from transaksi;
+--------------+--------------+-----------+--------+------------+
| id_transaksi | id_pelanggan | id_produk | jumlah | tanggal    |
+--------------+--------------+-----------+--------+------------+
|            1 |            1 |         1 |      1 | 2025-11-01 |
|            2 |            2 |         2 |      1 | 2025-11-01 |
|            3 |            3 |         3 |      1 | 2025-11-02 |
|            4 |            4 |         4 |      1 | 2025-11-02 |
|            5 |            5 |         5 |      2 | 2025-11-03 |
|            6 |            6 |         6 |      1 | 2025-11-03 |
|            7 |            7 |         7 |      2 | 2025-11-04 |
|            8 |            8 |         8 |      1 | 2025-11-04 |
|            9 |            9 |         9 |      1 | 2025-11-05 |
|           10 |           10 |        10 |      1 | 2025-11-05 |
|           11 |           11 |        11 |      1 | 2025-11-06 |
|           12 |           12 |        12 |      1 | 2025-11-06 |
|           13 |           13 |        13 |      1 | 2025-11-07 |
|           14 |           14 |        14 |      1 | 2025-11-07 |
|           15 |           15 |        15 |      1 | 2025-11-08 |
+--------------+--------------+-----------+--------+------------+
15 rows in set (0.000 sec)

================================================================
-- Keyword 'WHERE' untuk tabel produk, pelanggan, dan transaksi
================================================================

MariaDB [toko]> SELECT * FROM produk
    -> WHERE kategori = 'IT';
+-----------+----------+----------+---------+------+
| id_produk | nama     | kategori | harga   | stok |
+-----------+----------+----------+---------+------+
|         1 | Mouse    | IT       |   80000 |   20 |
|         2 | Keyboard | IT       |  120000 |   15 |
|         3 | Laptop   | IT       | 7500000 |   10 |
|         4 | Monitor  | IT       | 1500000 |    8 |
|         5 | Speaker  | IT       |  300000 |   12 |
|        10 | Webcam   | IT       |  250000 |   10 |
|        11 | SSD      | IT       | 1100000 |    6 |
|        12 | HDD      | IT       |  950000 |    8 |
+-----------+----------+----------+---------+------+
8 rows in set (0.006 sec)

MariaDB [toko]> SELECT * FROM pelanggan
    -> WHERE alamat = 'Jl. Mawar';
+--------------+------+--------------+-----------+------+
| id_pelanggan | nama | email        | alamat    | hp   |
+--------------+------+--------------+-----------+------+
|            1 | Ani  | ani@mail.com | Jl. Mawar | 0811 |
|            9 | Ira  | ira@mail.com | Jl. Mawar | 0819 |
+--------------+------+--------------+-----------+------+
2 rows in set (0.000 sec)

MariaDB [toko]> SELECT * FROM transaksi
    -> WHERE jumlah > 1;
+--------------+--------------+-----------+--------+------------+
| id_transaksi | id_pelanggan | id_produk | jumlah | tanggal    |
+--------------+--------------+-----------+--------+------------+
|            5 |            5 |         5 |      2 | 2025-11-03 |
|            7 |            7 |         7 |      2 | 2025-11-04 |
+--------------+--------------+-----------+--------+------------+
2 rows in set (0.002 sec)

==================================================================
-- Keyword 'BETWEEN' untuk tabel produk, pelanggan, dan transaksi
==================================================================

MariaDB [toko]> SELECT * FROM produk
    -> WHERE harga BETWEEN 100000 AND 500000;
+-----------+-----------+-----------+--------+------+
| id_produk | nama      | kategori  | harga  | stok |
+-----------+-----------+-----------+--------+------+
|         2 | Keyboard  | IT        | 120000 |   15 |
|         5 | Speaker   | IT        | 300000 |   12 |
|         8 | Headset   | Aksesoris | 200000 |   18 |
|         9 | Powerbank | Aksesoris | 150000 |   14 |
|        10 | Webcam    | IT        | 250000 |   10 |
|        13 | Tripod    | Aksesoris | 100000 |   10 |
+-----------+-----------+-----------+--------+------+
6 rows in set (0.003 sec)

MariaDB [toko]> SELECT * FROM transaksi
    -> WHERE tanggal BETWEEN '2025-11-02' AND '2025-11-05';
+--------------+--------------+-----------+--------+------------+
| id_transaksi | id_pelanggan | id_produk | jumlah | tanggal    |
+--------------+--------------+-----------+--------+------------+
|            3 |            3 |         3 |      1 | 2025-11-02 |
|            4 |            4 |         4 |      1 | 2025-11-02 |
|            5 |            5 |         5 |      2 | 2025-11-03 |
|            6 |            6 |         6 |      1 | 2025-11-03 |
|            7 |            7 |         7 |      2 | 2025-11-04 |
|            8 |            8 |         8 |      1 | 2025-11-04 |
|            9 |            9 |         9 |      1 | 2025-11-05 |
|           10 |           10 |        10 |      1 | 2025-11-05 |
+--------------+--------------+-----------+--------+------------+
8 rows in set (0.003 sec)

MariaDB [toko]> SELECT * FROM produk
    -> WHERE stok BETWEEN 10 AND 20;
+-----------+-----------+-----------+---------+------+
| id_produk | nama      | kategori  | harga   | stok |
+-----------+-----------+-----------+---------+------+
|         1 | Mouse     | IT        |   80000 |   20 |
|         2 | Keyboard  | IT        |  120000 |   15 |
|         3 | Laptop    | IT        | 7500000 |   10 |
|         5 | Speaker   | IT        |  300000 |   12 |
|         8 | Headset   | Aksesoris |  200000 |   18 |
|         9 | Powerbank | Aksesoris |  150000 |   14 |
|        10 | Webcam    | IT        |  250000 |   10 |
|        13 | Tripod    | Aksesoris |  100000 |   10 |
|        14 | Tas       | Aksesoris |   90000 |   15 |
+-----------+-----------+-----------+---------+------+
9 rows in set (0.000 sec)
