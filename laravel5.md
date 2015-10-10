# Laravel 5

### Instalando

Acessar o github e dar um clone na versão do Laravel 5. 

[Laravel 5 on Github](https://github.com/laravel/laravel)

```code
	$ git clone https://github.com/laravel/laravel.git
```

Ao finalizar o clone veja que na raiz do projeto terá o arquivo *composer.json*. Para prosseguir com a instalação das dependencias do Laravel será necessário ter o **Composer** instalado em sua máquina. Execute este comando para a instalação das dependencias do Laravel.

```code
	$ sudo composer install
```
Observe que após baixar as dependências irá aparecer um novo diretório chamado **vendor** na raiz do projeto, dentro deste diretório está instalado todas as denpendencias do Laravel.

### Colocando para rodar 

#### HOSTS 

Abra o arquivo ```config/app.php``` para edição, é notavel que este arquivo é uma array com inumeras propriedares. Vá até o indice ```'url' => 'localhost'``` e altere o *'localhost'* por *'local.laravel'* ou qualquer outro nome que deseja para a url do projeto.

```php
	'url' => 'local.laravel',
```

* Edite o arquivo ```/etc/hosts``` e insira a url do projeto para **127.0.0.1**

* Edite o **httpd-vhosts.conf** inserindo o diretorio **public/** como o diretório incial do projeto.
```xml
<VirtualHost *:80>
    ServerAdmin webmaster@dummy-local.laravel
    DocumentRoot /Users/dummy/Sites/laravel/public/
    ServerName local.laravel
    ServerAlias local.laravel
    ErrorLog "/private/var/log/apache2/dummy-local.laravel-error_log"
    CustomLog "/private/var/log/apache2/dummy-local.laravel-access_log" common
</VirtualHost>
```
Ao apache identificar através da url o alias do projeto, o projeto será direcionado para o diretorio apontado no **DocumentRoot** do vhosts.

#### Database

Para setar a base de dados vamos utilizar o MySQL. Vá até o arquivo ```config/database.php``` e configure a conexão desta maneira e crie a tabela **laravel** no MySQL.

```php
	'mysql' => [
	    'driver'    => 'mysql',
	    'host'      => env('DB_HOST', 'localhost'),
	    'database'  => env('DB_DATABASE', 'laravel'),
	    'username'  => env('DB_USERNAME', 'root'),
	    'password'  => env('DB_PASSWORD', 'root'),
	    'charset'   => 'utf8',
	    'collation' => 'utf8_unicode_ci',
	    'prefix'    => '',
	    'strict'    => false,
	],
```

#### Key Generate do Artisan

Agora vá até a linha de comando e digite ```$ php artisan key:generate```. Este comando ira gerar uma chave, copie a chave e vá até o arquivo ```config/app.php``` e cole como no exemplo abaixo.

**Cammand**
```
laravel (master) $ php artisan key:generate
Application key [0T5Iv8U0GKVwMTamwLjnQu8wxChkQYTH] set successfully.
joao@JoaoMilton-MacPro laravel (master) $ 
```

**config/app.php**
```php
'key' => env('APP_KEY', '0T5Iv8U0GKVwMTamwLjnQu8wxChkQYTH'),
```

#### .htaccess

O arquivo ```public/.htaccess``` deve ser substituido pelo exemplo que se encontra na documentação do Laravel para o funcionamento da URL amigável.

**.htaccess**
```
Options +FollowSymLinks
RewriteEngine On

RewriteCond %{REQUEST_FILENAME} !-d
RewriteCond %{REQUEST_FILENAME} !-f
RewriteRule ^ index.php [L]
```

Agora vá até o browser e entre com a URL **http://local.laravel** para acessar o 