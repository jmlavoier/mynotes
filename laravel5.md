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

Abra o arquivo ```config/app.php``` para edição, é notavel que este arquivo é uma array com inumeras propriedares. Vá até o indice ```'url' => 'localhost'``` e altere o *'localhost'* por *'local.laravel'* ou qualquer outro nome que deseja para a url do projeto.

```php
	'url' => 'local.laravel',
```

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

Agora vá até a linha de comando e digite ```php artisan key:generate```. Este comando ira gerar uma chave, copie a chave e vá até o arquivo ```config/app.php``` e cole na linha ```'key' => env('APP_KEY', 'insria a key aqui'),```.


