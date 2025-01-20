# PerancanganPerangkatLUnaK
PERANCANGAN SISTEM INVENTORY BARANG 
PADA BENGKEL BERBASIS WEB
Mata Kuliah Perancangan Perangkat Lunak

 

Disusun oleh:
Haycal Pramudia (2211310030)
Lesti Hanaviani (2211310037)
M. Agung Permana (2211310040)






PROGRAM STUDI S1 TEKNOLOGI INFORMASI
FAKULTAS TEKNIK
UNIVERSITAS TANGERANG RAYA
2024
KATA PENGANTAR

Puji syukur kehadirat Allah SWT yang telah melimpahkan Rahmat, Taufiq serta Hidayah-Nya sehingga dapat menyelesaikan laporan perancangan ini dengan judul “Perancangan Sistem Inventory Pada Bengkel Berbasis Web” dan tak lupa sholawat serta salam penulis haturkan kepada Nabi Muhammad SAW yang dinantikan syafa’atnya kelak di Yaumul Qiyamah.
 
DAFTAR ISI
KATA PENGANTAR	
DAFTAR ISI	
BAB I PENDAHULUAN
1.1	Latar Belakang	
1.2	Rumusan Masalah	
1.3	Tujuan	
BAB II PERANCANGAN DAN IMPLEMENTASI
1.1	Skema Hardware	
1.2	Skema Software	
1.3	Skema Database	
1.4	Skema Aktor	
1.5	Coding dan Tampilan	
BAB III PENUTUP
1.1	Kesimpulan	
1.2	Saran 	
 
BAB I
PENDAHULUAN

1.1	Latar Belakang
Perkembangan teknologi informasi akan memberikan dampak pada bisnis sebuah perusahaan. Untuk dapat mencapai efisiensi dan efektivitas proses bisnis, sebuah bidang usaha mengharapkan dengan penggunakan teknologi informasi akan dapat membantu bidang usaha dalam mencapai goals dari perusahaan serta dapat mencapai nilai strategis dan competitive,advantegedari penggunaan TI (Lantip dan Rianto, 2011). Sistem informasi harus dapat menyediakan informasi untuk orang yang tepat dalam waktu yang tepat serta dalam format dan jumlah yang tepat dan sesuai denga kebutuhan informasi.Sistem informasi akan memberikan manfaat bagi user, sistem, organisasi, dan level strategis dalam bidang usaha Kegiatan bisnis dalam dunia otomotif adalah pelayanan jasa perbaikan atau seringkali disebut dengan nama bengkel, dari dulu sampai saat ini keberadaannya sudah merupakan suatu bagian yang penting atau dapat dikatakan tidak mungkin terpisahkan lagi. Kegiatan ini sudah menjadi keperluan penunjang untuk dunia otomotif baik itu berupa sepeda motor.
Bengkel merupakan suatu jenis wirausaha kecil dan menengah yang bergerak dalam bidang jasa pelayanan perbaikan sepeda motor. Dalam menyajikan data yang dibutuhkan oleh bengkel masih manual, dalam mengendalikan persediaan stok dan keluar masuknya stok sparepart motor masih kurang efisien.









1.2	Rumusan Masalah
Terdapat beberapa permasalahan, yaitu terkadang terjadinya kesalahan informasi data stok karena pengolahan stok sparepart yang kurang akurat. 

1.3	Tujuan
Tujuan dari pembuatan laporan ini adalah merancang mengenai penjualan terdiri dari inventory stok barang-barang sparepart motor yang terjual, sehingga dapat membantu memecahkan masalah persediaan barang di bengkel.
 
BAB II
PERANCANGAN DAN IMPLEMENTASI

2.1	Skema Hardware
Skema hardware untuk sistem inventory stok sparepart motor pada bengkel ini menggambarkan infrastruktur fisik yang dibutuhkan untuk menjalankan sistem inventarisasi sparepart motor dengan efisien. Berikut beberapa komponen hardware yang diperlukan:
1.	Server dan Web Database
Menyimpan aplikasi website dan database untuk pengelolaan data sparepart, yang dapat dihosting server fisik di bengkel, sehingga website atau aplikasi berbasis web dapat diakses oleh pengguna kapan saja tanpa harus memikirkan tentang penyimpanan teknis server.
2.	Laptop, PC, atau Tablet Pengguna
Untuk mengakses aplikasi website melalui browser web seperti Chrome, Firefox, atau edge. Dan melakukan pengelolaan stok barang sparepart motor.
3.	Jaringan lokal dan Internet
Menyediakan koneksi jaringan untuk semua perangkat dalam sistem, yang menghubungkan komputer atau laptop ke server. Biasa memakai jaringan lokal (LAN) atau melalui internet.

2.2	Skema Software
Skema software dalam perancangan sistem inventory barang berbasis web untuk sebuah sistem bengkel yang akan mencakup berbagai komponen perangkat lunak yang saling berhubungan. Dibawah ini adalah skema software yang menjelaskann bagaimana semua komponen perangkat lunak tersebut bekerjasama dalam satu sistem. Berikut adalah komponen utama dalam skema software:
1.	User Interface
Pengguna (admin atau pekerja bengkel) untuk mengakses, menerima input, dan menampilkan informaasi yang dibuat menggunakan CSS dan PHP. Aplikasi web akan menampilkan dashboard dengan informasi stok sparepart, menambah atau mengedit data sparepart.

