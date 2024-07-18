# 1. Pengenalan Laravel

Laravel adalah framework di PHP untuk membuat Web atau API

Laravel pertama kali dibuat oleh Taylor Otwell tahun 2011

Laravel adalah framework yang open source dan gratis, sehingga kita bisa menggunakannya tanpa biaya dan juga bisa berkontribusi ke projectnya

https://laravel.com/

https://github.com/laravel/laravel

### **Kenapa Laravel?**

Saat ini Laravel adalah framework paling populer di PHP

Banyak perusahaan yang sudah menggunakan Laravel sebagai framework pilihan ketika menggunakan PHP

Laravel juga memiliki ekosistem yang sangat besar, terutama dari ekosistem teknologi pendukung, sehingga ketika menggunakan Laravel, kita bisa mengintegrasikan dengan teknologi pendukung nya dengan lebih mudah

Laravel sendiri membawa konsep MVC (Model View Controller)

Sehingga jika kita sudah terbiasa dengan konsep tersebut, kita akan dengan mudah menggunakan Laravel

Detail dari konsep MVC itu sendiri sudah dibahas di kelas PHP MVC

![Untitled.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/86cdea4d-c848-4d3c-868a-d3cff3ff6a71/5bc1bf45-fee3-41d8-96bc-a3550279c460/Untitled.png)

### Library

Laravel sendiri sebenarnya tidak membuat semua bagian pada framework nya sendiri

Beberapa bagian menggunakan library yang sudah populer di PHP, dan sudah kita bahas di roadmap kelas PHP

Contohnya untuk project management, Laravel menggunakan Composer

Untuk Logging, Laravel menggunakan Monolog

Untuk Unit Test, Laravel menggunakan PHPUnit

Dan lain-lain

# 2. Membuat Project

Laravel menggunakan Composer untuk project management nya

Dan untuk membuat projectnya pun kita bisa menggunakan Composer dengan perintah :

```php
composer create-project laravel/laravel=version nama-folder
```

https://packagist.org/packages/laravel/laravel

# 3. Struktur Projek

![Untitled.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/86cdea4d-c848-4d3c-868a-d3cff3ff6a71/4d739443-70bb-468e-bef1-3a852ae64ddb/Untitled.png)

### app

Direktori `app`berisi kode inti aplikasi kamu. Kita akan segera mencari direktori ini 
secara lebih rinci. Namun, hampir semua kelas dalam aplikasi kamu ada di direktori ini.

### bootstrap

Direktori `bootstrap`berisi file app.php yang mem-bootstrap framework. Direktori ini juga 
menampung direktori cache yang berisi file yang dihasilkan kerangka kerja untuk pengoptimalan kinerja seperti file cache rute dan layanan. Biasanya kamu tidak perlu mengubah file apa pun dalam direktori ini.

### config

Direktori `config`, seperti namanya, berisi semua file konfigurasi aplikasi kamu. Merupakan
ide bagus untuk membaca semua file ini dan membiasakan diri dengan semua opsi yang tersedia untuk kamu.

### database

Direktori `database` berisi migrasi database kamu, model factory, dan seed. Jika mau, Kamu juga bisa menggunakan ini dengan SQLite.

### public

Direktori `public`berisi file index.php, yang merupakan titik masuk untuk semua permintaan yang memasuki aplikasi kamu dan mengkonfigurasi pemuatan otomatis. Direktori ini juga menampung aset kamu seperti gambar, JavaScript, dan CSS.

### recources

Direktori `resources`berisi tampilan kamu serta aset mentah yang belum dikompilasi seperti 
CSS atau JavaScript. Direktori ini juga menampung semua file bahasa kamu.

### routes

Direktori `routes`berisi semua definisi rute untuk aplikasi kamu. Secara default, 
beberapa file rute disertakan dengan Laravel: web.php, api.php, console.php, dan channels.php.

- **web.php**

berisi route yang ditempatkan RouteServiceProvider di grup middleware web, yang menyediakan status sesi, perlindungan CSRF, dan enkripsi cookie. Jika aplikasi kamu tidak menawarkan stateless, RESTful API maka kemungkinan besar semua route kamu kemungkinan besar akan 
ditentukan di file web.php.

- **api.php**

