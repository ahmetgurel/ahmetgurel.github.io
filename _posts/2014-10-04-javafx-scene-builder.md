---
layout: post
title: JavaFX & JavaFX Scene Builder
date: 2014-10-04 01:50
author: ahmetgurel
comments: true
categories: [görsel programlama, gui, Java, java, java görsel programlama, java gui, JavaFX, JavaFX, Programlama Dilleri]
---
JavaFX ilk olarak 2007 yılında JavaOne konferansında duyuruldu. Swing in yerine yeni bir teknoloji olarak gelmiş swing in eksik yönleri güçlendirilmiştir..JavaFX,görsel olarak daha esnek ve gaha güçlü.3D, Canvas, Audio, Video, Web Service'leri cagirabilme CSS ile şekillendirebilme  özellikleriyle Javanın ileride masaüstü ve web servislerinde yerini alacağa benziyor.Ileri okuma için <a title="tıklayınız" href="http://docs.oracle.com/javafx/2/overview/jfxpub-overview.htm" target="_blank">tıklayınız.</a>Bu yazımda JavaFX ile görsel programlama yaparken işinizi kolaylaştıracak JavaFX Scene Builder ı anlatacağım.Başlamadan önce Netbeans ve JavaFX Scene Builder kurulumu yapmanız gerekmektedir.

JDK 8 ve NetBeans 8.0.1  <a href="http://www.oracle.com/technetwork/java/javase/downloads/jdk-netbeans-jsp-142931.html" target="_blank">Indirmek için tıklayınız.</a>

JavaFX Scene Builder 2.0 <a href="http://www.oracle.com/technetwork/java/javase/downloads/sb2download-2177776.html" target="_blank">Indirmek için tıklayınız.</a>

Ilk olarak JavaFX Scene Builder ı açarak  sürükle bırak ile istediğimiz arayüzü oluşturacağız.

<a href="http://www.gurelahmet.com/wp-content/uploads/2014/10/1.png"><img class="alignnone wp-image-184 size-large" src="http://www.gurelahmet.com/wp-content/uploads/2014/10/1-1024x575.png" alt="javafx scene builder" width="976" height="548" /></a>

Oluşturduktan sonra dosyamızı .FXML uzantısı ile kaydediyoruz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2014/10/3.png"><img class="alignnone size-large wp-image-186" src="http://www.gurelahmet.com/wp-content/uploads/2014/10/3-1024x575.png" alt="javafx scene builder" width="976" height="548" /></a>

Burdaki işimiz bitti şimdi NetBeans a geçip bu görsel arayüzü kodumuza eklememiz lazım.NetBeans açılırken masaüstünü kaydettiğimiz javafx.FXML dosyamızı göreceğiz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2014/10/4.png"><img class="alignnone size-large wp-image-187" src="http://www.gurelahmet.com/wp-content/uploads/2014/10/4-1024x575.png" alt="javafx" width="976" height="548" /></a>

<a href="http://www.gurelahmet.com/wp-content/uploads/2014/10/5.png"><img class="alignnone size-large wp-image-188" src="http://www.gurelahmet.com/wp-content/uploads/2014/10/5-1024x575.png" alt="javafx" width="976" height="548" /></a>

&nbsp;

NetBeans açıldığında new project dıyerek JavaFX ordanda görseldeki gibi JavaFX FXML Application açacağız.

<a href="http://www.gurelahmet.com/wp-content/uploads/2014/10/6.png"><img class="alignnone size-large wp-image-189" src="http://www.gurelahmet.com/wp-content/uploads/2014/10/6-1024x575.png" alt="javafx" width="976" height="548" /></a>

&nbsp;

Default ayarlar bu şekilde hiç bir değişiklik yapmadan finish diyoruz ve devam ediyoruz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2014/10/7.png"><img class="alignnone size-large wp-image-190" src="http://www.gurelahmet.com/wp-content/uploads/2014/10/7-1024x575.png" alt="javafx" width="976" height="548" /></a>

&nbsp;

Projemiz bu şekilde önümüze gelecektir.Ana dosyamızın yanında FXMLDocument.fxml dosyasını görüyoruz.Bu dosyaya JavaFX Scene Builder ile oluşturup kaydettiğimiz arayüz dosyasının içindeki kodları yapıştıracağız.

<a href="http://www.gurelahmet.com/wp-content/uploads/2014/10/8.png"><img class="alignnone size-large wp-image-191" src="http://www.gurelahmet.com/wp-content/uploads/2014/10/8-1024x575.png" alt="javafx" width="976" height="548" /></a><a href="http://www.gurelahmet.com/wp-content/uploads/2014/10/9.png"><img class="alignnone size-large wp-image-192" src="http://www.gurelahmet.com/wp-content/uploads/2014/10/9-1024x575.png" alt="javafx" width="976" height="548" /></a>

Projemize kodu yapıştırdıktan sonra çalıştırmamız yeterli oluşturduğumuz arayüz NetBeans ortamında çalışacaktır.Surekli kopyala yapıştır yapmak istemiyorsanız Scene Builder i IDE niz ile birleştirebilirsiniz fxml dosyanıza tıkladığınız Scene Builder açılır ve oradan tasarımı yapıp save dedıkten sonra kodlarınız otomatik olarak yüklenir.IDE nize Scene Builder eklemek için Tools seçeneğinden Options a tıklayarak Java yı seçip daha sonrada JavaFX e tıklayarak Scene Builder ın yolunu vermeniz gerekmektedir.Aşağıdaki resimde gösterildiği gibi yapabilirsiniz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2014/10/Screenshot-from-2014-10-30-141655.png"><img class="alignnone size-large wp-image-250" src="http://www.gurelahmet.com/wp-content/uploads/2014/10/Screenshot-from-2014-10-30-141655-1024x718.png" alt="javafx-scnebuilder" width="976" height="684" /></a>

<a href="http://www.gurelahmet.com/wp-content/uploads/2014/10/10.png"><img class="alignnone size-large wp-image-193" src="http://www.gurelahmet.com/wp-content/uploads/2014/10/10-1024x575.png" alt="javafx" width="976" height="548" /></a>

Yazımın sonuna gelmiş bulunmaktayım.Saat her zaman ki gibi 12 yi geçmiş ve bu sabah Kurban Bayramı :) Şimdiden Herkese iyi Bayramlar.Herhangi bir sorunda yorum kısmından veya  sol tarafta ki sosyal ağlar kısmından ulaşabilirsiniz.

&nbsp;

&nbsp;


<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-65335586-1', 'auto');
  ga('send', 'pageview');

</script>
