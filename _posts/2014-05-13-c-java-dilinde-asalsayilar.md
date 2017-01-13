---
layout: post
title: C & Java Dilinde Asalsayılar
date: 2014-05-13 14:08
author: ahmetgurel
comments: true
categories: [asalsayi, asalsayi algoritması, C, c de asalsayi, Java, java da asalsayi, Java SE]
---
<div class="separator" style="clear: both; text-align: center;"><a href="http://gurelahmet.com/wp-content/uploads/2014/05/1.jpg"><img class="alignnone size-medium wp-image-31" src="http://gurelahmet.com/wp-content/uploads/2014/05/1-237x300.jpg" alt="1" width="237" height="300" /></a></div>
Evet uzun bir süredir bloga yazmadığımın farkına varmıs bulunmaktayım bu sırada ikinci dönem basladı ve ilk vizelerim bitti hatta  C dili yerıne JAVA öğrenmeye başladık.Tabi ki ufak farklılıklar olsada önemli olan her zaman algoritma ve programlama mantığı yanı hemen hemen hepsı bır bırıne benzer fazla uzatmadan ilköğretim 4 .sınıftan beri gördüğümüz matematiğin vazgeçilmezi olan ASAL SAYILAR  a değinelim bugün :) Hem basit bir konu hemde programlama mantığı  C &amp; JAVA arasındaki  farklılıkları görelim C dilinide unutmayalım :)
<pre style="background-color: #eeeeee; border: 1px dashed #999999; color: black; font-family: Andale Mono, Lucida Console, Monaco, fixed, monospace; font-size: 12px; line-height: 14px; overflow: auto; padding: 5px; width: 100%;"><code>1 ile 10000 arasındaki asalsayıları ekrana yazdıran ve toplam kaç tane asal sayının olduğunu gösteren programı C &amp; JAVA dilinde kodlarını yazalım.
</code></pre>
Asal sayılar dendiğinde sadece 1 e ve kendisine bölünen  sayılar olarak tanımlanmakta  bunu programlama diline aktarırken nasıl bulucaz nasıl bır mantığı olacak algoritmadaki sayac programlama dilindeki döngü baya bir işimize yarayacak diye düşünüyorum :) Sonuçta 1 ve kendısıne bölünüyor 2 tane böleni var ise  bu iki böleni sayıp bir koşula baglarsak 2 böleni var ise asal sayi  bölen sayısı 2 den farklı ise asal değil  gibi bir mantık izleyeceğiz tabi ki asal sayıyı bulduk fakat 1 ile 10000 arasında kac tane asal sayının oldugunu bulmamız için bunları bir sayaç ile saymamız gerekiyor asalsayi adında bir sayac tanımlayıp bölen=2 koşulunda onuda bir artırarak bu işlemi yapmış olacağız  bu sefer kodları 2 dilde yazacağım C ve JAVA da iki dilin arasındaki farklılarıda görelim ama programlama mantığının aynı olduğunuda gösterelim istiyorum.
<pre style="background-color: #eeeeee; border: 1px dashed #999999; color: black; font-family: Andale Mono, Lucida Console, Monaco, fixed, monospace; font-size: 12px; line-height: 14px; overflow: auto; padding: 5px; width: 100%;"><code>C DİLİNDE</code></pre>
<pre style="background-color: #eeeeee; border: 1px dashed #999999; color: black; font-family: Andale Mono, Lucida Console, Monaco, fixed, monospace; font-size: 12px; line-height: 14px; overflow: auto; padding: 5px; width: 100%;"><code>/* Ahmet GÜREL
Süleyman Demirel University Yazılım Kulübü | Yönetim Kurulu Üyesi
Süleyman Demirel University| Computer Engineering
www.gurelahmet.com | www.twitter.com/ahmtgrll
ahmetgurel.yazilim@gmail.com */

#include&lt;stdio.h&gt;
#include&lt;conio.h&gt;
main(){

int bolen=0,asalsayi=0,i,j;

for( i=1;i&lt;=10000;i++){
bolen=0;
for(j=1;j&lt;=i;j++){
if(i%j==0)
bolen+=1;

}
if(bolen==2){
printf("Asalsayi: %d \n", i);
asalsayi+=1;
}
}

printf("1 ile 10000 arasinda %d asal sayi vardir \n", asalsayi);

getch();

}
</code></pre>
<pre style="background-color: #eeeeee; border: 1px dashed #999999; color: black; font-family: Andale Mono, Lucida Console, Monaco, fixed, monospace; font-size: 12px; line-height: 14px; overflow: auto; padding: 5px; width: 100%;"><code>JAVA DİLİNDE</code></pre>
<pre style="background-color: #eeeeee; border: 1px dashed #999999; color: black; font-family: Andale Mono, Lucida Console, Monaco, fixed, monospace; font-size: 12px; line-height: 14px; overflow: auto; padding: 5px; width: 100%;"><code>/* Ahmet GÜREL
Süleyman Demirel University Yazılım Kulübü | Yönetim Kurulu Üyesi
Süleyman Demirel University| Computer Engineering
www.gurelahmet.com | www.twitter.com/ahmtgrll
ahmetgurel.yazilim@gmail.com */

public class asalsayi {

public static void main(String[] args) {

int bolen=0,asalsayi=0,i,j;

for( i=1;i&lt;=10000;i++){
bolen=0;
for(j=1;j&lt;=i;j++){
if(i%j==0)
bolen+=1;

}
if(bolen==2)
{
System.out.println("Asalsayi:" +i);
asalsayi+=1;
}
}

System.out.println("1 ile 10000 arasında " +asalsayi+ " asal sayi vardır");

}


</code></pre>
<script>// <![CDATA[
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-51160619-1', 'gurelahmet.com');
  ga('send', 'pageview');

// ]]></script>


<script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-65335586-1', 'auto');
  ga('send', 'pageview');

</script>
