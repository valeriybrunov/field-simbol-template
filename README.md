## Field-simbol-template плагин для CakePHP

### Что может этот плагин?

Помогает пользователю вводить текст по шаблону в текстовом поле.

### Установка

Вы можете установить этот плагин в свое приложение CakePHP с помощью [composer](https://getcomposer.org).

Рекомендуемый способ установки пакетов composer - это:

```
composer require your-name-here/field-simbol-template
composer dumpautoload
bin/cake plugin load Field-simbol-template
```

### Использовать

```php
<?= $this->Webcomp->fieldSimbolTemplate() ?>
```

### Настройки:

Настройки указываются ввиде массива:

```php
<?php echo
    $this->Webcomp->fieldSimbolTemplate([
        'template' => '__/__',
        ...
    ]);
?>
```

#### template

Строка, содержащая шаблон для ввода текста. Символ подчёркивания (\_) в шаблоне используется для
замены символами ввода. По умолчанию используется шаблон ввода номера сотового телефона:

> 'template' => '+7(\_\_\_)\_\_\_-\_\_-\_\_',

#### input

Определяет какие значение можно вводить в шаблон, фильтрует ввод символов при вводе:
     
> Любые значения (буквы и цифры): 'input' => 'all', (по умолчанию)

> Только цифры: 'input' => 'numbers',

> Только буквы: 'input' => 'letters',

#### displayInput

Как отображает ввод символов с клавиатуры:

> Показывать ввод символов в шаблоне, заменяя символ подчёркивания (\_): 'displayInput' => 'full', (по умолчанию)

> Не показывать правую часть шаблона при вводе символов: 'displayInput' => 'right-crop',

#### clearFormFocus

Что делать с содержимым текстового поля при появление или потери фокуса (устанавливает режимы):

> Текстовое поле "при потери фокуса" очищается и показывается содержимое атрибута "placeholder",
> даже если часть символов введена. "При возникновение фокуса" текстовое поле очищается и
> набор начинается заново: ```php 'clearFormFocus' => 'y', (по умолчанию) ```

> Текстовое поле не очищается "при потери фокуса". Если не набрано ни единого символа, показывается
> "placeholder". Если введены часть символов, они остаются. "При появление фокуса" в текстовом
> поле, набор продолжается с того места, где остановился набор символов:
>> 'clearFormFocus' => 'n',

> !!! Для всех режимов: если введены все символы в соответствии с шаблоном, то при "потери фокуса" или "появление фокуса" набранный текст отображается;

#### placeholder

Текст, который отобразится в текстовом поле при потери фокуса.

> 'placeholder' => 'Текст',

