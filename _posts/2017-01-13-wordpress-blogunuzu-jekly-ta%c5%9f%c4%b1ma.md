---
layout: post
title: Wordpress Blogu  Jekly Taşıma
date: 2017-01-13 14:22
author: ahmetgurel
comments: true
categories: [jekly, Programlama Dilleri, WordPress, Wordpress Blogunuzu Jekly Taşıma, wordpress yazılarını markdown a çevirmek, wordpress yazılarınız md uzantılı yapmak]
---
Merhabalar,

Wordpressi benim gibi sadece blog tutmak için kullanan arkadaşlar sürekli wordpress güncellemeleri eklentileri vs bir çok uğraşı bulunmakta fakat bunun yerine son zamanlarda<strong> githubkullaniciadi.github.io</strong> ları görmekteyiz.Github username iniz olmak koşuluyla <strong>githubkullaniciadi.github.io </strong>adlı bir repo oluşturup buna Jekly kurup yayınlayabilirsiniz.Bu yazıda Jekly kurulumunu anlatmayacağım googleda çok fazla kişi yazmış. <a href="http://aristona.github.io/jekyll-ve-github-pages-kullanarak-kendi-blogumuzu-olusturmak">http://aristona.github.io/jekyll-ve-github-pages-kullanarak-kendi-blogumuzu-olusturmak</a> bunlardan birisi bu şekilde adım adım kurabilirsiniz.Eğer buda zor ve uzun bir uğraş gibi geldiyse bununda basit bir yolunu söyleyeyim Jekly kurmuş ve kullanmakta olan birinin reposunu indirerek (Örn: https://github.com/ahmetgurel/ahmetgurel.github.io )  onu kendinizi göre düzenledikten sonra kullanıcıadinizla açtığınız <strong>githubkullaniciadi.github.io </strong>reposuna yüklediğiniz direk çalışacaktır.Kurulumu bu şekilde hallettikden sonra gelelim wordpress yazılarınızı Jekly ye geçirmeye.

Wordpressi uzun yıllar kullanınca biriken bu yazıları ona geçirmek biraz insanı üşendirebilir.Jekly markdown .md uzantısı kullanmakta <strong>_post</strong> klasöründe bulunmaktadır.

<a href="http://www.gurelahmet.com/wp-content/uploads/2017/01/1.jpg"><img class="alignnone wp-image-680 size-large" src="http://www.gurelahmet.com/wp-content/uploads/2017/01/1-1024x525.jpg" width="976" height="500" /></a>

Şimdi wordpress teki yazılarınızı ilk olarak <strong>Araçlar -&gt; Dışa Aktar -&gt; Yazılar</strong> diyerek xml formatında kaydediyoruz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2017/01/2.jpg"><img class="alignnone size-large wp-image-681" src="http://www.gurelahmet.com/wp-content/uploads/2017/01/2-1024x421.jpg" alt="" width="976" height="401" /></a>

xml olarak inen dosyamızı artık markdown .md ye çevirmek içinde <strong>wpXml2Jekyll </strong>aracımızı kullanıyoruz. <a href="https://github.com/theaob/wpXml2Jekyll">https://github.com/theaob/wpXml2Jekyll</a> adresinden indirerek xml dosyamızı seçip save post dediğimizde wordpress deki tüm yazılarınız markdown haline çevirmiş olacaksınız.

<a href="http://www.gurelahmet.com/wp-content/uploads/2017/01/3.jpg"><img class="alignnone size-full wp-image-682" src="http://www.gurelahmet.com/wp-content/uploads/2017/01/3.jpg" alt="" width="934" height="470" /></a>

Artık bu işlem sonunda oluşan markdown .md uzantılı yazılarımızı repomuzdaki <a id="e2a2ff2d1ad978ada529597257972458-2e1be514044c14d4843cc877df018d4929325a34" class="js-navigation-open" title="_posts" href="https://github.com/ahmetgurel/ahmetgurel.github.io/tree/master/_posts">_posts</a>  dizinine atarak işlemimizi tamamlamış oluyoruz. Tüm yazılarım artık <a href="https://ahmetgurel.github.io/"> ahmetgurel.github.io</a> adresine aktarmış bulunmaktayız. Not: Yazılarınızda ki resim dosyalarınızı domain üzerine linklendiriyor bunları kaydedip reponuzun içine atarak yollarını değiştirmeniz gerekebilir.

<a href="http://www.gurelahmet.com/wp-content/uploads/2017/01/4.jpg"><img class="alignnone size-large wp-image-683" src="http://www.gurelahmet.com/wp-content/uploads/2017/01/4-1024x515.jpg" alt="" width="976" height="491" /></a>

&nbsp;
