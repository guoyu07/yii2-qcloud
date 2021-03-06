# yii2-qcloud

适用于Yii2的[腾讯云](http://www.qcloud.com)API接口类。

Installation
------------

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```
php composer.phar require --prefer-dist xutl/yii2-qcloud
```

or add

```
"xutl/yii2-qcloud": "~1.0.0"
```

to the require section of your `composer.json` file.

配置
----

To use this extension, you have to configure the Connection class in your application configuration:

```php
return [
    //....
    'components' => [
        'qcloud' => [
            'class' => 'xutl\qcloud\Qcloud',
            'secretId' => 'abcdefg',
            'secretKey' => 'abcdefg',
        ],
    ]
];
```

使用
----

```php
use xutl\qcloud\Qcloud;

/** var Qcloud $qcloud */
$qcloud = Yii::$app->qcloud;
$wenzhi = $qcloud->createRequest(Qcloud::API_WENZHI,'gz');
$package = [
            'title'=>'啦啦啦啦啦啦',
            "content"=>"操"
        ];
print_r($wenzhi->TextKeywords($package));
```

资源
-----

* [公共参数](http://wiki.qcloud.com/wiki/%E5%85%AC%E5%85%B1%E5%8F%82%E6%95%B0)
* [API列表](http://wiki.qcloud.com/wiki/API)
* [错误码](http://wiki.qcloud.com/wiki/%E9%94%99%E8%AF%AF%E7%A0%81)