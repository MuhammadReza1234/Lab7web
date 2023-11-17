<h1 <p align="center"><b>Praktikum 7</b></p></h1> 

**Nama: Rini Ariza**

**NIM: 312210337**

**Kelas: TI.22.A3**

---

Persiapan
Untuk memulai membuat kode php, perlu disiapkan web server dan interpreter PHP
terlebih dahulu. Web servar yang kita gunakan adalah Apache 2 dan interpreter PHP 7.
Untuk memudahkan proses praktikum, kita gunakan aplikasi bundle web server yaitu
XAMPP.

---

## Install XAMPP
Unduh XAMPP dari https://www.apachefriends.org/download.html dan pilih versi
portable untuk memudahkan proses installasi. Kemudian extract file tersebut, seusikan
direktorinya (misal: c:\xampp).

![Screenshot (442)](https://github.com/rniarzz/Lab7web/assets/115542704/9dbf02a5-5a03-4094-9076-7bc6319b0896)

---

## Konfigurasi Web Server
• Konfigurasi Apache
Untuk konfigurasi HTTP server, seperti port yang digunakan akses HTTP, modul
yang diaktifkan, lokasi document root, dll.
Lokasi file: \xampp\apache\conf\httpd.conf

• Konfigrasi PHP
Untuk konfigurasi perilaku engine PHP yang berefek pada keamanan dan performa.
Seperti batas maksimal waktu eksekusi script, batas file yang dapat diupload, error
reporting, dll.
Lokasi file: \xampp\php\php.ini

• Konfigrasi MySql
Konfigurasi server MySQL, seperti administrator user, port, timezone, dll.
Lokasi file: \xampp\mysql\bin\my.ini

![Screenshot (443)](https://github.com/rniarzz/Lab7web/assets/115542704/2ce9e395-302e-45ec-aa31-1e25936b901d)

---

Uji coba apakah server sudah berkerja dengan baik
http://127.0.0.1 atau http://localhost

Tampil halaman utama XAMPP jika server sudah berkerja dengan baik.

• Dokumen Website
Semua file website tempatkan di direktori: \xampp\htdocs\

• Database MySQL
Direktori: \xampp\mysql\
Manajemen database: http://localhost/phpmyadmin

## Memulai PHP
Buat folder lab7_php_dasar pada root directory web server (d:\xampp\htdocs)

![Screenshot (444)](https://github.com/rniarzz/Lab7web/assets/115542704/a08cdfe8-10a9-4ab9-af57-a9da8b05a0e0)

---

Kemudian untuk mengakses direktory tersebut pada web server dengan mengakses URL:
http://localhost/lab7_php_dasar/

![Screenshot (376)](https://github.com/rniarzz/Lab7web/assets/115542704/ae2860f7-0561-4fad-b5ee-1cb3395de2eb)

---

## PHP Dasar
Buat file baru dengan nama php_dasar.php pada directory tersebut. Kemudian buat
kode seperti berikut.

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>PHP Dasar</title>
</head>
<body>

```

Kemudian untuk mengakses hasilnya melalui URL:
http://localhost/lab7_php_dasar/php_dasar.php

# Hasil output
![Screenshot (377)](https://github.com/rniarzz/Lab7web/assets/115542704/db80362d-f7bf-4d06-88ae-064c3d49a0ef)

---

## Variable PHP
Menambahkan variable pada program.

```php
<?php
    $nim = "312210337";
    $nama = 'Rini Ariza';
    echo "NIM : " . $nim . "<br>";
    echo "Nama : $nama";
    ?>

```

# Hasil output

![Screenshot (378)](https://github.com/rniarzz/Lab7web/assets/115542704/7878aa91-1960-4bd7-b16a-f06ec84da024)

---

Predefine Variable $_GET

```php
 <h1>Predefine Variable</h1>
    <?php
    echo "Selamat Datang " . $_GET ["nama"];
    ?>
</body>
</html>

```

# Hasil output

![Screenshot (379)](https://github.com/rniarzz/Lab7web/assets/115542704/ac384dce-6d0c-4dbe-916d-b19763c4c75b)

---

Untuk mengaksesnya gunakan URL: http://localhost/lab7_php_dasar/php_dasar.php?nama=Rini%20Ariza

## Membuat Form Input

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>PHP Dasar</title>
</head>
<body>
<h2>Form Input</h2>
<form method="post">
    <label>Nama: </label>
    <input type="text" name="nama">
    <input type="submit" value="Kirim">
</form>
<?php
echo 'Selamat Datang ' . $_POST['nama'];
?>

```

# Hasil output

![Screenshot (380)](https://github.com/rniarzz/Lab7web/assets/115542704/4259b9fc-7a12-4784-a3ed-ee063daf2395)

---

# Operator

```php
<h2>Operator</h2>
<?php
$gaji = 1000000;
$pajak = 0.1;
$thp = $gaji - ($gaji*$pajak);
echo "Gaji sebelum pajak = Rp. $gaji <br>";
echo "Gaji yang dibawa pulang = Rp. $thp";
?>

```

# Kondisi IF

```php
<h2>Kondisi IF</h2>
<?php
$nama_hari = date("l");
if ($nama_hari == "Sunday") {
    echo "Minggu";
} elseif ($nama_hari == "Monday") {
    echo "Senin";
} else {
    echo "Selasa";
}
?>

```

#  Kondisi Switch

```php
<h2>Kondisi Switch</h2>
<?php
$nama_hari = date("l");
switch ($nama_hari) {
    case "Sunday":
        echo "Minggu";
        break;
    case "Monday":
        echo "Senin";
        break;
    case "Tuesday":
        echo "Selasa";
        break;
    default:
        echo "Sabtu";
    }
?>

```

# Hasil output

<img width="960" alt="Cuplikan layar 2023-11-16 223147" src="https://github.com/rniarzz/Lab7web/assets/115542704/8687a568-1ab7-4e93-a6df-66875c60879b">

# Perulangan for

```php
<h2>Perulangan for</h2>
<?php
echo "Perulangan 1 sampai 10 <br />";
for ($i=1; $i<=10; $i++) {
    echo "Perulangan ke: " . $i . '<br />';
}
echo "Perulangan Menurun dari 10 ke 1 <br />";
for ($i=10; $i>=1; $i--) {
    echo "Perulangan ke: " . $i . '<br />';
}
?>

```

# Hasil output

<img width="960" alt="Cuplikan layar 2023-11-16 223525" src="https://github.com/rniarzz/Lab7web/assets/115542704/f0058202-16d5-4314-a64e-c0cfd65d4214">

---

# Perulangan while

```php
<h2>Perulangan while</h2>
<?php
echo "Perulangan 1 sampai 10 <br />";
$i=1;
while ($i<=10) {
    echo "Perulangan ke: " . $i . '<br />';
    $i++;
}
?>

```

# Hasil output

<img width="960" alt="Cuplikan layar 2023-11-16 223947" src="https://github.com/rniarzz/Lab7web/assets/115542704/c2352591-58a8-493d-87b8-9693952a3e08">

---

# Perulangan dowhile

```php
<h2>Perulangan dowhile</h2>
<?php
echo "Perulangan 1 sampai 10 <br />";
$i=1;
do {
echo "Perulangan ke: " . $i . '<br />';
$i++;
} while ($i<=10);
?>
</body>
</html>

```

# Hasil output

<img width="958" alt="Cuplikan layar 2023-11-16 224149" src="https://github.com/rniarzz/Lab7web/assets/115542704/d37d2bb1-dd41-4403-a075-506ce11e340a">

---

## Pertanyaan dan Tugas

Buatlah program PHP sederhana dengan menggunakan form input yang menampilkan nama, tanggal lahir dan pekerjaan. Kemudian tampilkan outputnya dengan menghitung umur berdasarkan inputan tanggal lahir. Dan pilihan pekerjaan dengan gaji yang berbeda-beda sesuai pilihan pekerjaan.

# Input

```php
<!DOCTYPE html>
<html lang="en">

    <head>
        <title>Form Input</title>
        <meta charset="utf-8">

        <!-- CSS -->
        <style>
        body {
            width: 100%;
            height: 100vh;
            margin: 0;
            font-family: tahoma;
            font-size: 16px;
        }
        h1, p {
            margin: 1em auto;
            text-align: center;
        }
        form {
            width: 60vw;
            max-width: 500px;
            min-width: 300px;
            margin: 0 auto;
            padding-bottom: 2em;
            }
        label {
            display: block;
            margin: 0.5rem 0;
        }
        button[type="submit"] {
            display: block;
            width: 60%;
            margin: 1em auto;
            height: 2em;
            font-size: 1.1rem;
            background-color: #e0daca;
            border-color: white;
            min-width: 300px;
        }
        </style>
    </head>

    <body>
        <h1 id="title">Survey Formulir Pekerjaan dan Gaji</h1>
        <p id="description"><i>Melansir dari situs <a href="https://id.indeed.com/career/php-developer/salaries"> indeed.com</a></i></p>

        <form id="survey-form" action="" method="POST">
            <fieldset>
                <label>Nama: 
                    <input type="text" name="nama" required/>
                </label>
                <label>Tanggal lahir: 
                    <input type="date" name="date">
                </label>
                <label>Pekerjaan: 
                    <label>
                    <input type="radio" name="job" value="0"/>Database Administrator
                    </label>
                    <label>
                    <input type="radio" name="job" value="1"/>Software Developer
                    </label>
                    <label>
                    <input type="radio" name="job" value="2"/>Web Developer
                    </label>
                </label>
                <button type="submit" name="submit">Kirim</button>
            </fieldset>
            <fieldset>
                <?php
                if( isset($_POST['submit']))
                {
                    $nama = $_POST['nama'];
                    $date = $_POST['date'];
                    $job = $_POST['job'];


                    $date_user = new DateTime($date);
                    $today =  new DateTime('today');
                    $usia = $today->diff($date_user)->y;

                    $job_array = ["Database Administrator","Software Developer","Web Developer"];
                    $salary_array = ["Rp. 5.300.000","Rp. 5.400.000","Rp. 4.800.000"];


                    echo "Halo, ".$nama."<br>Kamu lahir pada tanggal ".$date.", Usia mu ".$usia." tahun";
                    echo "<br>Pekerjaan yang kamu pilih adalah ".$job_array[(int)$job].", dengan penghasilan kurang lebih ".$salary_array[(int)$job];
                }
                ?>
            </fieldset>
        </form>
    </body>
</html>

```

# Hasil output

![Screenshot (440)](https://github.com/rniarzz/Lab7web/assets/115542704/bb65f331-7c30-4955-8a19-78a1a8f1b518)

![Screenshot (441)](https://github.com/rniarzz/Lab7web/assets/115542704/ad5a76e6-0849-4535-98a5-5a57a834cbdc)

---

<h1 <p align="center"><b>======== Sekian Terima Kasih ==========</b></p></h1>
