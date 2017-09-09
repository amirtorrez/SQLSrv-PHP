First we have to find out if php is *ts* or *nts*. to do this, you have to create a php file called *phpinfo* and add inside:
```php
<?php phpinfo(); ?>
```

Once saved, run the file:
> http://localhost/phpinfo.php

You have to look for the variable **Thread Safety**, if it is enabled, then php is ts, otherwise (if it is disabled) then nts.

Once you know this, copy the driver to the ext php folder, some examples:
```
C:\php\ext\
C:\appsrv\php\ext\
C:\xampp\php\ext\
```

Both dlls must be copied and pasted depending on the version of php in use. Once the dlls have been copied, open the **php.ini** file with any editor
```
C:\php\php.ini
C:\appsrv\php\php.ini
C:\xampp\php\php.ini
```

Once opened, paste:
```
extension=php_sqlsrv.dll
extension=php_pdo_sqlsrv.dll
```

**Note: Preferably paste these two lines under Windows Extensions.**

Now all that's left is to save the file and restart apache to start using SQL through PDO.

* http://php.net/manual/en/book.pdo.php
* http://php.net/manual/en/ref.pdo-sqlsrv.connection.php
