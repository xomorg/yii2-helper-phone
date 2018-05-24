Yii2 Phone
========================
Formatting a phone number for Yii 2 framework.

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```bash
$ php composer.phar require --prefer-dist xomorg/yii2-helper-phone "*"
```

or add

```json
"xomorg/yii2-helper-phone": "*"
```

to the `require` section of your `composer.json` file.


Usage
-----

First, you need to connect the class. That's it!

```php
use xomorg\helpers\Phone;
```

### Default

Easy to use with no additional setup:

```php
echo Phone::format("89131234567");  // 8 (913) 123-45-67
echo Phone::format("+38 (044) 226-22-04");  // +380 (44) 226-22-04
echo Phone::format("0038 (044) 226-22-04"); // +380 (44) 226-22-04
echo Phone::format("+79263874815"); // +7 (926) 387-48-15
echo Phone::format("4816145");  // 481-61-45
echo Phone::format("+44 (0) 870 770 5370"); // +44 (0870) 770-53-70
echo Phone::format("0044 (0) 870 770 5370");    // +44 (0870) 770-53-70
echo Phone::format("+436764505509");    // +43 (6764) 50-55-09
echo Phone::format("(+38-048) 784-15-46 "); // 380 (4878) 415-46
echo Phone::format("(38-057) 706-34-03 ");  // 380 (5770) 634-03
echo Phone::format("+38 (044) 244 12 01 "); // +380 (44) 244-12-01
```

### Extra settings

To display the country to which the phone number belongs, you must specify in the template _{country}_:

```php
echo Phone::format("89131234567", ['template'=>'{country} {phone}']);  // Russia 8 (913) 123-45-67 
```

If you think that the brackets are unnecessary, they can be removed:

```php
echo Phone::format("89131234567", ['removeBrackets'=>true]);  // 8 913 123-45-67 
```

You can also remove "+" and replace country code "8" with "+7"

```php
echo Phone::format("+79131234567", ['removePlus'=>true]);  // 7 (913) 123-45-67 
echo Phone::format("89131234567", ['replace8-7'=>true]);  // +7 (913) 123-45-67 
echo Phone::format("89131234567", ['replace8-7'=>true, 'removePlus'=>true]);  // 7 (913) 123-45-67
```

