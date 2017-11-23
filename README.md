# File Manager PHP

Una buena solucion para manejar archivos y carpetas para desarrolladores que no pueden accesar por medio de SSH y FTP.

![PHP File Manager](https://raw.github.com/alexantr/filemanager/master/phpfm.png)

**¡ADVERTENCIA! No use este script como administrador de archivos normal en el área pública.
Después de todas las acciones, debe eliminar este script del servidor.**

## Requisitos

- PHP 5.2 en adelante.
- [Zip extension](http://php.net/manual/en/book.zip.php) para comprimir y descomprimir.
- Fileinfo, iconv and mbstring extensions are strongly recommended.

## Como usarlo

Descarga el archivo **Zip** con la última versión de la rama maestra.

### Paso #1
Copia **filemanager.php** a tu sitio web y abrelo con su navegador.
(e.g. http://tusitioweb.com/carpeta/filemanager.php).

## Seguridad

Usuario y contraseña por defecto: **admin**/**admin123**

**Warning! Please set your own username and password in `$auth_users` before use.**

To enable or disable authentication set `$use_auth` to `true` or `false`.

*For better security enable HTTP Authentication in your web server.*

## Embedding

You can include file manager in another scripts. Just define `FM_EMBED` and other necessary constants. Example:

```php
class SomeController
{
    public function actionIndex()
    {
        define('FM_EMBED', true);
        define('FM_SELF_URL', UrlHelper::currentUrl()); // must be set if URL to manager not equal PHP_SELF
        require 'path/to/filemanager.php';
    }
}
```

Supported constants:

- `FM_ROOT_PATH` - default is `$_SERVER['DOCUMENT_ROOT']`
- `FM_ROOT_URL` - default is `'http(s)://site.domain/'`
- `FM_SELF_URL` - default is `'http(s)://site.domain/' . $_SERVER['PHP_SELF']`
- `FM_ICONV_INPUT_ENC` - default is `'CP1251'`
- `FM_USE_HIGHLIGHTJS` - default is `true`
- `FM_HIGHLIGHTJS_STYLE` - default is `'vs'`
- `FM_DATETIME_FORMAT` - default is `'d.m.y H:i'`

## Alternatives

- [Tiny PHP File Manager](https://github.com/prasathmani/tinyfilemanager) with search and file editor
- [simple php filemanager](https://github.com/jcampbell1/simple-file-manager)

## Bug tracker

If you have any issues with file manager, you may report them on
[Issue tracker](https://github.com/alexantr/filemanager/issues).

## License

This software is released under the MIT license.

Icons by [Yusuke Kamiyamane](http://p.yusukekamiyamane.com/).
