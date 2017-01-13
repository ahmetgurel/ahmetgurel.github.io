---
layout: post
title: Ubuntu'ya Burp Suite Kurulumu
date: 2015-09-12 19:03
author: ahmetgurel
comments: true
categories: [burp suite, burpsuite kurulum, linux ubuntu, linux ubuntu burpsuite kurulumu, Siber Güvenlik, Sızma Testi Araçları (Pentest Tools), ubuntu]
---
Burpsuite sızma testlerinde ve bir siteyi incelemek istediğimizde en çok kullanılan web proxy uygulamalarından birisidir.Free ve Professional olarak iki sürümü mevcuttur.Kali de Free versiyonu kurulu olarak gelmektedir.Bu yazıda bende günlük hayatta ubuntu kullandığım için Ubuntuda Burpsuite kurulumunu göstereceğim.

İlk olarak Burpsuite çalışabilmesi için OpenJDK nın kurulu olması gerekmekte.

<span class="geshifilter"><code class="java geshifilter-java">sudo apt-get update </code></span>

<span class="geshifilter"><code class="java geshifilter-java">sudo apt-get install openjdk-7-jdk openjdk-7-jre  </code></span>

komutları ile OpenJDK kurulumunu yapıyoruz.

Daha sonra <a href="https://portswigger.net/burp/download.html">https://portswigger.net/burp/download.html</a>  adresine giderek Burpsuite Free Edition ı indiriyoruz.(Tabi lisanslı alacaksanız Professional ı da seçebilirsiniz malum öğrencilik :) )

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/09/21.png"><img class="alignnone size-large wp-image-527" src="http://www.gurelahmet.com/wp-content/uploads/2015/09/21-1024x579.png" alt="2" width="976" height="552" /></a>

&nbsp;

Eğer yolunu değiştirmediyseniz <strong>burpsuite_free_v1.6.25.jar</strong> adlı jar dosyası <strong>Downloads</strong>  klasörüne inmiştir.Son olarak

<span class="geshifilter"><code class="java geshifilter-java"> cd Downloads </code></span>

<span class="geshifilter"><code class="java geshifilter-java">sudo java -jar -Xmx2g burpsuite_free_v1.6.25.jar </code></span>

komutları ile Burpsuite i açmış olacaksınız.

<a href="http://www.gurelahmet.com/wp-content/uploads/2015/09/22.png"><img class="alignnone size-large wp-image-530" src="http://www.gurelahmet.com/wp-content/uploads/2015/09/22-1024x554.png" alt="2" width="976" height="528" /></a>