berisi route yang ditempatkan RouteServiceProvider di grup middleware api. Route ini dimaksudkan untuk menjadi tanpa kewarganegaraan, jadi permintaan yang memasuki aplikasi melalui route 
ini dimaksudkan untuk diautentikasi melalui token dan tidak akan memiliki akses ke status sesi.

- **console.php**

adalah tempat kamu dapat menentukan semua perintah konsol berbasis penutupan kamu. Setiap penutupan terikat ke contoh perintah yang memungkinkan pendekatan sederhana untuk berinteraksi dengan setiap metode IO perintah. Meskipun file ini tidak menentukan route HTTP, file 
ini mendefinisikan titik masuk (route) berbasis konsol ke dalam aplikasi kamu.

File channels.php adalah tempat kamu dapat mendaftarkan semua saluran penyiaran acara yang didukung aplikasi kamu.

### storage

Direktori `storage`berisi log kamu, templat Blade yang dikompilasi, sesi berbasis file, 
cache file, dan file lain yang dihasilkan oleh kerangka kerja. Direktori ini dipisahkan menjadi direktori app, framework, dan logs. Direktori aplikasi dapat digunakan untuk menyimpan file apa pun yang dibuat oleh aplikasi kamu. Direktori framework digunakan untuk menyimpan file dan 
cache yang dibuat oleh framework. Terakhir, direktori logs berisi file  log aplikasi kamu. Direktori penyimpanan / app / publik dapat digunakan untuk menyimpan file yang dibuat pengguna, seperti avatar profil, yang harus dapat diakses publik. kamu harus membuat tautan simbolis di publik / penyimpanan yang mengarah ke direktori ini. kamu dapat membuat tautan menggunakan 
perintah php artisan storage: link Artisan.

### tests

Direktori `tests`berisi tes otomatis kamu. Contoh pengujian unit PHPUnit dan pengujian 
fitur disediakan di luar kotak. Setiap kelas tes harus diakhiri dengan kata Tes. Kmau dapat menjalankan pengujian kamu menggunakan perintah :

```php
phpunit atau php vendor / bin / phpunit
```

. Atau, jika kamu ingin representasi yang lebih detail dan indah dari hasil pengujian kamu, kamu
 dapat menjalankan pengujian kamu menggunakan perintah php artisan test kamu.

### vendor

Direktori `vendor` berisi dependensi Composer kamu. Mereka adalah folder-folder dari root atau direktori utama/paling awal.

# 4. Menjalankan Laravel

Saat kita membuat project Laravel, laravel sendiri sudah menyediakan secara otomatis sebuah file bernama artisan

File artisan ini sendiri sebenarnya adalah file yang berisi kode php

Kita bisa menggunakan perintah “php artisan” untuk melihat semua feature yang bisa dilakukan oleh file artisan

### Menjalankan Laravel

File artisan bisa digunakan untuk melakukan banyak hal, salah satunya menjalankan aplikasi laravel ketika proses development

Untuk menjalankan aplikasi laravel dalam mode development, kita bisa gunakan perintah :

```php
php artisan serve
```

# 5. Git

Saat membuat project Laravel, Laravel menyediakan sebuah file bernama artisan

File artisan ini adalah kode PHP yang bisa digunakan untuk banyak hal, kita akan bahas fitur-fitur file artisan ini secara bertahap di materi-materi selanjutnya

# 6. Artisan

Saat membuat project Laravel, Laravel menyediakan sebuah file bernama artisan

File artisan ini adalah kode PHP yang bisa digunakan untuk banyak hal, kita akan bahas fitur-fitur file artisan ini secara bertahap di materi-materi selanjutnya.

### Melihat Semua Perintah Artisan

Untuk melihat semua fitur file artisan, kita bisa gunakan perintah :

```php
php artisan
```

Secara otomatis kita bisa lihat semua fitur yang terdapat di file artisan

![Screenshot from 2023-11-25 14-25-20.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/86cdea4d-c848-4d3c-868a-d3cff3ff6a71/67d25cbf-aea8-43ec-8edb-c5413b21131c/Screenshot_from_2023-11-25_14-25-20.png)

### Melihat Detail Informasi

