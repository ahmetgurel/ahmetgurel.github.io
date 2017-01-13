---
layout: post
title: Linux DNS Değiştirme
date: 2014-10-06 16:14
author: ahmetgurel
comments: true
categories: [dns, Linux, linux, linux dns, linux dns degistirme]
---
DNS(Domain Name System) nedir?

Türkçe olarak Alan Adı Sistemi olan DNS girdiğimiz sitelerin IP adresini tutan bir adres defteri gibidir.Girdiğimiz bir domain tıkladığımızda kullandığımız DNS bizi yönlendirdiği için bazen ulaşamama durumları oluyor farklı nedenlerden o IP yı engellıyorlar ve bu site yasaklanmıştır diyor bizde bunun için farklı DNS ler kullanarak erişimimize devam ediyoruz :)

Türkiyede yasaklanan sitelerden zamanında youtube,twitter gibi sitelerde girdiği için herkes DNS değiştirmeyi ve yardımcı proğramlar,browserler kullanmayı öğrendi sanırım yasakların tek iyi sonucu :)

Fakat Linux biraz daha az kullanıldığı için her yerde windows için anlatılıyor.Durum böyle olunca bende Linux a yeni başlamış arkadaşların işine yarayabilir diye Linuxta DNS Değiştireceğim :)

Linuxta DNS adresleri /etc dizinin altınta resolv.conf  dosyasında tutuluyor. (.conf configuration  dan geliyor ayar,yapılandırma dosyası demektır.)

<a href="http://www.gurelahmet.com/wp-content/uploads/2014/10/11.png"><img class="alignnone size-full wp-image-200" src="http://www.gurelahmet.com/wp-content/uploads/2014/10/11.png" alt="1" width="561" height="124" /></a>

sudo ile root yetkisi alarak resolv.conf  ayar dosyasını vim editörü ile açtık.(vim editörü yüklü değil ise "sudo apt-get install vim" komutu ile yükleyebilir yada nano ve vi  editörlerinden birini kullanabilirsiniz.)

<a href="http://www.gurelahmet.com/wp-content/uploads/2014/10/2.png"><img class="alignnone size-full wp-image-201" src="http://www.gurelahmet.com/wp-content/uploads/2014/10/2.png" alt="2" width="550" height="362" /></a>

Default olarak gelen DNS imiz 127.0.1.1 adresini görüyoruz biz bunu Google'ın DNS i olan 8.8.8.8 /8.8.4.4 ile değiştireceğiz.Bunun için "i" tuşuna basarak editörümüzü INSERT hale getireceğiz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2014/10/31.png"><img class="alignnone size-full wp-image-202" src="http://www.gurelahmet.com/wp-content/uploads/2014/10/31.png" alt="3" width="563" height="361" /></a>

DNS imizi böyle girdikten sonra "ESC" tuşuna basarak ":wq" yazarak vim editörüne kaydet ve çık komutunu vermiş olduk.Fakat bu yaptığımız işlem bilgisayar yeniden başlattığımızda silinip eski halini alacak.Bunun için bizde
<pre style="font-family: Andale Mono, Lucida Console, Monaco, fixed, monospace; color: #000000; background-color: #eee; font-size: 12px; border: 1px dashed #999999; line-height: 14px; padding: 5px; overflow: auto; width: 50%;"><code>chattr +i /etc/resolv.conf 
</code></pre>
komutunu vererek işlemimizi kalıca hale getireceğiz.Chattr +i dosyamızı kilitlemeye yarayan komuttur.Ileri okuma için lütfen <a href="http://belgeler.gen.tr/man/man1/man1-chattr.html">tıklayınız.</a>

<a href="http://www.gurelahmet.com/wp-content/uploads/2014/10/Screenshot-from-2014-10-06-154253.png"><img class="alignnone size-full wp-image-203" src="http://www.gurelahmet.com/wp-content/uploads/2014/10/Screenshot-from-2014-10-06-154253.png" alt="Screenshot from 2014-10-06 15:42:53" width="373" height="78" /></a>

Yazım burada sona eriyor başka bir yazıda görüşmek üzere :)


<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-65335586-1', 'auto');
  ga('send', 'pageview');

</script>