2.	Database 
Database memakai MySQL untuk menyimpan semua data yang diperlukan oleh sistem, seperti data sparepart, pengguna, dan supplier. Relasi antar tabel didatabase akan menghubungkan data sparepart dengan data pengguna.
3.	Web Server
Web server yang menyajikan aplikasi web kepada pengguna yang mengaksesnya melalui browser.

2.3	Skema Database
1.	Class Diagram

2.4	Skema Aktor
1.	Use Case
 
 
2.	Sequence Diagram
 
 


3.	Activity Diagram
Pelanggan	Bag. penjualan	Bag. administrasi	Pemilik bengkel

 

2.5	Coding
A.Index.php
<?php
session_start();
if(empty($_SESSION['username'])){
  header("location:login.php");
}
?>
<!DOCTYPE html>

<html>

<head>
  <title>Bengkel</title>

  <!-- Panggil Bootstrap -->
  <link href="bootstrap/css/bootstrap.css" rel="stylesheet">
  <!-- <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.6/css/bootstrap.min.css" /> -->
  <script src="jquery/jquery.min.js"></script>
  <script src="jquery/bootstrap.min.js"></script>
  <style type="text/css">
    body{
      background-color: #f0f5f5;
    }
  </style>
</head>

<body>
  <nav class="navbar navbar-default navbar-static-top">
    <div class="container">
      <div class="navbar-header">
       <!-- Skrip dibawah ini akan aktif ketika posisi mobile -->
       <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#navbar" aria-expanded="false" aria-controls="navbar">
         <span class="sr-only">Toggle navigation</span>
         <span class="icon-bar"></span>
         <span class="icon-bar"></span>
         <span class="icon-bar"></span>
       </button>
       <a class="navbar-brand" href="index.php">Bengkel Online</a>
     </div>
     <!-- Daftar menu yang diinginkan-->
     <div id="navbar" class="navbar-collapse collapse">
      <ul class="nav navbar-nav">

        <li>
          <a href="index.php">
            <span class="glyphicon glyphicon-home"></span> Beranda
          </a>
        </li>

        <li class="dropdown">
          <a href="#" class="dropdown-toggle" data-toggle="dropdown">
            <span class="glyphicon glyphicon-folder-open"></span> &nbsp;Mastering Data 
            <b class="caret"></b>
          </a>
          <ul class="dropdown-menu">

            <li>
             <a href="index.php?lihat=jasa/index">
               <span class="glyphicon glyphicon-user"></span> &nbsp;Master Jasa</a>
             </li>
             <li>
               <a href="index.php?lihat=sparepart/index">
                 <span class="glyphicon glyphicon-lock"></span> &nbsp;Master Sparepart</a>
               </li>

             </ul>
           </li>

           <li>
            <a href="index.php?lihat=Transaksi/index">
              <span class="glyphicon glyphicon-usd"></span> Transaksi
            </a>
          </li>
          
          <li class="right">
            <a href="logout.php">
              <span class=" glyphicon glyphicon-log-out"></span> Logout
            </a>
          </li>

        </ul>
      </div><!-- #navbar -->
    </div><!-- .container -->
  </nav><!-- .navbar -->

  <div class="container">

    <?php
    /*Skrip dibawah berfungsi memanggil perintah sesuai nama file*/
    if(!empty($_GET['lihat'])){
      include('panggil/'.$_GET['lihat'].'.php');
    }

    else{
      include 'beranda.php';
    }
    ?>

  </div> <!-- .container -->

  <!-- Panggil JavaScript -->
  <!-- <script src="jquery/jquery.min.js"></script> -->
  <!-- <script src="bootstrap/js/bootstrap.min.js"></script>     -->
</body>

</html>


B. Koneksi.php
<?php
    //Urutan fungsi dibawah
    //Server    = localhost
    //User      = root
    //Password  = (kosong)
    //Database  = oop_4
    $koneksi = new mysqli('localhost', 'root', '','dbservice');

    //Jika koneksi gagal jalankan perintah dibawah
    if ($koneksi->connect_error) {
        die("Koneksi Gagal: " . $koneksi->connect_error);
    } 
?>
                                 C. Action.php
<?php
    session_start();                        
        $koneksi = new mysqli('localhost', 'root', '','dbservice');

    $username=$_POST['username'];           
    $password=$_POST['password'];           

    $query=mysqli_query($koneksi, "select * from user where nama='$username' and password='$password'");    
    if($query==TRUE){                             
        $_SESSION['username']=$username;      
        header("location:index.php");         
    }else{                                   
        echo "gagal login";
    }

?>
                               D. Beranda.php
<div class="jumbotron">
    <p><?php echo "selamat datang ".$_SESSION['username']; ?></p>
    <p>BENGKEL ONLINE</p>
    <br><center><p>Repost by <a href='https://instagram.com/agungpermana.17?igsh=MWR5Zjg5NDhuZHQ3Zw==' title='.service web' target='_blank'>Service web</a></p></center>
    