![Screenshot from 2023-11-25 14-26-43.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/86cdea4d-c848-4d3c-868a-d3cff3ff6a71/5d5bd440-7596-434c-afb9-ab2c20f0deee/Screenshot_from_2023-11-25_14-26-43.png)

Untuk melihat detail informasi perintah yang terdapat di file artisan, kita bisa gunakan perintah :

```php
php artisan perintah --help
```

# 7. Request Lifecycle

Sebelum kita membuat kode program menggunakan Laravel, ada baiknya kita perlu tahu cara kerja Laravel itu sendiri

Terutama bagaimana alur hidup dari request yang kita lakukan ke aplikasi Laravel.

### Entry Point

Entry point pertama dari aplikasi Laravel adalah sebuah file index.php yang terdapat di folder public

Semua request yang masuk ke aplikasi Laravel, maka akan masuk melalui file ini

File ini sengaja disimpan di dalam folder public tersendiri, agar file-file kode program lainnya tidak bisa diakses via URL

Ini file index.php sebenarnya tidak ada yang kompleks, hanya me-load framework Laravel, dan menjalankan kode program yang kita buat

### Kernel

Dari index.php, **request akan dilanjutkan ke class Kernel**

Di Laravel, terdapat dua jenis Kernel, HTTP Kernel, dan Console Kernel. HTTP Kernel digunakan untuk menangani request berupa HTTP, sedangkan Console Kernel digunakan untuk menangani request berupa perintah console

kita bahas tentang HTTP Kernel, jadi ketika request web masuk ke index.php, maka request akan dilanjutkan ke HTTP Kernel.

### Service Provider

Kernel sendiri sebenarnya adalah core dari logic aplikasi, dimana di dalam Kernel, request yang masuk di tangani sampai mendapatkan response

Kernel melakukan beberapa hal : 

1. Pertama Kernel melakukan proses bootstraping, yaitu me-load yang namanya Service Provider, yang akan kita bahas di materi terpisah
2. Laravel akan melakukan iterasi semua Service Provider dan melakukan proses registrasi dan juga bootstraping untuk semua Service Provider
3. Service Provider ini lah yang bertanggung jawab melakukan bootstraping semua komponen di Laravel, seperti database, queue, validation, routing dan lain-lain

# 8. Testing

Laravel menggunakan PHPUnit untuk implementasi unit test nya

Secara garis besar, di Laravel terdapat dua jenis test, unit test dan feature test / integration test

### Unit Test

Untuk unit test, kita bisa membuat class unit test seperti menggunakan PHP Unit biasanya

Yaitu dengan membuat class turunan dari PHPUnit\Framework\TestCase

Jika kita perlu membuat test tanpa harus menggunakan fitur Laravel, maka kita cukup buat Unit Test saja.

### Integration Test

Laravel memiliki fitur yang mempermudah kita ketika membuat integration test

Bedanya dari unit test, di integration test, aplikasi laravel bisa diakses dengan mudah, misal kita nanti mau memanggil Database, Controller, dan lain-lain

Untuk membuat Integration Test, kita cukup membuat class turunan dari Illuminate\Foundation\Testing\TestCase

Integration Test akan lebih lambat dibandingkan Unit Test, karena kita butuh me-load framework Laravel terlebih dahulu

Dan jika kita membutuhkan fitur Laravel, maka kita wajib menggunakan Integration Test.

### Membuat Test

Untuk membuat Integration Test, kita bisa lakukan manual, atau kita bisa gunakan file artisan menggunakan perintah :

```php
php artisan make:test NamaTest
```

Secara otomatis akan masuk ke folder tests/Feature

Jika kita ingin membuat Unit Test, kita bisa gunakan perintah :

```php
php artisan make:test NamaTest --unit
```

Secara otomatis akan masuk ke folder tests/Unit

### Menjalankan Test

Untuk menjalankan test, kita bisa gunakan PHPUnit seperti biasanya

Atau jika ingin menjalankan semua test, bisa menggunakan file artisan dengan perintah :

```php
php artisan test
```

# 9. Environment

Saat kita membuat aplikasi, kadang kita perlu menyimpan nilai konfigurasi di environment variable

Laravel memiliki fitur untuk memudahkan kita mengambil data dari environment variable

