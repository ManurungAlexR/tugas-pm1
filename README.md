Nama  : Manurung Alex Roger

Kelas : TI.2O.A.2

NIM   : 312010478

1. API EDIT

<?php
    require_once(' . -/config/koneksi_db. php');
    $data - json_decode (file_get_contents (" php: //input"));

    if ($data->id! =nul 1)
        $id                = $data-&gt;id;
        $nama_mahasiswa    = $data-&gt;nama_mahasiswa;
        $nim               = $data-&gt;nim;

        $sql $conn-&gt;prepare("UPDATE produk SET nama produk=?, tipe produk=?, harga=? stok=? HERE d=?"):
        11 pada bind parameter ssddd itu artinya tipe data yang dikitimkan s5- string, d= double, i=intefer.
        $sq1-gt;bind_param(' ssddd', Snama_produk, $tipe _produk, Sharga, $stok, $id);
        $sql-&gt;execute () ;
        1f ($sql)
            echo json_encode(array( "RESPONSE* gti sUCCESS")):
        Jelse{
        )
        Jelse {
            echo json_encode (array(' RESPONSE gti 'FATLED"));
        echo "GAGAL";
        
.  
2. API TAMBAH

<?php
    require_once('../config/koneksi_db.php');
    if (isset($_POST['nama_mahasiswa']) && isset($_POST['harga']) &amp;&amp; isset($_POST['stok'])) {
        $nama_mahasiswa = $_POST['nama_mahasiswa'];
        $nim  = $_POST['nim'];
        $sql = $conn->gt;prepare("INSERT INTO produk (nama_mahasiswa, nim) VALUES (?, ?");
        $sql-&gt;bind_param('ssdd', $nama_mahasiswa, $nim);
        $sql-&gt;execute();
        if ($sql) {
         //echo json_encode(array('RENPONSE' =&gt; 'FAILED'));
         echo json_encode(array('RESPONSE' => 'SUCCESS'));
         //header("location:../readapi/tampil.php);
         } else {
         echo "GAGAL";
         }
    }
    
?>



3. API TAMPIL ALL


<?php
    require_once('../config/koneksi_db.php');
    if (isset($_POST['nama_mahasiswa']) && isset($_POST['harga']) &amp;&amp; isset($_POST['stok'])) {
        $nama_mahasiswa = $_POST['nama_mahasiswa'];
        $nim  = $_POST['nim'];
        $sql = $conn->gt;prepare("INSERT INTO produk (nama_mahasiswa, nim) VALUES (?, ?");
        $sql-&gt;bind_param('ssdd', $nama_mahasiswa, $nim);
        $sql-&gt;execute();
        if ($sql) {
         //echo json_encode(array('RENPONSE' =&gt; 'FAILED'));
         echo json_encode(array('RESPONSE' => 'SUCCESS'));
         //header("location:../readapi/tampil.php);
         } else {
         echo "GAGAL";
         }
    }
    
?>



4. KONEKSI.DB

<?php
    define('HOST', 'localhost');
    define('USER', 'root');
    define('DB', 'latihan_restful');
    //password disesuaikan dengan akses ke database masing-masing
    define('PASS', '');
    $conn = new mysqli(HOST,USER,PASS,DB) or die('Koneksi error untuk mengakses database');
?>
