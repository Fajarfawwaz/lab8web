---

## Praktikum 7 – PHP Dasar

---

**Nama:** ZAENAL MAULANA RIZKI

**NIM:** 312410332

**Kelas:** TI.2A.A.4

**Mata Kuliah:** Pemrograman Web1

**Dosen:** Agung Nugroho, S.Kom., M.Kom.

---

### Persiapan

1. Install **XAMPP** dari [https://www.apachefriends.org](https://www.apachefriends.org)
2. Jalankan **Apache** dan **MySQL** melalui XAMPP Control Panel.
3. Buat folder baru bernama **`lab7_php_dasar`** di direktori:

   ```
   C:\xampp\htdocs\
   ```
4. Buka folder tersebut di **VS Code** atau text editor pilihanmu.

---

### Langkah-langkah Praktikum

#### 1. Membuat File PHP Dasar

**File:** `php_dasar.php`

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>PHP Dasar</title>
</head>
<body>
    <h1>Belajar PHP Dasar</h1>
    <?php
        echo "Hello World";
    ?>
</body>
</html>
```

**Hasil:**
Tampilkan di browser melalui URL:
`php_dasar.php`

<img width="517" height="139" alt="image" src="https://github.com/user-attachments/assets/7ebdfe6c-409c-4962-bcd7-0213046f8ba3" />

---

#### 2. Menambahkan Variabel PHP

**File:** `http://localhost/lab7_php_dasar/php_dasar.php`

```php
<?php
$nim = "312410332";
$nama = "Zaenal Maulana Rizki";
echo "NIM: $nim <br>";
echo "Nama: $nama";
?>
```
**Hasil:**
Tampilkan di browser melalui URL:
`http://localhost/lab7_php_dasar/php_dasar.php`
<img width="574" height="227" alt="image" src="https://github.com/user-attachments/assets/c5a1b89c-9884-4bf8-9c0e-7ae9dfd44286" />

---

#### 3. Predefine Variable `$_GET`

**File:** `latihan2.php`

```php
<?php
echo 'Selamat Datang ' . $_GET['nama'];
?>
```

Akses dengan URL:
`http://localhost/lab7_php_dasar/latihan2.php?nama=Zaenal`

<img width="563" height="108" alt="image" src="https://github.com/user-attachments/assets/7a6eb944-4c84-4db9-8f30-9def7c74c706" />

---

#### 4. Form Input

```php
<!DOCTYPE html>
<html>
<head><title>Form Input</title></head>
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
</body>
</html>
```
### Hasil tampilan nya
<img width="449" height="149" alt="image" src="https://github.com/user-attachments/assets/23704d30-46e0-4afb-8457-f803951a3519" />

---

#### 5. Operator Aritmatika

```php
<?php
$gaji = 3000000;
$pajak = 0.1;
$thp = $gaji - ($gaji * $pajak);
echo "Gaji Sebelum Pajak = Rp. $gaji <br>";
echo "Gaji Bersih = Rp. $thp";
?>
```
### Hasil tampilan nya 
<img width="433" height="111" alt="image" src="https://github.com/user-attachments/assets/c77a8af7-1732-466f-92c9-b2a00c8be218" />

---

#### 6. Struktur Kondisi dan Perulangan

**IF ELSE:**

```php
<?php
$hari = date("l");
if ($hari == "Sunday") echo "Minggu";
elseif ($hari == "Monday") echo "Senin";
else echo "Hari lainnya";
?>
```
### Hasil tampilan nya 
<img width="461" height="93" alt="image" src="https://github.com/user-attachments/assets/6cce736c-d011-4a01-b247-e5721d07d4af" />

**FOR Loop:**

```php
<?php
for ($i=1; $i<=10; $i++) {
    echo "Perulangan ke-$i <br>";
}
?>
```
### Hasil tampilan nya
<img width="482" height="206" alt="image" src="https://github.com/user-attachments/assets/25880dad-2531-4bce-a2d3-3c7d6e72e43f" />

---

### TUGAS 

<img width="587" height="291" alt="image" src="https://github.com/user-attachments/assets/512e720c-7557-4af6-98e0-2ade8e657d0a" />

---


**File:** `form_biodata.php`

```php
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Form Biodata</title>
</head>
<body>
<h2>Form Biodata</h2>
<form method="post">
    Nama: <input type="text" name="nama"><br>
    Tanggal Lahir: <input type="date" name="tgl_lahir"><br>
    Pekerjaan:
    <select name="pekerjaan">
        <option value="Programmer">Programmer</option>
        <option value="Designer">Designer</option>
        <option value="Manager">Manager</option>
    </select><br><br>
    <input type="submit" value="Kirim">
</form>

<?php
if ($_POST) {
    $nama = $_POST['nama'];
    $tgl = $_POST['tgl_lahir'];
    $pekerjaan = $_POST['pekerjaan'];

    $umur = date_diff(date_create($tgl), date_create('today'))->y;

    switch ($pekerjaan) {
        case 'Programmer': $gaji = 8000000; break;
        case 'Designer': $gaji = 6000000; break;
        case 'Manager': $gaji = 10000000; break;
        default: $gaji = 0; break;
    }

    echo "<h3>Hasil Output:</h3>";
    echo "Nama: $nama <br>";
    echo "Umur: $umur tahun <br>";
    echo "Pekerjaan: $pekerjaan <br>";
    echo "Gaji: Rp. " . number_format($gaji, 0, ',', '.');
}
?>
</body>
</html>
```
### Hasil tampilannya
---

<img width="538" height="301" alt="image" src="https://github.com/user-attachments/assets/58b6c6f5-e34f-4fa7-9ff8-7f04306d2d17" />

---
