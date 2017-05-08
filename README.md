# Phalcon-Multiples-modulos-esqueleto
Esqueleto para construir multiples modulos en phalcon

1. Dentro de la carpeta apps tendra un modulo frontend 

2. Duplicar la carpeta frontend y cambiarle el nombre a admin

3. cd admin/  y modificar el archivo Module.php
   * Localizar el namespace
   
   > namespace Wil\Frontend;
   cambiar a
   > namespace Wil\Admin;
   * Localizar el $loader
   ``` php
        $loader->registerNamespaces(array( 
            'Wil\Frontend\Controllers' => __DIR__ . '/controllers/',
            'Wil\Frontend\Models' => __DIR__ . '/models/',
        ));
   ```
   cambiar a
   ``` php
        $loader->registerNamespaces(array(
            'Wil\Admin\Controllers' => __DIR__ . '/controllers/',
            'Wil\Admin\Models' => __DIR__ . '/models/',
        ));
   ```
3.  cd controllers/   dentro de la carpeta de admin
    * Editar el archivo ControllerBase.php
    > namespace Wil\Frontend\Controllers;
    cambiar a
    > namespace Wil\Admin\Controllers;
    * Editar el archivo IndexController.php
    > namespace Wil\Frontend\Controllers;
    cambiar a
    > namespace Wil\Admin\Controllers;
        
4.  cd admin/views/index/index.phtml
    * Editar el archivo
    > Congratulations!
    cambiar a
    > Felicidades estas en la vista del administrador
      
5.  cd wil/config
    * Editar el archivo de modules.php, vamos a registrar nuestro modulo de admin
    ``` php
      'frontend' => array(
          'className' => 'Wil\Frontend\Module',
          'path' => __DIR__ . '/../apps/frontend/Module.php'
      )
    ```
    agregar la siguiente linea
    ```
      'admin' => array(
        'className' => 'Wil\Admin\Module',
        'path' => __DIR__ . '/../apps/admin/Module.php'
      )
    ```
URL for [front end](http://localhost/Wil/)
URL for [Backend Admin](http://localhost/Wil/admin)


======
