# Praktikum_PemWeb7

### Pertanyaan dan Tugas

Buatlah program PHP sederhana dengan menggunakan form input yang menampilkan nama, tanggal lahir dan pekerjaan. Kemudian tampilkan outputnya dengan menghitung umur berdasarkan inputan tanggal lahir. Dan pilihan pekerjaan dengan gaji yang berbeda-beda sesuai pilihan pekerjaan.

#### Kode PHP Sederhana Form Input
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Form Input</title>
</head>
<body>
    <h2>Form Input</h2>
    <form method="post">
        <label>Nama: </label>
        <input type="text" name="nama" required><br>

        <label>Tanggal Lahir: </label>
        <input type="date" name="tgl_lahir" required><br>

        <label>Pekerjaan: </label>
        <select name="pekerjaan" required>
            <option value="programmer">Programmer</option>
            <option value="designer">Designer</option>
            <option value="manager">Manager</option>
        </select><br>

        <input type="submit" value="Submit">
    </form>

    <?php
    if ($_SERVER["REQUEST_METHOD"] == "POST") {
        $nama = $_POST["nama"];
        $tgl_lahir = $_POST["tgl_lahir"];
        $pekerjaan = $_POST["pekerjaan"];

        // Hitung umur berdasarkan tanggal lahir
        $tanggal_lahir = new DateTime($tgl_lahir);
        $today = new DateTime();
        $umur = $today->diff($tanggal_lahir)->y;

        // Tentukan gaji berdasarkan pekerjaan
        switch ($pekerjaan) {
            case "programmer":
                $gaji = 5000000;
                break;
            case "designer":
                $gaji = 4500000;
                break;
            case "manager":
                $gaji = 7000000;
                break;
            default:
                $gaji = 0;
        }

        // Tampilkan output
        echo "<h2>Output</h2>";
        echo "Nama: $nama<br>";
        echo "Umur: $umur tahun<br>";
        echo "Pekerjaan: $pekerjaan<br>";
        echo "Gaji: Rp " . number_format($gaji, 0, ',', '.') . "<br>";
    }
    ?>
</body>
</html>
```
![code](https://github.com/RadjaAzukio/Praktikum_PemWeb7/assets/115551911/8238cf82-8e34-4929-834a-477902f0cef7)

##### Output

![image](https://github.com/RadjaAzukio/Praktikum_PemWeb7/assets/115551911/cdade0cf-e679-486e-a1d9-e73967a83faa)
![image](https://github.com/RadjaAzukio/Praktikum_PemWeb7/assets/115551911/1a194da7-448f-4e07-9c75-b96c3e9c2c1e)
![image](https://github.com/RadjaAzukio/Praktikum_PemWeb7/assets/115551911/4ff87b7e-1b55-4509-9efb-248ccd000e6c)

