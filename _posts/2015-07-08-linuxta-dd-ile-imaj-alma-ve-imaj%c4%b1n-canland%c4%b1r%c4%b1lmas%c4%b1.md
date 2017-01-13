---
layout: post
title: Linux'ta DD ile İmaj Alma ve İmajın Canlandırılması
date: 2015-07-08 15:09
author: ahmetgurel
comments: true
categories: [adli bilişim, Adli Bilişim, dd, forensics, image, imaj alma, Linux, linux, linux dd, Siber Güvenlik, siber güvenlik]
---
<strong>İmaj Almak Neden Önemli?</strong>

Öncelik ile neden format atılmış bir diskin imajını alıp recovery yapıyoruz da, direkt olarak bu diskimizin üzerinde recovery programlarını kullanmıyoruz ?

Çünkü kullandığımız programlar diskteki verilerin bilgilerinin tutulduğu metadata bilgilerini değiştirir.Bir programla kurtaramayacağımız verileri başka bir programla kurtarmak bazen mümkün olabiliyor.Bunun için orjinal diskin metadata larını değiştirmemek zarar vermemek için imaj alıp imaj üzerinden işlem yaparız.

<strong>İmaj Almak</strong>

Disklerimizin imajlarını fiziksel ve yazılımsal olarak alabiliriz.

<strong>Fiziksel İmaj Alma Cihazları</strong>

Bu cihazlar temel prensip olarak biri imajı alınacak disk diğeride imajın kaydedileceği boş disk olarak iki diski araçlara bağlayarak imaj alır.

<strong>Bu cihazlardan bazıları:</strong>

<strong>DIBS RAID (Rapid Action Imaging Device)</strong>

[caption id="attachment_368" align="alignnone" width="451"]<a href="http://www.gurelahmet.com/wp-content/uploads/2015/07/DIBS-RAID-Rapid-Action-Imaging-Device.jpg"><img class="size-full wp-image-368" src="http://www.gurelahmet.com/wp-content/uploads/2015/07/DIBS-RAID-Rapid-Action-Imaging-Device.jpg" alt="DIBS RAID (Rapid Action Imaging Device)" width="451" height="475" /></a> DIBS RAID (Rapid Action Imaging Device)[/caption]

<strong>Image MASSter Solo III</strong>

[caption id="attachment_369" align="alignnone" width="600"]<a href="http://www.gurelahmet.com/wp-content/uploads/2015/07/Image-MASSter-Solo-III.jpg"><img class="size-full wp-image-369" src="http://www.gurelahmet.com/wp-content/uploads/2015/07/Image-MASSter-Solo-III.jpg" alt="Image MASSter Solo III" width="600" height="400" /></a> Image MASSter Solo III[/caption]

<strong>Logicube</strong>

[caption id="attachment_370" align="alignnone" width="220"]<a href="http://www.gurelahmet.com/wp-content/uploads/2015/07/Logicube.jpg"><img class="size-full wp-image-370" src="http://www.gurelahmet.com/wp-content/uploads/2015/07/Logicube.jpg" alt="Logicube" width="220" height="353" /></a> Logicube[/caption]

<strong>Tableau</strong>

[caption id="attachment_371" align="alignnone" width="600"]<a href="http://www.gurelahmet.com/wp-content/uploads/2015/07/Tableau.jpg"><img class="size-full wp-image-371" src="http://www.gurelahmet.com/wp-content/uploads/2015/07/Tableau.jpg" alt="Tableau" width="600" height="381" /></a> Tableau[/caption]

<strong>Yazılımsal İmaj Alma Programları</strong>

&nbsp;

Safeback v3
Forensic Replicatorv 3.1
PDA Seizure v 3.0.1.35
Pdd (Palm dd, Windows, Free)
Forensic Toolkit (FTK) v 1.50
WinHex v 12.0NTI
Image (DOS)
SMART (Linux Redhat)
ByteBack (DOS) v 3
Anadisk v 2.10
ILook v 8.0.8AIR-(Linux-Free)
Automated Image &amp; Restore
Forensic Explorer
Sans

Imaj almaya yarayan bazı araçlar bunlardır.Bunların dışında ben bu yazımda linuxta DD ile imaj almayı anlatacağım.Bu yazıda  linux ta bir usb belleğin imajını alıp o imajı ayağa kaldıracağız.

<strong>Linux'ta DD ile Imaj Alma</strong>

DD sabit bir diskin,usb belleğin,cd nin yada dvd nin imajını alabilir.Aldığınız bu imajı sisteme mount ederekte usb bilgisayarımıza takılıymış gibi açabilir yada verilerimizi kurtarabiliriz.

