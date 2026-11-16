# Hafta 5 — Python ile UDP Veri Gönderme ve Alma

Python kullanılarak UDP protokolü üzerinden veri gönderme/alma işlemleri ve büyük boyutlu verilerde IP parçalanması incelenmiştir.

- **UDP (User Datagram Protocol):** Cihazlar arasında bağlantı kurmadan çalışan taşıma katmanı protokolü.
- **Socket:** Uygulamaların ağ üzerinden veri alışverişi yapmasını sağlayan yazılım arayüzü. Python'da `socket` kütüphanesiyle kullanılır.
- **IP Adresi ve Port:** IP adresi hedef cihazı, port numarası ise cihazdaki uygulamanın iletişim uç noktasını belirtir.
- **MTU (Maximum Transmission Unit):** Tek bir pakette taşınabilecek maksimum veri miktarı; aşıldığında IP paketleri parçalanabilir veya iletilemeyebilir.

- `socket` kütüphanesiyle bir UDP soketi oluşturulur.
- Hedef IP: `172.16.107.22`, port: `5000`, veri boyutu: `4000` bayt.
- `b"A" * 4000` ile üretilen veri `sendto()` fonksiyonuyla hedefe gönderilir.
- `IP_MTU_DISCOVER` ve `IP_PMTUDISC_DONT` seçenekleriyle Linux'taki IPv4 Path MTU Discovery davranışı ayarlanır.

- UDP soketi `bind()` ile `0.0.0.0` adresinin `8000` portuna bağlanır.
- `recvfrom()` ile gelen veri beklenir.
- Veri ulaştığında gönderen cihazın IP adresi, portu ve verinin boyutu ekrana yazılır; alınan verinin ilk 40 baytı görüntülenir.

---

*Zeynep Sena Taşolar*
