![Image Text](imagenes/descarga.png "Imagen superficial")
#UNIDAD 1

##TAREA 2

###1. Ventajas de incorporar el script desde un fichero externo frente a hacerlo en línea (código javascript directamente en el fichero HTML)

- Se cumple el principio de diseño de separación y hace que todo sea mucho más sostenible y reutilizable.
- La legibilidad y mantenimiento del código HTML es mucho más fácil. El HTML es más ligero y rápido de cargar.
- Proporciona mejores herramientas de depuración en los navegadores.
- Facilita la colaboración en equipos de desarrollo.
- Los navegadores pueden cachear archivos externos, acelerando la carga de páginas posteriores.
- Se puede implementar políticas de Content Security Policy (CSP) de manera más controlada y segura, limitando las fuentes de las cuales se pueden cargar recursos en la página web y reduciendo el riesgo de ataques de seguridad.

Ejemplo de script en un fichero externo:

- Archivo JavaScript:

```JS
function saludar() {
    alert("¡Hola desde el archivo separado!");
}
```

A continuación hay que enlazar el archivo JavaScript en el HTML:

- Archivo HTML:

```HTML
<!DOCTYPE html>
<html>
<head>
    <title>Ejemplo de Script en Archivo Separado</title>
</head>
<body>
    <h1>Hola, Mundo!</h1>

    <script src="mi_script.js"></script>
    <script>
        saludar();
    </script>
</body>
</html>
```

###2. Atributos aplicables a la etiqueta \<script>

1. **_async_**. Indica que el script se ejecutará de forma asíncrona, lo que significa que no bloqueará la carga de la página web mientras se descarga y ejecuta el script.

```JS
<script src="mi-script.js" async></script>
```

2. **_integrity_**. Se utiliza junto con el atributo "src" para proporcionar una medida de seguridad al cargar recursos externos, como archivos JavaScript o CSS, desde un servidor web. Este atributo garantiza que en la descarga del recurso no haya nada malicioso.

```JS
<script
  src="https://example.com/example-framework.js"
  integrity="sha384-oqVuAfXRKap7fdgcCY5uykM6+R9GqQ8K/uxy9rx7HNQlGYl1kPzQho1wx4JwY8wC"
  crossorigin="anonymous"></script>
```

3. **_src_**. Especifica la URL del archivo externo.

```JS
<script src="mi-script.js"></script>
```

4. **_type_**. Indica el tipo de contenido del script. Los valores están especificados como un MIME type, algunos son: text/javascript, text/ecmascript, application/javascript y application/ecmascript.
   Si el atributo está ausente, por defecto será un script JavaScript.

```JS
<script type="text/javascript" src="mi-script.js"></script>
```

5. **_defer_**. Indica que el script se ejecutará después de que la página entera haya sido analizada, pero antes de que se complete la carga. Esto permite que la página continúe cargándose mientras se descarga el script. A diferencia de "async", los scripts con el atributo "defer" se ejecutan en orden.

```JS
script src="mi-script.js" defer></script>
```

6. **_crossorigin_**. Se utiliza para controlar cómo se manejan las solicitudes cuando se solicitan recursos desde un dominio diferente al de la página web actual. Este atributo mejora la seguridad y garantiza que los recursos externos sean confiables. Tiene dos valores principales:
   - _anonymous_. El recurso se solicita sin incluir credenciales de autenticación del usuario.
   - _use-credentials_. Indica que se deben incluir las credenciales del usuario al realizar la solicitud.

### 3. Atributos por defecto

El único atributo por defecto es **_type_**. Se utiliza para indicar el tipo de contenido del script, su valor más común es "text/javascript" pero también puede tener otros valores como "text/typescript" para TypeScript y "text/css" para CSS.
Si se omite el atributo type, su valor por defecto será "text/javascript".

- Con atributo type:

```JS
<script type="text/javascript">
    alert("¡Hola, mundo!");
</script>
```

- Sin atributo type:

```JS
<script>
    alert("¡Hola, mundo!");
</script>
```

### 4. Atributos booleanos. Qué implican

Estos atributos influyen en cómo se carga y ejecuta el código JavaScript en una página web.

- **_async_**. Con este atributo, la descarga del script se realiza de manera asíncrona mientras se sigue analizando la web. El script se ejecuta nada más descargarse independientemente del estado de carga de la web.
  No existe ningún orden de ejecución de los scripts, se ejecutarán conforme se vayan descargando.
  Este atributo se utiliza cuando no es necesario un orden de ejecución de scripts y cuando éstos no dependen del contenido HTML o de otros scripts.  
   <br>
- **_defer_**. La descarga del script se realiza de manera asíncrona mientras se sigue analizando la web, con la diferencia de que la ejecución del script se pospone hasta que se haya analizado completamente la web y que estos se van ejecutando en el orden en que aparece en el código fuente.
  Se usa cuando se desea mantener el orden de ejecución y para asegurarnos de que la web se ha cargado completamente antes de ejecutar el código JavaScript.

### 5. Sitio recomendado para colocar la etiqueta \<script>

Antes de que apareciesen los atributos async y defer, el sitio recomendado para los scripts era al final del documento html, ya que cuando se colocaba al principio, el navegador lo descargaba antes de continuar con el análisis y esto era lento para los usuarios porque debían esperar a que se procesara todo el código JavaScript, antes de ver algo en la pantalla.

Otra razón por la que se colocaba al final del documento es por la compatibilidad de los navegadores antiguos ya que algunos no gestionaban bien los scripts colocados en el encabezado del documento.

Con los atributos async y defer, los scripts se pueden colocar en cualquier parte del documento ya que permiten la carga asíncrona. El navegador puede continuar cargando y mostrando la página mientras los scripts se descargan y ejecutan en segundo plano.

### 6. Etiqueta \<noscript>. Utilidad, atributos y dónde colocar

Esta etiqueta se utiliza para proporcionar contenido o instrucciones cuando el navegador no soporta la ejecución de scripts o cuando están deshabilitados en la configuración del navegador.

La etiqueta \<noscript> no admite atributos, su uso es sencillo y se puede colocar tanto en el \<head> como en el \<body>:

1. En el \<head>. Se coloca para proporcionar instrucciones globales o metadatos que no pueden ejecutar scripts:

```JS
<head>
   <noscript>
      <meta http-equiv="refresh" content="5;url=noscript.html">
   </noscript>
</head>
```

2. En el \<body>. Para indicar que el navegador no permite la ejecución del script que se está intentando ejecutar.

```JS
<p>Este es un párrafo de texto normal.</p>
<noscript>
   <p>El navegador no admite JavaScript o los scripts están deshabilitados.</p>
</noscript>
```