Kita bisa menggunakan function env(key) atau Env::get(key) untuk mendapatkan nilai dari environment variable

Internal implementasi dari Environment variable di Laravel menggunakan library

https://github.com/vlucas/phpdotenv

```php
class EnvironmentTest extends TestCase
{
   public function testYoutube()
   {

            $appName = env('YOUTUBE',"Nichola Saputra"); // Default Value

            self::assertEquals("Nichola Saputra", $appName);

   }

   public function testDefaultValue()
   {
        // $name = env('AUTHOR', 'Nichola');

        $name = Env::get('AUTHOR', 'Nichola'); // Gini Juga Bisa

        self::assertEquals('Nichola', $name);
   }

}
```

![Screenshot from 2023-11-25 15-39-00.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/86cdea4d-c848-4d3c-868a-d3cff3ff6a71/a9dd5217-90ac-42da-b0b5-964f3e871a32/Screenshot_from_2023-11-25_15-39-00.png)

### File .ENV

Selain membaca dari environment variable, Laravel juga memiliki kemampuan untuk membaca nilai dari file .env yang terdapat di project Laravel

Ini lebih mudah dibandingkan mengubah environment variable di sistem operasi, Kita cukup menambah environment variable ke file .env

File .env secara default di ignore di Git project Laravel, oleh karena itu, kita bisa menambahkan konfigurasi di local tanpa takut ter-commit ke Git Repository

### Default Value

Laravel mendukung default value untuk environment variable

Default value adalah nilai yang akan digunakan ketika environment variable yang kita ambil tidak tersedia

Kita bisa menggunakan function env(key, default) atau Env::get(key, default)

# 10. Application Environment

Saat membuat aplikasi, kadang kita ingin menentukan saat ini sedang berjalan di environment mana, misal di local, di dev, di staging, di qa atau di production

Di Laravel, hal ini biasanya dilakukan dengan menggunakan environment variable APP_ENV

Dan untuk mengecek saat ini sedang berjalan di environment apa, kita bisa menggunakan function **App::environment(value) atau App::environment([value1, value2])**, dimana akan return true jika benar.

```php
class AppEnvironmentTest extends TestCase
{
      public function testAppEnv()
      {

        if(App::environment("testing"))
        {
            self:assertTrue(true);
        }
      }
}
```

# 11. Configuration

Environment variable cocok digunakan untuk jenis konfigurasi yang memang butuh berubah-ubah nilainya, dan terintegrasi dengan baik dengan environment variable di sistem operasi

Laravel juga mendukung penulisan konfigurasi dengan menggunakan PHP Code, konfigurasi ini biasanya digunakan ketika memang dibutuhkan tidak terlalu sering berubah, dan biasanya pengaturannya hampir sama untuk tiap lokasi dijalankan aplikasi

Namun saat menggunakan fitur Laravel Configuration, kita juga tetap bisa mengakses Environment Variable.

### File Config

Laravel menyimpan semua konfigurasi di folder config yang terdapat di project

Dan prefix dari konfigurasi diawali dengan file php yang terdapat di project tersebut

### Membuat FIle Configuration

Untuk membuat file konfigurasi, kita cukup membuat file php di dalam folder config

Lalu di dalam file tersebut, kita cukup return konfigurasi dalam bentuk array

```php
"author" => [
        "first" => env('NAME_FIRST', 'Nichola'),
        "last" => env('NAME_LAST', 'Saputro')
    ],
    "address" => [
        "regency" => "blitar",
        "district" => "bakung"
    ],
];
```

### Mengambil Configuration

Untuk mengambil konfigurasi di file konfigurasi, kita bisa menggunakan function config(key, default)

Dimana pembuatan key pada config diawali dengan nama file, lalu diikuti dengan key yang terdapat di dalam return value nya

Tiap nested array menggunakan . (titik)

Misal contoh.author.first, artinya kita ambil konfigurasi dari file contoh.php, lalu ambil data array key author, dan di dalamnya kita ambil data key first

Sama seperti function env(), function config() juga memiliki parameter default value jika key konfigurasinya tidak tersedia

