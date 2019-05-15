# EMTypograph

Типограф от Евгения Муравьёва

Официальный сайт типографа: [http://mdash.ru/](http://mdash.ru/)

## Установка

### Composer

Предпочтительным способом установки этого расширения является [Composer](http://getcomposer.org/).

Запустите команду 
```
composer require karelwintersky/EMTypograph
```

или добавьте ```"karelwintersky/EMTypograph": "^0.1"``` в секцию зависимостей в файле ```composer.json```

## Использование

1. Запуск типографа с настройками по умолчанию:
```
use karelwintersky\EMTypograph\EMTypograph;
 
$typograf = new EMTypograph();
$typograf->set_text("...Когда В. И. Пупкин увидел в газете ( это была &quot;Сермяжная правда&quot; № 45) рубрику Weather Forecast(r), он не поверил своим глазам - температуру обещали +-451F.");
$result = $typograf->apply();
echo "<i>Настройки по умолчанию</i>: " . $result . "\n";
```

2. Ручная настройка правил:
```
use karelwintersky\EMTypograph\EMTypograph;
 
$typograf = new EMTypograph();
$typograf->set_text("...Когда В. И. Пупкин увидел в газете ( это была &quot;Сермяжная правда&quot; № 45) рубрику Weather Forecast(r), он не поверил своим глазам - температуру обещали +-451F.");
$typograf->setup(array(
	'Text.paragraphs' => 'off',
	'OptAlign.oa_oquote' => 'off',
	'OptAlign.oa_obracket_coma' => 'off',
));
$result = $typograf->apply();
echo "<i>Без параграфов, висячей пунктуации</i>: " . $result . "<br><br>\n";
```

3. Быстрый запуск типографа с настройками по умолчанию:
```
use karelwintersky\EMTypograph\EMTypograph;
 
$result = EMTypograph::fast_apply("...Когда В. И. Пупкин увидел в газете ( это была &quot;Сермяжная правда&quot; № 45) рубрику Weather Forecast(r), он не поверил своим глазам - температуру обещали +-451F.");
echo "<i>Быстрый запуск</i>: " . $result . "<br>\n";
```

4. Быстрый запуск типографа с ручными настройками:
```
use karelwintersky\EMTypograph\EMTypograph;
 
$result = EMTypograph::fast_apply("...Когда В. И. Пупкин увидел в газете ( это была &quot;Сермяжная правда&quot; № 45) рубрику Weather Forecast(r), он не поверил своим глазам - температуру обещали +-451F.",array(
	'Text.paragraphs' => 'off',
	'OptAlign.oa_oquote' => 'off',
	'OptAlign.oa_obracket_coma' => 'off',
));
echo "<i>Быстрый запуск настройками</i>: " . $result . "<br><br>\n";
```

5. Ручная настройка правила - использования css классов вместо inline стилей:
```
use karelwintersky\EMTypograph\EMTypograph;
 
$typograf = new EMTypograph();
$typograf->set_text("...Когда В. И. Пупкин увидел в газете ( это была &quot;Сермяжная правда&quot; № 45) рубрику Weather Forecast(r), он не поверил своим глазам - температуру обещали +-451F.");
$typograf->setup(array(
	'OptAlign.layout' => 'class',
));
$result = $typograf->apply();
echo "<i>Классы вместо инлайн стилей</i>: " . $result . "<br><br>\n";
```

## Автор

Authors: Evgeny Muravjev & Alexander Drutsa  

Доработка: Karel Wintersky <karel.wintersky@gmail.com>

