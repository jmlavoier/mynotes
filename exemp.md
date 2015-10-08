# jQuery Only Number 
Plugin para permitir digitar somente números em um campo

# Requisitos

**jQuery JavaScript Library v2.1.4**

# Instalação

Inserir o plugin abaixo do jQuery

**Exemplo**
```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<title>Testando JQuery Only Number 1.0</title>
		<script src="../bower_components/jquery/dist/jquery.min.js"></script>
        <script src="../jquery.onlynumber.js"></script>
	</head>
	<body>
           
           
	</body>
</html>
```

# Usando

Insira o comando abaixo para disparar o evento em um input

```javascript
$('input').onlynumber();
```

Caso necessário destuir o evento 

```javascript
$('input').onlynumber("destroy");
```

**Cuidado:** 
*certificar sempre se o DOM foi totalmente carregado*

```javascript
$(document).ready(function(){
    $('input').onlynumber();
});
```

# Exemplo

Inserindo o evento ao input *valores*:

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<title>Testando JQuery Only Number 1.0</title>
		<script src="bower_components/jquery/dist/jquery.min.js"></script>
        <script src="jquery.onlynumber.js"></script>
        <script>
            $(document).ready(function(){
                $("#valores").onlynumber(); 
            });
        </script>
	</head>
	<body>
        <input type="text" id="valores" value="" />
	</body>
</html>
```

# Autor

[João M. Lavoier Fh.](https://github.com/jmlavoier)