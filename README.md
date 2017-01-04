# Phalcon-Multiples-modulos-esqueleto
Esqueleto para construir multiples modulos en phalcon

* dentro de la carpeta apps tendra un modulo frontend 

1.  Duplicar la carpeta frontend y cambiarle el nombre a admin

2.  cd admin/  y modificar el archivo Module.php <br>
    * Localizar el namespace <br>
        namespace Wil\Frontend;  <br>
      <b>cambiar a</b>  <br>
        namespace Wil\Admin;
    * Localizar el $loader <br>
        $loader->registerNamespaces(array( <br>
            'Wil\Frontend\Controllers' => __DIR__ . '/controllers/',  <br>
            'Wil\Frontend\Models' => __DIR__ . '/models/',  <br>
        )); <br>
      <b>cambiar a</b>  <br>
        $loader->registerNamespaces(array( <br>
            'Wil\Admin\Controllers' => __DIR__ . '/controllers/',  <br>
            'Wil\Admin\Models' => __DIR__ . '/models/',  <br>
        ));

3.  cd controllers/   dentro de la carpeta de admin
    * Editar el archivo ControllerBase.php <br>
        namespace Wil\Frontend\Controllers; <br>
      <b>cambiar a</b>  <br>
        namespace Wil\Admin\Controllers; <br>
    * Editar el archivo IndexController.php <br>
        namespace Wil\Frontend\Controllers;  <br>
      <b>cambiar a</b>  <br>
        namespace Wil\Admin\Controllers; <br>
        
4.  cd admin/views/index/index.phtml
    * Editar el archivo <br>
      <h1>Congratulations!</h1>
    <b>cambiar a</b>  <br>
      <h1> Felicidades estas en la vista del administrador </h1>
      
5.  cd wil/config
    *Editar el archivo de modules.php, vamos a registrar nuestro modulo de admin <br>
      'frontend' => array( <br>
          'className' => 'Wil\Frontend\Module',  <br>
          'path' => __DIR__ . '/../apps/frontend/Module.php'  <br>
      ) <br>
    agregar la siguiente linea <br>
      'admin' => array( <br>
        'className' => 'Wil\Admin\Module', <br>
        'path' => __DIR__ . '/../apps/admin/Module.php' <br>
      ) <br>

URL for front end : http://localhost/Wil/ <br>
URL for Backend Admin : http://localhost/Wil/admin


------------------------------    O.O   ----------------------------------------------------
