# Laravel 5 Instagram Packages
Package Instagram untuk Laravel 5

### Installasi

Tambahkan Package pada composer.json
```sh
composer require muhamadrezaar/instagram
```
setelah package terdownload , register  provider  dan facade nya

Provider :
```sh
Oblagio\Instagram\InstagramServiceProvider::class,
```
Facade :
```sh
'IG' => Oblagio\Instagram\InstagramFacade::class,
```

Publish config
```sh
php artisan vendor:publish
```

### Konfigurasi

Buka file config/InstagramConfig.php
masukan user id dan access token instagram anda
contoh :
```sh
return [
		'userId' => '1234567890',
		'accessToken' => '1619689047987654321', 
];
```

### Cara penggunaaan

Menampilkan Gambar low resolusi
  
```sh

<?php

foreach(IG::lowResolution() as $row)
{
	echo "<img src = '".$row."' />";
}

?>
```

Menampilkan Gambar standar resolusi

```sh

<?php

foreach(IG::standardResolution() as $row)

{
	echo "<img src = '".$row."' />";
}

?>

```

Menampilkan Informasi User

```sh

<?php

echo IG::username();

echo IG::bio(); 

echo IG::website();

echo IG::pic();

echo IG::fullName();

echo IG::countFollowers();

echo IG::countFollowing();

?>


```

Menampilkan Data Followers

```sh

<?php

foreach(IG::displayFollowers() as $row)

{
	echo $row['full_name'];
	echo $row['profile_picture'];
	echo $row['username'];
	echo $row['id'];
}

?>

```

Menampilkan Data Following

```sh

<?php

foreach(IG::displayFollowing() as $row)

{
	echo $row['full_name'];
	echo $row['profile_picture'];
	echo $row['username'];
	echo $row['id'];
}

?>

```

Outout Menampilkan gambar low resolution di browser

![alt tag](http://s15.postimg.org/n8nhl6r8r/low_resoulution.png)

## License

MIT

**ENJOY !!!**