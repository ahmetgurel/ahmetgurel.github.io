---
layout: post
title: Windows 7 ve 8 Sistemlerde Şifre Bypass
date: 2015-10-25 13:46
author: ahmetgurel
comments: true
categories: [Genel Güvenlik, Siber Güvenlik, windows, windows 7 kullanıcı şifresi, windows hacking, windows password bypass, windows şifre kırma]
---
Windows 7 ve ya 8 kullanıyorsanız sistem  açılışta size parola sorduğu kısımda sol altta erişebilirlik var ve oradan büyüteç,ekran klavyesi gibi araçları çalıştırabiliyoruz.Bu böyle baktığımızda gereksiz gibi görünsede sisteme parola girmeden önce C nin altında Windows klasörünün içinde System32 klasöründen bir .exe çalıştırıyor.Ve biz ekran klavyesi  yerine konsol exe sini çağırısak durum biraz farklı olabilir.Oradan istediğimiz bir komut ile sisteme yeni bir kullanıcı ve şifre atayabiliriz bunlar size kalmış.

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/10/1.png"><img class="alignnone size-large wp-image-535" src="http://www.gurelahmet.com/wp-content/uploads/2015/10/1-1024x495.png" alt="1" width="976" height="472" /></a>
<div class="separator">Yukarıda ki resimde şifreli bir windows 7 işletim sisteminde ekran klavyesi açık.Buradan sonra biz bu ekran klavyesi yerine cmd.exe yani konsol u açacağız.Bunun için yapmamız gerekenler şöyle:</div>
<div class="separator"></div>
<ul>
	<li>Bir tane live linux cd yada flash hazırlamak</li>
	<li>Linux işletim sistemini BIOS dan ayarları yapıp açmak</li>
	<li>Linux açıldıktan sonra tüm disk bölümlerini görecektir windows un kurulu olduğu disk ve varsa diğer bölümleri</li>
	<li>Windows un kurulu olduğu disk bölümüne girerek windows klasörünün altındaki System32 klasörüne gireceğiz.</li>
	<li>Burada ekran klavyesinin olan osk.exe klasörünün adını değiştirmeliyiz ve cmd.exe yi linux masaüstüne kopyalayıp adını osk.exe yaptıktan sonra yeniden System32 klasörünün içine kopyalamalıyız.</li>
	<li>Burada ekran klavyesinin yerine konsol yani cmd.exe çalıştırmış bulunmaktayız.</li>
	<li>Konsoldan net user  kullanıcı_adi  yeni_şifre şeklinde bir komut girdiğimizde o kullanıcı adının şifresini kırıp kendiniz belirlemiş bulunmaktasınız.</li>
</ul>
<a href="http://www.gurelahmet.com/wp-content/uploads/2015/10/2.jpg"><img class="alignnone size-full wp-image-536" src="http://www.gurelahmet.com/wp-content/uploads/2015/10/2.jpg" alt="2" width="960" height="720" /></a>

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/10/3.jpg"><img class="alignnone size-full wp-image-537" src="http://www.gurelahmet.com/wp-content/uploads/2015/10/3.jpg" alt="3" width="960" height="720" /></a>

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/10/4.png"><img class="alignnone size-full wp-image-538" src="http://www.gurelahmet.com/wp-content/uploads/2015/10/4.png" alt="4" width="961" height="338" /></a>

Resimde linux işletim sistemi ile System32 klasöründeki değiştireceğimiz .exe ler görünüyor.Bu işlemleri adım adım yaptıktan sonra sistemi yeniden başlatıp windows u açmanız ve parola sorduğu kısımda ekran klavyesini çalıştıra tıklamanız gerekmektedir.Bu işlem sonucunda  karşınıza ekran klavyesi yerine konsol  gelmesi gerekmektedir.

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/10/5.jpg"><img class="alignnone size-large wp-image-539" src="http://www.gurelahmet.com/wp-content/uploads/2015/10/5-1024x768.jpg" alt="5" width="976" height="732" /></a>

Bu ekran karşımıza geldiğinde net user  kullanıcı_adi  yeni_şifre şeklinde komut girerek unuttuğunuz yada bilmediğiniz bir şifreyi yeni belirlediğiniz şifre ile değiştirmiş olacaksınız.
