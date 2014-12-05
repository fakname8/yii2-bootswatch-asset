yii2-bootswatch-asset
==========================
Asset bunlde around the Bootswatch theme suite. Visit [Bootswatch](http://bootswatch.com/) for more.

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist raoul2000/yii2-bootswatch-asset "*"
```

or add

```
"raoul2000/yii2-bootswatch-asset": "*"
```

to the require section of your `composer.json` file.


Usage
-----
To use a bootswatch theme in your Yii2 application add the BootswatchAsset bundle to your main AppAsset bundle:

```php

// ./assets/AppAsset.php

class AppAsset extends AssetBundle
{
    public $basePath = '@webroot';
    public $baseUrl = '@web';
    public $css = [
        'css/site.css',
    ];
    public $js = [
    ];
    public $depends = [
        'yii\web\YiiAsset',
    	'raoul2000\bootswatch\BootswatchAsset',
    ];
}
?>
```

Then at some point you must select the theme name you want to use. In the example below, the theme 'amelia' is set in the main layout.

```php

// ./views/layouts/main.php

raoul2000\bootswatch\BootswatchAsset::$theme = 'amelia';
AppAsset::register($this);

```

For more information on the plugin options, please refer to [yii2-bootswatch-asset@github](https://github.com/raoul2000/yii2-bootswatch-asset).

Warning
-------
If you're using Yii-2.0.0 (the first release) note that the debug toolbar will not be displayed correctly because of [this bug](https://github.com/yiisoft/yii2/issues/5402). It has been
fixed in the next release, but in the meantime, if you don't want to use the dev-master version, you can temporarly comment lines
 from 48 to 56 in `vendor/raoul2000/yii2-bootswatch-asset/BootswatchAsset.php`.   


License
-------

**yii2-bootswatch-asset** is released under the BSD 3-Clause License. See the bundled `LICENSE.md` for details.