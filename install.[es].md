Primero hay que averiguar si php es ts o nts. para ello hay que crear un archivo php llamado phpinfo y añadir dentro:
```
<?php phpinfo(); ?>
```

Una vez guardado, hay que ejecutar el archivo:
http://localhost/phpinfo.php

Hay que buscar la variable Thread Safety, si está en enabled, entonces php es ts, sino (si está en disabled) estonces en nts.

Una vez sabiendo esto, hay que copiar el driver a la carpeta ext de php, algunos ejemplos:
C:\php\ext\
C:\appsrv\php\ext\
C:\xampp\php\ext\

Hay que copiar y pegar ambos dll depediendo la versión de php en uso. Una vez que las dll han sido copiadas, hay que abrir con cualquier editor el archivo php.ini
> C:\php\php.ini

> C:\appsrv\php\php.ini

> C:\xampp\php\php.ini

Una vez abierto, pegar:
```
extension=php_sqlsrv.dll
extension=php_pdo_sqlsrv.dll
```

Nota: De preferencia pega esas dos lineas debajo de las Windows Extensions.

Ahora solo queda guardar el archivo y reiniciar apache para empezar a usar SQL a través de PDO.

http://php.net/manual/es/book.pdo.php
http://php.net/manual/es/ref.pdo-sqlsrv.connection.php
