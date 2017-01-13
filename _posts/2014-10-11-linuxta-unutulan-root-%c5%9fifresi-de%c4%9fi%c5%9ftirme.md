---
layout: post
title: Linux'ta Unutulan Root Şifresi Değiştirme
date: 2014-10-11 17:03
author: ahmetgurel
comments: true
categories: [Linux, linux, linux root şifresi, linux root şifresi değiştirme, root, unutulan root şifresi]
---
Linux ta bildiğiniz gibi bazı işlemleri gerçekleştirebilmeniz için root yetkilerine sahip olmanız gerekir.Program yükleyip kaldıracağınız zaman,sistem dosyalarında değişiklik yapacağınız zaman root yetkisi gerekir  fakat bazen root şifresi unutulabiliyor hele ki yeni kullanıcıların çok başına gelmektedir.Bu yazımda Debian(Ubuntu,Mint,Kali,Pardus...) dağıtımlarında unutulan root şifresini yeniden oluşturmayı anlatacağım.Önümüze gelen grub ekranı aşağıda ki görselde mevcut grub ekranında E tuşuna basarak EDIT hala getireceğiz.

[caption id="attachment_236" align="alignnone" width="584"]<a href="http://www.gurelahmet.com/wp-content/uploads/2014/10/0.png"><img class="size-full wp-image-236" src="http://www.gurelahmet.com/wp-content/uploads/2014/10/0.png" alt="Grub Ekranı" width="584" height="414" /></a> Grub Ekranı[/caption]

[caption id="attachment_237" align="alignnone" width="623"]<a href="http://www.gurelahmet.com/wp-content/uploads/2014/10/11.jpg"><img class="size-full wp-image-237" src="http://www.gurelahmet.com/wp-content/uploads/2014/10/11.jpg" alt="Grub Ekranında E ye Bastıktan Sonra" width="623" height="448" /></a> Grub Ekranında E ye Bastıktan Sonra Edit Hali[/caption]

Şimdi yukarıda ki görselde kırmızı ile çizilmiş kısımlar bizim için önemli ro yazan yerde ki yolu değiştirdikten sonra Ctrl-x yada F10 ile boot ederek sistemi root olarak açacağız.

<a href="http://www.gurelahmet.com/wp-content/uploads/2014/10/3.jpg"><img class="alignnone size-full wp-image-238" src="http://www.gurelahmet.com/wp-content/uploads/2014/10/3.jpg" alt="linux grub" width="691" height="520" /></a>

ro ve sonrasını silerek  rw quiet init=/bin/bash yazarak  CTRL+X yada F10 ile boot edeceğiz.Bu arada ro ve rw kernel parametreleridir.ro default olarak gelen sadece okuma iznini barındırıyor rw ise okumanın yanında yazma yetkisinide barındırıyor.ro yu kullansak yazma yetkımızın olmamasından dolayı bir hata alabilirdik.

<a href="http://www.gurelahmet.com/wp-content/uploads/2014/10/41.png"><img class="alignnone size-full wp-image-239" src="http://www.gurelahmet.com/wp-content/uploads/2014/10/41.png" alt="linux grub" width="806" height="495" /></a>

Boot ettikten sonra sistem root olarak açılıyor. passwd komutunu girerek yeni şifre belirleyeceğiz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2014/10/61.png"><img class="alignnone size-full wp-image-242" src="http://www.gurelahmet.com/wp-content/uploads/2014/10/61.png" alt="6" width="861" height="572" /></a>

Resimdeki gibi komutu girdikten sonra yeni şifre oluşturmamızı isteyecek ve bunu tekrar girmemizi isteyecek.

<a href="http://www.gurelahmet.com/wp-content/uploads/2014/10/71.png"><img class="alignnone size-full wp-image-243" src="http://www.gurelahmet.com/wp-content/uploads/2014/10/71.png" alt="7" width="847" height="563" /></a>

Resimde gördüğünüz gibi işlem başarı ile gerçekleşti  passwd: password updated successfully gibi bir çıktı aldık.Artık şifreniz yeniden oluşturulmuştur güle güle kullanınız :) Başka bir yazıda görüşmek üzere :)


<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-65335586-1', 'auto');
  ga('send', 'pageview');

</script>
