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

###2. Atributos aplicables a la etiqueta script

1. **_async_**. Indica que el script se ejecutará de forma asíncrona, lo que significa que no bloqueará la carga de la página web mientras se descarga y ejecuta el script.

```JS
<script src="mi-script.js" async></script>
```

2. **_integrity_**. Se utiliza junto con el atributo "src". Se utiliza para proporcionar una medida de seguridad al cargar recursos externos, como archivos JavaScript o CSS, desde un servidor web. Este atributo garantiza que en la descarga del recurso no haya nada malicioso.

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

5. **_defer_**. Indica que el script se ejecutará después de que la página entera haya sido analizada, pero antes de que se complete la carga. Esto permite que la página continúe cargándose mientras se descarga el script. A diferencia de "async", los scripts con el atributo "defer" se ejecutan en orde.

```JS
script src="mi-script.js" defer></script>
```

6. **_crossorigin_**. Se utiliza para controlar cómo se manejan las solicitudes cuando se solicitan recursos desde un dominio diferente al de la página web actual. Este atributo mejora la seguridad y garantiza que los recursos externos sean confiables. Tiene dos valores principales:
   - _anonymous_. El recurso se solicita sin incluir credenciales de autenticación del usuario.
   - _use-credentials_. Indica que se deben incluir las credenciales del usuario al realizar la solicitud.
