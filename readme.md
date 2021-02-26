
Imagick for PHP 8
=================
**2021.02**

![wizard](wizard.jpg)


As You probably know, we still wait for official release of imagick for php8.

So at this moment we need not official releases. 

----------
 1. Mac
 
   
For MAC installation is relay simple with homebrew

```
brew tap shivammathur/extensions
brew install imagick@8.0
```

----------

 2. Windows


| PHP  |  Architecture | Thread Safe  |  Non Thread Safe | ImageMagick |
|------|---------------|--------------|------------------|----------------|
| 8.0  | x64   | [php_imagick-3.4.4-dev x64 ts](./8.0/x64/ts/php_imagick.zip) | [php_imagick-3.4.4-dev x64 nts](./8.0/x64/nts/php_imagick.zip) | [ImageMagick-7.0.11 x64.zip](./IM/ImageMagick-7.0.11-Q16-HDRI.zip)
| 8.0  | x86   | [php_imagick-3.4.4-dev x86 ts](./8.0/x86/ts/php_imagick.zip) | [php_imagick-3.4.4-dev x86 nts](./8.0/x86/nts/php_imagick.zip) | [ImageMagick-7.0.11 x86.zip](./IM/ImageMagick-7.0.11-Q16-HDRI-x86.zip)




Once you downloaded the correct files:

  1.  Extract from `php_imagick-….zip` the `php_imagick.dll` file, and save it to the ext directory of your PHP installation
  2.  Extract from `ImageMagick-….zip` files and directory and save them to the PHP root directory (where you have php.exe), or to a directory in your PATH variable
  3.  Add this line to your `php.ini` file:
    `extension=php_imagick.dll`
  4.  Restart the Apache/NGINX Windows service (if applicable)


--------------

To test if the extension works, you can run this PHP code:

```PHP
<?php
$image = new Imagick();
$image->newImage(1, 1, new ImagickPixel('#ffffff'));
$image->setImageFormat('png');
$pngData = $image->getImagesBlob();
echo strpos($pngData, "\x89PNG\r\n\x1a\n") === 0 ? 'Ok' : 'Failed'; 

```

-------------

Versions for older PHP version as available on 
https://mlocati.github.io/articles/php-windows-imagick.html



Thanks for great article with examples: https://jite.eu/2021/2/21/imagick-on-php8/
