rex_socket für REDAXO 4
=======================

Die Klassen benötigen mindesten PHP 5.3!

Beispiel
--------

```php
try {
    $socket = rex_socket::factory('www.example.com');
    $socket->setPath('/path/index.php?param=1');
    $response = $socket->doGet();
    if($response->isOk()) {
        $body = $response->getBody();
    }
} catch(rex_socket_exception $e) {
    // error message: $e->getMessage()
}
```

Einbindung
----------

Die Klassen `rex_socket` und `rex_socket_response` werden in jedem Fall benötigt, und müssen eingebunden werden (sie
können natürlich auch gemeinsam in einer Datei liegen).
Die Klasse `rex_socket_proxy` ist optional, und wird nur benötigt, wenn Verbindungen über Proxy-Server aufgebaut werden
sollen.
