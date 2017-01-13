---
layout: post
title: WordPress Siteye İndex.html Giriş Sayfası Oluşturma
date: 2015-08-26 13:20
author: ahmetgurel
comments: true
categories: [.htaccess, canonical.php, index, index sayfası olusturma, WordPress, wordpress, wordpress de giriş sayfası oluşturmak, wordpress ındex olusturma, wp-includes/canonical.php]
---
WordPress sitenize sizde bir giriş sayfası oluşturmak isterseniz benim izlediğim yolu izleyerek yapabilirsiniz.Şimdi öncelikle index.html dosyası oluşturarak istediğiniz giriş sayfasını oluşturmalısınız.Daha sonra bu dosyaya FTP nize yukleceksiniz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/08/1.png"><img class="alignnone size-full wp-image-444" src="http://www.gurelahmet.com/wp-content/uploads/2015/08/1.png" alt="1" width="1006" height="312" /></a>

Buraya kadar olan kısım basit peki şimdi bu dosyayı wordpress nasıl tanıyacak yada asıl sitenize nasıl yönlendirecek asıl sorun burada başlıyor.Genelde oluşturduğumuz index.html sayfası açılıyor fakat yönlendirme sorunları çıkıyor.Bunun içinde iki tane dosyayı duzenleyerek bu sorunu çözmekteyiz.

<strong>1-</strong> İlk olarak <strong>.htaccess  </strong>dosyasına   <strong>DirectoryIndex index.html  index.php </strong>satırını ekliyoruz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/08/2.png"><img class="alignnone size-full wp-image-445" src="http://www.gurelahmet.com/wp-content/uploads/2015/08/2.png" alt="2" width="1023" height="403" /></a>

<strong>2- wp-includes/canonical.php</strong> <strong> </strong>dosyasını açıyoruz.Aşağıdaki yeri buluyoruz.

[php]
    // Some PHP setups turn requests for / into /index.php in REQUEST_URI 
    // See: http://trac.wordpress.org/ticket/5017 
    // See: http://trac.wordpress.org/ticket/7173 
    // Disabled, for now: 
    // $original['path'] = preg_replace('|/index\.php$|', '/', $original['path']);[/php]

Daha sonra en alt satırdaki kodu yorum satırından çıkarıyoruz.

[php]
    // Some PHP setups turn requests for / into /index.php in REQUEST_URI 
    // See: http://trac.wordpress.org/ticket/5017 
    // See: http://trac.wordpress.org/ticket/7173 
    // Disabled, for now: 
       $original['path'] = preg_replace('|/index\.php$|', '/', $original['path']); [/php]

<img class="alignnone size-large wp-image-449" src="http://www.gurelahmet.com/wp-content/uploads/2015/08/3-1024x537.png" alt="3" width="976" height="512" />

Bu adımları tamamladıysanız başarılı bir şekilde index.html giriş sayfanız oluşmuştur güle güle kullanın :)

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/08/Screenshot-from-2015-08-26-133538.png"><img class="alignnone size-large wp-image-453" src="http://www.gurelahmet.com/wp-content/uploads/2015/08/Screenshot-from-2015-08-26-133538-1024x519.png" alt="Screenshot from 2015-08-26 13:35:38" width="976" height="495" /></a>
