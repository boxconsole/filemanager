# PHP File Manager Russian Translation
### Русский перевод
Хорошее решение для управления файлами и папками для разработчиков, которые не могут получить доступ к своему сайту через SSH или FTP.
![PHP File Manager](https://raw.github.com/alexantr/filemanager/master/phpfm.png)

**ПРЕДУПРЕЖДЕНИЕ! Не используйте этот скрипт как обычный файловый менеджер в публичных местах.
После всех действий вы должны удалить этот скрипт с сервера. **

## Требования

- PHP 5.2 или выше.
- [Расширение Zip] (http://php.net/manual/en/book.zip.php) для действий ZIP и распаковать.
- Настоятельно рекомендуется использовать расширения Fileinfo, iconv и mbstring.

## Как пользоваться

Загрузите ZIP с последней версией из главной ветки.

Скопируйте **filemanager.php** в папку вашего сайта и откройте его в веб-браузере
(например, http: //yoursite/any_path/filemanager.php).

## Безопасность

Имя пользователя / пароль по умолчанию: ** fm_admin ** / ** fm_admin **

**Warning! Please set your own username and password in `$auth_users` before use.**

Чтобы включить или отключить аутентификацию, установите для `$ use_auth` значение` true` или `false`.

*Для большей безопасности включите HTTP-аутентификацию на вашем веб-сервере.*

## Встраивание

Вы можете включить файловый менеджер в другой скрипт. Просто определите `FM_EMBED` и другие необходимые константы. Пример:

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

Поддерживаемые константы:

- `FM_ROOT_PATH` - по умолчанию установлено значение `'$_SERVER['DOCUMENT_ROOT']'`
- `FM_ROOT_URL` - по умолчанию `'http(s)://site.domain/'`
- `FM_SELF_URL` - по умолчанию `'http(s)://site.domain/' . $_SERVER['PHP_SELF']`
- `FM_ICONV_INPUT_ENC` - по умолчанию установлено значение` 'CP1251'`
- `FM_USE_HIGHLIGHTJS` - по умолчанию установлено значение` true`
- `FM_HIGHLIGHTJS_STYLE` - по умолчанию установлено значение` 'vs'`
- `FM_DATETIME_FORMAT` - по умолчанию установлено` 'd.m.y H: i'`

## Альтернативы

- [Tiny PHP File Manager] (https://github.com/prasathmani/tinyfilemanager) с поиском и редактором файлов
- [простой php файловый менеджер] (https://github.com/jcampbell1/simple-file-manager)

## Баг трекер

Если у вас есть какие-либо проблемы с файловым менеджером, вы можете сообщить о них на
[Отслеживание проблем] (https://github.com/alexantr/filemanager/issues).

## Лицензия

Это программное обеспечение выпущено под лицензией MIT.

Иконки типов файлов от [Юсуке Камиямане] (http://p.yusukekamiyamane.com/).
