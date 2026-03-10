# linux-Syslog-bilgilerinin-bagli-liste-ile-gosterilmesi

Linux Syslog Yönetimi ve Bağlı Liste Uygulaması
    Bu proje, Linux işletim sistemindeki sistem günlüklerinin (syslog) veri yapıları kullanılarak nasıl işlenebileceğini gösteren bir C uygulamasıdır. Yazılım mühendisliği prensipleri çerçevesinde, dinamik veri yönetimi için bağlı liste (linked list) yapısı tercih edilmiştir.

Teknik Detaylar
    Kullanılan Dil: C

Veri Yapısı: Tek Yönlü Bağlı Liste (Singly Linked List)

Test Ortamı: Kali Linux

Veri Kaynağı: /var/log/syslog

Çalışma Mantığı
    Program, işletim sisteminin /var/log/syslog dosyasını salt okunur modda açar. Dosyadaki her bir satır, bağlı listenin bir düğümünü (node) temsil eder. Veriler çekilirken şu adımlar izlenir:

Her log satırı için malloc fonksiyonu ile bellekte dinamik bir alan ayrılır.

Ayrılan bu düğüme log içeriği kopyalanır.

Düğüm, listenin sonuna eklenerek kronolojik sıra korunur.

Neden Bağlı Liste Tercih Edildi?
    Sistem günlükleri belirsiz sayıda ve sürekli artan verilerdir. Sabit boyutlu diziler (array) kullanmak, bellek israfına veya veri taşmalarına yol açabilir. Bağlı liste yapısı sayesinde:

  Bellek sadece ihtiyaç duyulduğu kadar kullanılır.

  Veri ekleme işlemleri dinamik olarak gerçekleştirilir.

  Çalışma zamanında (runtime) esneklik sağlanır.

Kurulum ve Çalıştırma
    Sistemde GCC derleyicisinin kurulu olması gerekmektedir. Log dosyalarına erişim için yönetici (root) yetkisi gerekebilir.

Derleme komutu:

Bash
gcc syslog_odev.c -o syslog_app
Çalıştırma komutu:

Bash
sudo ./syslog_app
Proje Yapısı
syslog_odev.c: Bağlı liste yapısını ve dosya okuma işlemlerini içeren kaynak kod.

README.md: Proje dökümantasyonu.
