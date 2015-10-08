# PHP for Mac OS X

##MAMP

### Principais pastas do MAMP
O MAMP se localiza na pasta */Applications/MAMP/* 

* **conf/** Várias versões do *php.ini*;
* **conf/apache/** *httpd.conf*, a pasta *extra* e seus vários *confs*;
* **bin/php/** Várias versões do server PHP, onde deve ser configurado no *httpd.conf*;
* **db/** Bases de dados gerenciados pelo MAMP *mongodb, mysql, sqlite*;

### Alterando a versão do PHP 
Editar o arquivo *conf/apache/httpd.conf* e altarar linha que habilita o servico PHP para versão desejada
```$
 $ nano /Applications/MAMP/conf/apache/httpd.conf
```

Veja as versões que possui no diretório *bin/php/*  
```code
 LoadModule php5_module /Applications/MAMP/bin/php/**php5.6.2**/modules/libphp5.so
``` 

- - - -

## Apache2
O Apache nativo do Mac se localiza */etc/apache2/*

**Arquivos importantes**
* **httpd.conf**
* extra/
	* **httpd-vhosts.conf**
* users/
	* **<user>.conf**
	* **Guest.conf**
	
## Arquivo HOSTS
O arquivo hosts se localiza no diretírio *etc/hosts*

## Arquivo php.ini
O arquivo php.ini se localiza no diretório *etc/php.ini*



