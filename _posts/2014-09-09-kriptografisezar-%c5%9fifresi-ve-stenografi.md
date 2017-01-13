---
layout: post
title: Kriptografi,Sezar Şifresi ve Steganografi
date: 2014-09-09 15:56
author: ahmetgurel
comments: true
categories: [Genel Güvenlik, imagehide, kripto, kriptografi, kriptoloji, sezar şifrelemesi, Siber Güvenlik, stenografi, veri gizleme]
---
<strong>Kriptografi</strong> bilgi güvenliği kavramlarını sağlamak için çalışan matematiksel yöntemler bütünüdür.Yani gönderdiğiniz bir bilginin istemediğiniz kişilerce okunmaması için kullanılan tekniklerin(şifreleme) tümüdür.

<strong>Bilgi güvenliği kavramları:</strong>
<ul>
	<li>Gizlilik (<i>privacy/confidentiality</i>)</li>
	<li>Kimlik Denetimi (<i>authentication/identification)</i></li>
	<li>Bütünlük (<i>integrity</i>)</li>
	<li>Reddedilmezlik (<i>non-repudation</i>)</li>
	<li>Erişim Kontrolü (<i>access control</i>)</li>
</ul>
Temel olarak kriptografi bunlar üzerine kuruludur ve şifreleme kısmını halleder.

<strong>Kriptoanaliz</strong>  kriptografi ile şifrelenmiş dosyaların şifre analiz ederek şifreyi çözmeye dayanır.

<strong>Kriptoloji </strong>ise şifre bilimidir.Şifrelenmiş dosyaların güvenli olarak alıcıya ulaşması ve şifrenin analiz edilip doğru kişi tarafından okunmasını sağlamaktır.

<strong>Bazı şifreleme teknikleri:</strong>
<ul>
	<li>Sezar Şifrelemesi</li>
	<li>Steganografi(Veri Gizleme)</li>
	<li>Açık anahtarlı şifreleme</li>
	<li>Rotor makinası</li>
	<li>Çırpı fonksiyonları</li>
</ul>
Ben bu yazımda Sezar şifrelemesi ve Stenografi ye değineceğim.

<strong>1-Sezar Şifrelemesi</strong>

Sezar şifrelemesinde her harf  harf atlatılarak yazılır. "ahmet"  kelimesi üçlü sezar şifrelemesine göre "djphy" dir.(Latin alfabesi kullanılmıştır.Ö bu yüzden yok Türk alfabesi olarak düşünmeyiniz.)

<a href="http://www.gurelahmet.com/wp-content/uploads/2014/09/Sezar_sifresi.gif"><img class="size-medium wp-image-165 aligncenter" src="http://www.gurelahmet.com/wp-content/uploads/2014/09/Sezar_sifresi-300x157.gif" alt="Sezar_sifresi" width="300" height="157" /></a>

&nbsp;
<p style="text-align: center;">Üçlü Sezar Şifrelemesi</p>
<p style="text-align: left;">Sezar şifresi günümüzde pek kullanılmaz.Kriptolojinin atalarındandır.Kolaylıkla kırılabilmektedir.Kaç harf atladığını görerek çözülebileceği gibi Brute Force(Kaba Kuvvet) saldırısıyla Latin alfabesinin(25) elemanlarının hepsi denenerek bulunabilir.</p>
<p style="text-align: left;"><strong>2-Steganografi (Veri Gizleme)</strong></p>
Stenografi,  stenografi  alfabesi ile yazılan herhangi bir şeyi yine steno bilen kişiler okuyup anlayabiliyor.Mahkemelerde ve  meclis oturumlarında konuşmaların hızlı yazıya dökülmesi için kullanılmıştır.Tarihçesi böyledir.Steganografi ve stenografi  karışabilmektedir.

Steganografi ise veri gizleme demektir..Bir resmin içine yazı saklama, aynı zamanda müzik,video yada başka uzantılı dosyalara veri saklamak ve okumak için kullanılmaktadır.İnternette bununla ilgili bir çok program bulunmaktadır.Dosyaların içine veri yazıp ve şifrelemek için bunlardan bazıları:

<strong>1-ImageHide:</strong> Resim dosyalarının içine veri gizlemeyi ve şifrelemeye yarayan araçtır.

<strong>2-Mp3Stego:</strong>Bu araçta ses dosyalarının içine veri saklamaya yarar.

<strong>3-StegoVideo:</strong>Bu aracında adından anlaşılacağı üzere video  üzerine veri saklayabilirsiniz.

İnternette bunlar gibi bir çok program bulunmaktadır.Bunlar sadece bir kaçı.

<strong>Basit Bir Örnek:</strong>

<a href="http://www.gurelahmet.com/wp-content/uploads/2014/09/meteor-imagehide.png"><img class="size-medium wp-image-166 aligncenter" src="http://www.gurelahmet.com/wp-content/uploads/2014/09/meteor-imagehide-225x300.png" alt="meteor-imagehide" width="225" height="300" /></a>

&nbsp;

Bu resme ImageHide programı ile veri gizlenmiştir.Programı indirip resmi açtığınızda Read Data ya tıkladığınızda veriyi göreceksiniz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2014/09/meteor.jpg"><img class="size-medium wp-image-167 aligncenter" src="http://www.gurelahmet.com/wp-content/uploads/2014/09/meteor-300x240.jpg" alt="meteor" width="300" height="240" /></a>

&nbsp;

Programı kullandığınızda resimde ki metni görmeniz gerekiyor.Bu arada köpeğim meteor lada tanışmış oldunuz :)

Yazım burada bitiriyorum başka bir yazıda görüşmek üzere hatalarım varsa affola yorum,öneri ve sorularınız için yorum kısmını yada sol taraftaki sosyal ağlardan bana ulaşabilirsiniz.

<strong>Faydalandığım Kaynaklar:</strong>

1-http://tr.wikipedia.org/wiki/Kriptografi

2-http://tr.wikipedia.org/wiki/Kriptoloji

3-http://tr.wikipedia.org/wiki/Sezar_%C5%9Fifrelemesi

4-http://tr.wikipedia.org/wiki/Stenografi

<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-65335586-1', 'auto');
  ga('send', 'pageview');

</script>
