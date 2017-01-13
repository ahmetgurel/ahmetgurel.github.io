---
layout: post
title: Linux'ta Scalpel ile Silinmiş Dosya Kurtarma
date: 2015-07-05 11:46
author: ahmetgurel
comments: true
categories: [adli bilişim, Adli Bilişim, data recovery, forensics, Linux, linux, linux recovery, recovery, scalpel, scalpel recovery, Siber Güvenlik, silinen dosyalari kurtarma]
---
Scalpel sisteminizden,harici disklerinizden her hangi bir nedenle silinen dosyalarınızı kurtarmanızı sağlayabilen küçük,hızlı ve kullanışlı bir araçtır.Bu yazımda kurulumu ve nasıl kullanıldığını anlatmaya çalışacağım.

Öncelikle <strong>sudo apt-get install scalpel</strong> komutu ile sistemimize kuruyoruz.Paket depoları dağıtımtan dağıtıma farklılık gösterir  debian tabanlı bir dağıtım kullanmıyorsanız paket yöneticisi farklı olacaktır.

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/07/1.png"><img class="alignnone size-full wp-image-358" src="http://www.gurelahmet.com/wp-content/uploads/2015/07/1.png" alt="scalpel" width="562" height="336" /></a>

&nbsp;

Scalpel i sistemimize kurduktan sonra <strong>sudo vim /etc/scalpel /scalpel.conf </strong> diyerek scalpel in ayar dosyasını açıyoruz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/07/2.png"><img class="alignnone size-full wp-image-359" src="http://www.gurelahmet.com/wp-content/uploads/2015/07/2.png" alt="2" width="561" height="354" /></a>

Ben ayar dosyasını vim ile açtım siz vi,nano,gedit gibi editörler ilede açabilirsiniz.vim kurulu olarak gelmemekte bir live cd ile çalıştığınızda vim i kurmadıysanız bu komut hata verecektir.

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/07/3.png"><img class="alignnone size-full wp-image-360" src="http://www.gurelahmet.com/wp-content/uploads/2015/07/3.png" alt="3" width="566" height="501" /></a>

Şimdi scalpel in ayar dosyasında bolca # (diyez) işareti görmekteyiz.Bunlarda yorum satırı olarak algılanıp çalışmamaktadır.Kurtarmak istediğiniz dosya formatının önündeki #(diyez) işaretlerini kaldırarak arama esnasında o uzantılı dosyayı arayıp kurtarmasını sağlayacağız.Ayar dosyasında gördüğünüz y nin yanındakiler bytes olarak dosyanın büyüklüğüdür.Daha büyük dosyaları aramayacaktır onuda değiştirmek elinizdedir.Son olarak #(diyez) i kaldırıp vim in :wq komutu ile dosyayı kaydetip ve çıktım.Bundan sonrası istediğimiz disk,kurtarılcak alanı gösterip dosylarımızı kurtarmaya kaldı.

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/07/4.png"><img class="alignnone size-large wp-image-361" src="http://www.gurelahmet.com/wp-content/uploads/2015/07/4.png" alt="4" width="558" height="348" /></a>

&nbsp;

<strong>sudo scalpel /dev/sda1 -o /home/ahmet-gurel/Desktop/output </strong>diyerek scalpel i sda1 disk bölümündeki .jpg ve .png uzantılı silinmiş dosyaları arayarak kurtardığı dosyaları  masaüstünde output adlı bir klasöre kaydetmiştir.Diskin büyüklüğüne göre tarama ve kurtarma işlemi uzayacaktır ben deneme amaçlı 100 mb lık küçük bir alanı taradım genel anlamda kullanımı bu şekildedir. -o parametresinden sonraki kısım kurtarılan dosyaların nereye kaydedileciğini göstermektedir istediğiniz gibi bir yol klasör verebilirsiniz.

Silinen dosyalarınızı kurtarmak için bir çok başka araç mevcuttur.

ENCASE
FTK
Restorer
R-Studio
PC Inspector™ File Recovery
Active Partition Recovery
Scalpel    bunlardan bazılarıdır.Encase ve FTK adli bilişim analizlerinde en çok kullanılan programlardır.Scalpel ın kurtaramadığı bulamadığı büyük veri kayıpları için diğer araçları deneyebilirsiniz.

Umarım işinize yarayan bir yazı olmuştur sorularınızı yorum ve mail olarak atabilirsiniz :)


<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-65335586-1', 'auto');
  ga('send', 'pageview');

</script>
