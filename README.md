###### Nama     : Adrian Sondang I.
###### Kelas    : XII RPL-1
###### No Absen : 08

# Modul 1
## Mengenal dan Instalasi Laravel

**Pada Modul 1 ini, kita akan belajar mengenal apa itu framework, Laravel, dan dasar cara membuat framework PHP yaitu Laravel.**

>Apa itu Framework? Framework sebuah kerangka kerja yang digunakan untuk mengembangkan website. Framework ini diciptakan untuk membantu web developer dalam menulis baris kode. Dengan menggunakan framework penulisan kode akan jauh lebih mudah, cepat, dan terstruktur rapi [[dicoding.com](https://www.dicoding.com/blog/apa-itu-framework/)].

>Beberapa bahasa pemrograman memiliki frameworknya sendiri, contohnya PHP memiliki framework Laravel, Laravel adalah salah satu Framework PHP yang paling populer dan paling banyak digunakan di seluruh dunia dalam membangun aplikasi web mulai dari proyek kecil hingga besar. Framework ini banyak digunakan oleh Web Developer karena kinerja, fitur, dan skalabilitas nya.Framework ini mengikuti struktur MVC (Model View Controller), MVC adalah sebuah metode aplikasi dengan memisahkan data dari tampilan berdasarkan komponen- komponen aplikasi, seperti : manipulasi data, controller, dan user interface. Dengan menggunakan struktur MVC maka membuat laravel mudah untuk dipelajari dan mempercepat proses pembuatan prototipe aplikasi web. Framework ini juga menyediakan fitur bawaan seperti otentikasi, mail, perutean, sesi, dan daftar berjalan [[Jagoanhosting.com](https://www.jagoanhosting.com/blog/framework-laravel/)].

Setelah kalian mengenal apa itu framework dan laravel, selanjutnya kita akan mencoba membuat Database menggunakan framework Laravel. Sebelum itu, pastikan kalian sudah mempunyai Web Browser (Disanrankan Google Chrome), memiliki Text Editor (Disarankan Visual Studio Code), memiliki XAMPP, dan Postman. Jika kalian belum memilikinya kalian bisa download bahan tersebut disini.

|-------------|----------|
|Google Chrome|[Klik link](https://www.google.com/intl/id_id/chrome/)  
|VS Code      |[Klik link](https://code.visualstudio.com/)             
|XAMPP        |[Klik link](https://www.apachefriends.org/download.html)
|Postman      |[Klik link](https://www.postman.com/downloads/)

Setelah kalian mempunyai semua bahan diatas, kita akan mulai pada langkah pertama yaitu membuat projectnya.
Aktifkan Apache dan MySql di XAMPP, lalu buat folder dengan nama kalian atau folder untuk project tersebut, pada praktek kali ini saya masukkan di D dengan nama folder Praktikum1
Lalu kalian ketik code berikut pada terminal atau cmd:

```
D:
```
```
cd Praktikum1
```

Setelah masuk ke folder Praktikum1, selanjutnya ketikan code berikut:

```
composer create-project laravel/laravel penjualan
```

Setelah membuat projectnya kalian masuk ke folder penjualan dan buka VS Code project penjualan
ketik code berikut di terminal atau cmd:

```
cd penjualan
```
```
code .
```

Modul 1 yaitu Pengenalan dan Instalasi Laravel telah selesai dan kita selesai juga membuat satu project Laravel.



## Modul 2
## Fitur Pada Laravel

**Pada Modul 2 ini, kita akan mengenal apa itu artisan, migration, model, dan seeder, serta kita akan membuat database MySql dengan Laravel.**

Pada modul 1 kita telah membuat folder project Laravel dengan nama *penjualan*. Di dalam project tersebut terdapat banyak folder seperti database dan app lalu di dalam folder tersebut terdapat migration, mode dan seeder. Nah folder tersebutlah yang akan kita eksekusi, sebelum itu saya akan mengenalkan apa itu Artisan atau si asisten pembantu dalam pemrograman Laravel ini.

>Artisan CLI akan membantu pengembang untuk meng-generate file-file dengan struktur kode dasar yang dibutuhkan pengembang. Pengembang bisa saja membuat file-file secara manual, tapi akan banyak waktu dan usaha, jadi Artisan merupakan CLI yang membantu kita saat pemrograman nanti [[medium.com](https://medium.com/easyread/apa-itu-artisan-cli-pada-laravel-62a94232a29a)].

>Model merupakan salah satu dari bagian MVC yang akan berkomunikasi dengan database. Model yang sudah terhubung ke database akan digunakan/dipanggil via Controller sebagaimana konsep MVC itu berjalan.

>Migration merupakan salah satu fitur Laravel yang berfungsi seperti version control untuk database. Melalui fitur ini sebuah team pengembangan web development akan dapat bekerja dalam team untuk mengelola dan modifikasi skema basis data aplikasi. Migration biasanya dipasangkan dengan Schema Builder dari Laravel untuk dengan mudah membangun skema basis data aplikasi Anda. Facade Skema Laravel menyediakan dukungan untuk membuat dan memanipulasi tabel di semua sistem basis data yang didukung Laravel [[informatika.uc.ac.id](https://informatika.uc.ac.id/id/2019/10/laravel-model-2/#:~:text=Apa%20itu%20Laravel%20Model%3F,sebagaimana%20konsep%20MVC%20itu%20berjalan.)].

>Jika migrations berfungsi untuk menjalankan DDL (Data Definition Language), maka database seeder pada Laravel berfungsi untuk menjalankan DML (Data Manipulation Language). Database seeder sangat berguna untuk inisiasi data pada tabel atau beberapa tabel ketika setup aplikasi pertama kali. Bisa juga untuk memperbarui data yang sudah ada atau menghapusnya dari belakang layar [[medium.com](https://medium.com/laravel-web-id/database-seeder-di-laravel-c839c34bfe0#:~:text=Jika%20migrations%20berfungsi%20untuk%20menjalankan,ketika%20setup%20aplikasi%20pertama%20kali.)]

Kalian telah mengetahui apa itu artisan, migration, model, dan seeder. Selanjutnya kita akan membuat database MySql dengan menggunakan artisan, migration, model, dan seeder ini,  pertama buka project dan pilih yang .env dikiri bagian folder, setelah itu kalian cari DB_DATABASE=laravel dan ganti nilai laravel tersebut menjadi penjualan (DB_DATABASE=penjualan), setelah itu pada web browser kalian localhost/phpmyadmin. Setelah itu kalian kembali ke VS Code dan buka terminalnya.

Selanjutnya ketikan code berikut:

```
php artisan make:migration create_kategori_table
```

Setelah itu kalain pergi ke database - migrations - lalu ke file yang telah kalian buat (biasanya filenya berada dibawah sendiri), tambahkan string nama pada file, lihat kode berikut:

```
<?php

use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Support\Facades\Schema;

return new class extends Migration
{
    /**
     * Run the migrations.
     *
     * @return void
     */
    public function up()
    {
        Schema::create('kategoritgs', function (Blueprint $table) {
            $table->id();
            $table->string('nama');
            $table->timestamps();
        });
    }

    /**
     * Reverse the migrations.
     *
     * @return void
     */
    public function down()
    {
        Schema::dropIfExists('kategoritgs');
    }
};
```

Setelah membuat migration kalian ketik ini pada cmd:

```
php artisan migrate
```

Setelah di migrate, maka tabel baru akan terbuat dengan nama kategoritgs. Setelah membuat migration, kalian buat seeder baru dengan mengetikan code berikut di cmd atau terminal:

```
php artisan make:seeder kategoritgsTableSeeder
```

Setelah mengetikan code tersebut, maka file seeder baru akan terbuat dengan nama kategoritgsTableSeeder, setelah itu kalian ubah codenya seperti ini:

```
<?php

namespace Database\Seeders;

use Illuminate\Database\Console\Seeds\WithoutModelEvents;
use Illuminate\Database\Seeder;
use DB;

class kategoritgsTableSeeder extends Seeder
{
    /**
     * Run the database seeds.
     *
     * @return void
     */
    public function run()
    {
        DB::table('kategoritgs')->insert(array(
            [
                'nama' => 'Perlangkapan sekolah',
            ],
            [
                'nama' => 'Komputer',
            ],
            [
                'nama' => 'Sabun',
            ],
            [
                'nama' => 'Accesories',
            ],
            [
                'nama' => 'ATK',
            ]
        ));
    }
}
```

Kalian ketikan lagi code berikut untuk membuat model:

```
php artisan make:model Kategoritgs
```

Setelah model terbuat kalian ketik kode berikut

```
<?php

namespace App\Models;

use Illuminate\Database\Eloquent\Factories\HasFactory;
use Illuminate\Database\Eloquent\Model;

class Kategoritgs extends Model
{
    use HasFactory;

    protected $table = 'kategoritgs';
}
```

Oh iya, kalian jangan lupa ketikan ini di seeders-DatabaseSeeder agar database bisa diketahui

```
<?php

namespace Database\Seeders;

// use Illuminate\Database\Console\Seeds\WithoutModelEvents;
use Illuminate\Database\Seeder;

class DatabaseSeeder extends Seeder
{
    /**
     * Seed the application's database.
     *
     * @return void
     */
    public function run()
    {
        // \App\Models\User::factory(10)->create();

        // \App\Models\User::factory()->create([
        //     'name' => 'Test User',
        //     'email' => 'test@example.com',
        // ]);
        $this->call(kategoritgsTableSeeder::class);
    }
}
```

Setelah semuanya selesai kalian ketikan code ini di terminal atau cmd agar databasenya terkirim

```
php artisan db:seed
```