DD alt seviye kopyalama yapar yanı diskimizinboş alanlarda dahil  tamamının kopyalayıp imajını alır.<strong>Yani disk boyutu ile imaj boyutu aynı olmalıdır.</strong>

DD komutu if ve of olmak üzere iki temel parametre alır. Diğer parametreler ise isteğe bağlıdır.<strong>If</strong> bilgisi burada kaynak aygıt/partition u, <strong>of</strong> ise hedefi göstermektedir.

Bunun dışında <strong>bs  </strong>kaçar byte kopyalanacağını belirtir.<strong>conv=noerror </strong>ise hata alsan bile kopyalamaya devam et demeye yarar.

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/07/11.png"><img class="alignnone size-full wp-image-372" src="http://www.gurelahmet.com/wp-content/uploads/2015/07/11.png" alt="1" width="985" height="609" /></a>

Öncelikle burada sudo fdisk -l komutu ile flash belleğimizin yolunu bulduk bunun dışında diske nerden yazılmaya başlandığı (Start 2048) bitişi (End=798176) Diskin formatı gibi bilgileri edindik.Burada sdb flash bellleğimizi sdb1 ise onun bir partition göstermektedir.Bu yüzden imaj alırken diskimizin tamamını yanı sdb nin imajını almalıyız.

Daha sonra ise <strong>sudo dd if=/dev/sdb  of=/home/ahmetDesktop/disk.img bs=10M conv=noerror</strong> komutu ile  diskimizin imajını masaüstüne aldım burada durum dd çalışırken bir çıktı vermez burada çalışmıyor diye kapatmayın iptal etmeyin işlem bittiğinde çıktı verecektir.Komutu çalıştırdığımızda bir değişiklik olmayacak aşağıdaki resimde gördüğünğünüz gibi  sadece masaütüne ismini verdiğimiz disk.img gelecektir.

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/07/21.png"><img class="alignnone size-large wp-image-373" src="http://www.gurelahmet.com/wp-content/uploads/2015/07/21-1024x524.png" alt="2" width="976" height="499" /></a>

&nbsp;

Işlem bittiğinde ise aşağıdaki gibi bir çıktı alacağız.Bu başarı ile imajımızın alındığını göstermektedir.

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/07/31.png"><img class="alignnone size-large wp-image-374" src="http://www.gurelahmet.com/wp-content/uploads/2015/07/31-1024x582.png" alt="3" width="976" height="555" /></a>

Artık flash belleğimizin imajını aldık şimdi bu imajı açmamız içini görmek istiyorsak imaj açma toolları kullanabiliriz.Ben linuxta aldığım imajı mount ederek açacağım.

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/07/41.png"><img class="alignnone size-large wp-image-375" src="http://www.gurelahmet.com/wp-content/uploads/2015/07/41-1024x884.png" alt="4" width="976" height="843" /></a>

Yukarıda gördüğünüz gibi önce Desktop(Masaüstü) a gelerek  mkdir ile imajac diye boş bir klasör oluşturdum.<strong>sudo mount -o offset=1048576 /home/ahmet/Desktop/disk.img  /home/ahmet/Desktop/imajac/ </strong>komutu ile de disk.img adlı imaj dosyamı imajac adlı klasöre mount ettim.Artık imajac klasörüne tıkladığımızda imajımıza ulaşıyoruz.Burada mount komutu ile ilgili <strong>offset </strong>önemli offset değerini kendimiz hesaplıyoruz ilk resimdeki <strong>sudo fdisk -l </strong>komutunun çıktısındaki diskin yazılmaya başlandığı değeri start değeri  2048 idi.Sector size 512 idi.Bu iki sayıyı çarptığımızda 2048x512=1048576  bizim offset değerimiz oluyor.Flash belleğimizin imajını aldık ve imajını açtık gördüğünüz gibi flash bellek boş çıktı.Daha önce silinen veriler var ise bunuda başka araçlar üzerinden imajımızdan ulaşabilriz.Böyle bir şeye gerek duyarsanız <a href="http://www.gurelahmet.com/linuxta-scalpel-ile-silinmi%C5%9F-dosya-kurtarma/">Linux'ta Scalpel ile Silinmiş Dosya Kurtarma</a> adlı yazımı inceleyebilirsimiz.Umarım faydalı bir yazı olmuştur.Soru ve önerilerinizi yorum kısmından veya mail ile ulaşabilrisiniz.



<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-65335586-1', 'auto');
  ga('send', 'pageview');

</script>
