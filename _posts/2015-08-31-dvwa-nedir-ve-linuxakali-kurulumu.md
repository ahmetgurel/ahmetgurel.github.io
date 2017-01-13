---
layout: post
title: DVWA Nedir ve Linux'a(Kali) Kurulumu
date: 2015-08-31 01:38
author: ahmetgurel
comments: true
categories: [Brute Force, Command Execution, CSRF, dvwa, dvwa nasıl kurulur, dvwa nedir, File Inclusion, kali linux dvwa, kaliye dvwa kurulumu, qwb dvwa, Siber Güvenlik, SQL Injection, Upload, Web Uygulama Güvenliği, web uygulama guvenlıgı, XSS Reflected, XSS Stored]
---
<span style="color: #000000;"><strong>Damn Vulnerable Web Application (DVWA) Nedir?</strong></span>

<span style="color: #000000;">Web uygulama güvenliği  alanında kendini geliştirmek isteyen pentesterlar ve güvenlik ile uğraşan kimseler için PHP ile oluşturulmuş içinde belli web zafiyetlerini barındıran bir eğitim sistemidir.</span>

<strong><span style="color: #000000;">Barındırdığı Zafiyetler:</span></strong>

<span style="color: #000000;">- Brute Force</span>
<span style="color: #000000;">- Command Execution</span>
<span style="color: #000000;">- CSRF</span>
<span style="color: #000000;">- File Inclusion</span>
<span style="color: #000000;">- SQL Injection</span>
<span style="color: #000000;">- Upload</span>
<span style="color: #000000;">- XSS Reflected</span>
<span style="color: #000000;">- XSS Stored</span>

<span style="color: #000000;">DVWA Sisteminde 3 tane zorluk seçeneği vardır.Bunlar low,medium ve high dır.</span>

&nbsp;

<span style="color: #000000;"><strong>Damn Vulnerable Web Application (DVWA) Kali Linux'a Kurulumu</strong></span>

<span style="color: #000000;">Öncelikle <strong>service apache2 start </strong> ve<strong> service mysql start</strong> komutları ile apache ve mysql servislerini başlatıyoruz.</span>

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/08/000.png"><img class="alignnone size-full wp-image-478" src="http://www.gurelahmet.com/wp-content/uploads/2015/08/000.png" alt="000" width="1010" height="641" /></a>

&nbsp;

<span style="color: #000000;">Sonra <strong>cd /var/www  k</strong>omutunu kullanarak  /www dizinine geliyoruz.</span>

<span style="color: #000000;">Ve <strong> git clone https://github.com/RandomStorm/DVWA.git  dvwa</strong> komutunu çalıştırarak DVWA dosyasını dvwa klasörünün içine git ile kopyalıyoruz.</span>

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/08/0001.png"><img class="alignnone size-full wp-image-479" src="http://www.gurelahmet.com/wp-content/uploads/2015/08/0001.png" alt="0001" width="1010" height="635" /></a>

<span style="color: #000000;">Daha sonra <strong>leafpad  dvwa/config/config.inc.php</strong>  konfigurasyon dosyasını açarak  password kısmını silip boş bırakarak kaydedip çıkıyoruz.</span>

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/08/002.png"><img class="alignnone size-full wp-image-480" src="http://www.gurelahmet.com/wp-content/uploads/2015/08/002.png" alt="002" width="1013" height="707" /></a>

&nbsp;

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/08/003.png"><img class="alignnone size-full wp-image-481" src="http://www.gurelahmet.com/wp-content/uploads/2015/08/003.png" alt="003" width="996" height="713" /></a><span style="color: #000000;">Daha sonra internet tarayıcımıza <strong>127.0.0.1/dvwa</strong> yazıp gittiğimizde DVWA ın kurulum ve veri tabanı oluşturma sayfası gelmektedir.</span>

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/08/005.png"><img class="alignnone size-full wp-image-482" src="http://www.gurelahmet.com/wp-content/uploads/2015/08/005.png" alt="005" width="1010" height="687" /></a>

&nbsp;

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/08/0005.png"><img class="alignnone size-full wp-image-483" src="http://www.gurelahmet.com/wp-content/uploads/2015/08/0005.png" alt="0005" width="996" height="717" /></a>

&nbsp;

<span style="color: #000000;">Ve son olarak bu adımları tamamlayıp internet tarayıcımıza <strong>127.0.0.1/dvwa</strong> tıkladığımız login ekranı gelmektedir.</span>

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/08/006.png"><img class="alignnone size-full wp-image-484" src="http://www.gurelahmet.com/wp-content/uploads/2015/08/006.png" alt="006" width="1015" height="713" /></a>

&nbsp;

<span style="color: #000000;">Gelen login ekranına Username kısmına<strong>  admin</strong> Password kısmınada <strong>password </strong>girerek sisteme giriş yapıyoruz.</span>

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/08/abc.png"><img class="alignnone size-full wp-image-485" src="http://www.gurelahmet.com/wp-content/uploads/2015/08/abc.png" alt="abc" width="1001" height="729" /></a><span style="color: #000000;">Son adımdan sonra sistem bu şekilde karşımızda olacak ve istediğimiz leveli ve bölümleri seçerek kendinizi geliştirip deneyebilirsiniz.Bir başka yazıda görüşmek üzere :)</span>

&nbsp;

&nbsp;

&nbsp;