</div>

                               E. Login.php

<html>
    <head>
        <link rel="stylesheet" type="text/css" href="login.css">      
    </head>
    <body>
        <div id="kotak">
            <br><center><p>Repost by <a href='https://agungpermana.17?igsh=MWR5Zjg5NDhuZHQ3Zw==' title='Service web' target='_blank'>Service web</a></p></center>
            <div id="atas">
                LOGIN BENGKEL ONLINE
            </div>
            
            <div id="bawah">
                <form method="post" action="action.php">
                    <input class="masuk" type="text" autocomplete="off" placeholder="Username .." name="username" required><br/>
                    <input class="masuk" type="password" autocomplete="off" placeholder="Password .." name="password" required><br/>
                    <input id="tombol" type="submit" value="Login">
                </form>
            </div>
        </div>
    </body>
</html>

                               F. logout.php
<?php
session_start();
session_destroy();
header('location:login.php');
?>
                             G. Login.css

body{
    background:#ECF0F1;
    font-family: sans-serif;
}
#kotak{
    width: 520px;
    height: 250px;
    background: #fff;
    margin: 150px auto 100px auto;
    color:#2ECC71;
}
#atas{
    height: 35px;
    width: 520px;
    text-align: center;
    font-size: 15pt;
    padding-top:20px;
}
#bawah{
    height: 200px;
    width: 520px;
    
}
.masuk{
    width: 400px;
    height:40px;
    margin-top:10px;
    margin-left: 60px;
    font-size: 12pt;
    border: 1px solid #2ECC71;
    padding-left:10px;
    color:#2ECC71;
}
.masuk:focus{
    width: 400px;
    height:40px;
    margin-top:10px;
    margin-left: 60px;
    font-size: 12pt;
    padding-left:10px;
    color:#1ABC9C;
    outline: none;
    box-shadow: 0 0 5px #2ECC71;
}

#tombol{
    width: 400px;
    height:40px;
    margin-top:10px;
    margin-left: 60px;
    background: #2ECC71;
    border:none;
    color:#fff;
    font-size: 14pt;
    outline:none;
}




2.6	Tampilan Web Bengkel

Tampilan Beranda
 
Tampilan Mastering Data
Mastering Jasa
 
 

Master Sparepart
 


 

Tampilan Transaksi
 








 

BAB III PENUTUP
KESIMPULAN DAN SARAN
1.1	Kesimpulan
Kesimpulan
Berdasarkan hasil perancangan sistem inventory berbasis web untuk bengkel, dapat disimpulkan bahwa:
1.	Sistem yang dirancang mampu meningkatkan efisiensi pengelolaan stok sparepart melalui otomatisasi pencatatan keluar-masuk barang, sehingga dapat mengurangi potensi kesalahan akibat proses manual.
2.	Penggunaan teknologi berbasis web memberikan fleksibilitas akses data kapan saja dan di mana saja selama terhubung dengan jaringan internet, sehingga mendukung operasional yang lebih dinamis.
3.	Implementasi sistem ini memungkinkan integrasi antara komponen hardware, software, dan database yang mendukung, sehingga menciptakan proses kerja yang lebih terstruktur dan terkontrol.
4.	Desain antarmuka pengguna yang sederhana namun fungsional mendukung kemudahan penggunaan oleh operator maupun administrator tanpa memerlukan pelatihan yang kompleks.
5.	Sistem ini memberikan kontribusi strategis dalam pengelolaan stok, transaksi, dan laporan yang akurat, sehingga mendukung pengambilan keputusan yang lebih efektif bagi manajemen bengkel.



2.1	Saran
Saran
1.	Pengembangan Fitur Tambahan: Direkomendasikan untuk menambahkan modul analitik yang dapat membantu dalam mengidentifikasi pola penjualan sparepart sehingga bengkel dapat mengelola stok dengan lebih optimal.
2.	Peningkatan Keamanan Sistem: Implementasikan sistem keamanan data yang lebih komprehensif, seperti enkripsi SSL, manajemen akses berbasis peran, serta mekanisme backup data otomatis untuk mencegah kehilangan data.
3.	Integrasi Layanan: Sistem ini dapat dikembangkan lebih lanjut dengan mengintegrasikan fitur pembayaran digital dan e-invoice untuk meningkatkan kenyamanan pelanggan.
4.	Kompatibilitas Multi-Platform: Optimalkan antarmuka agar responsif dan kompatibel dengan berbagai perangkat, khususnya perangkat mobile, sehingga memudahkan pengguna dalam mengakses sistem.
5.	Pemeliharaan dan Evaluasi: Lakukan evaluasi berkala terhadap kinerja sistem untuk memastikan keandalannya, serta melakukan pembaruan fitur agar sistem tetap relevan dengan kebutuhan operasional bengkel yang terus berkembang.
Dengan pengembangan dan implementasi yang optimal, sistem ini diharapkan dapat memberikan dampak positif terhadap efisiensi operasional bengkel serta meningkatkan daya saing di tengah persaingan industri otomotif.