```php
public function testConfiguration()
    {
        $firtname = config('contoh.author.first');
        $lastname = config('contoh.author.last');
        $regency = config('contoh.address.regency');
        $district = config('contoh.address.district');

        self::assertEquals('Mas Nichola', $firtname);
        self::assertEquals('Saputra', $lastname);
        self::assertEquals('blitar', $regency);
        self::assertEquals('bakung', $district);
    }
```

# 12. Configuration Cache

Saat kita membuat terlalu banyak file konfigurasi, lama-lama maka akan membuat proses baca konfigurasi menjadi lambat karena Laravel harus membaca file setiap kali kita mengambil konfigurasi

Pada saat proses development, hal ini mungkin bukan masalah, namun jika sudah masuk ke production, maka ini bisa memperlambat performa aplikasi Laravel kita

Laravel memiliki fitur untuk meng-cache data konfigurasi yang kita buat menjadi satu file sehingga proses membacanya lebih cepat karena datanya langsung di load saat aplikasi berjalan

Untuk membuat configuration cache, kita bisa gunakan perintah :

```php
php artisan config:cache
```

### Hapus Configuration Cache

Ketika file cache sudah dibuat, jika kita menambah konfigurasi di file php yang terdapat di folder config, maka config tersebut tidak akan bisa diakses

Hal ini karena Laravel akan selalu menggunakan configuration cache jika ada, oleh karena itu kita bisa buat ulang cache nya, atau jika ingin menghapus cache nya, kita bisa gunakan perintah :

```php
php artisan config:clear
```

# 13. Depedency Injection

Di dalam pengembangan perangkat lunak, ada konsep yang namanya Dependency Injection

Dependency Injection adalah teknik dimana sebuah object menerima object lain yang dibutuhka atau istilahnya dependencies

Saat kita membuat object, sering sekali kita membuat object yang butuh object lain

https://en.wikipedia.org/wiki/Dependency_injection

**Foo.php**

```php
<?php

namespace App\Data;
class Foo
{
    public function Foo()
    {
        return "Foo";
    }

}
```

**Bar.php**

```php
<?php

namespace App\Data;

class Bar
{
    private Foo $foo;

    public function __construct(Foo $foo)
    {
        $this->foo = $foo;
    }

    public function bar() : string
    {
        return $this->foo->Foo() . "and Bar";
    }
}
```

### Foo Dan Bar

Dari class Foo dan Bar kita tahu bahwa Bar membutuhkan Foo, artinya Bar depends-on Foo, atau Foo adalah dependency untuk Bar

Dependency Injection berarti kita perlu memasukkan object Foo ke dalam Bar, sehingga Bar bisa menggunakan object Foo

Pada kode Foo dan Bar kita menggunakan Constructor untuk melakukan injection (memasukkan dependency), sebenarnya caranya tidak hanya menggunakan Constructor, bisa menggunakan Attribute atau Function, namun sangat direkomendasikan menggunakan Constructor agar bisa terlihat jelas dependencies nya dan kita tidak lupa menambahkan dependencies nya

```php
public function testInjection()
    {
        $foo = new Foo();
        $bar = new Bar($foo); //depends

        self::assertEquals("Foo and Bar", $bar->bar());
    }
```

# 14. Service Container

Sebelumnya kita sudah mencoba melakukan Dependency Injection secara manual

Laravel memiliki fitur Dependency Injection secara otomatis, dan ini wajib dikuasai agar lebih mudah membuat aplikasi menggunakan Laravel

Di Laravel fitur ini bernama Service Container, dimana Service Container ini merupakan fitur yang digunakan untuk manajemen dependencies dan juga dependency injection

### Apa Itu Service Container

Apa itu service container? Secara sederhana, service container adalah service yang disediakan oleh laravel yang membuat kita bisa memberi tahu laravel bagaimana sebuah objek akan dikonstruksikan pada aplikasi yang kita buat.

Service container merupakan sebuah alat yang digunakan untuk me-manage class dependencies dan melakukan dependencies injection.

### Application Class

Service Container di Laravel direpresentasikan dalam class bernama Application

Kita tidak perlu membuat class Application secara manual, karena semua sudah dilakukan secara otomatis oleh framework Laravel

Di semua project Laravel, hampir disemua bagian terdapat field $app yang merupakan instance dari Application

https://laravel.com/api/9.x/Illuminate/Foundation/Application.html

### Membuat Depedency
