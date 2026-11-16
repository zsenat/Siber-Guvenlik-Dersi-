# Hafta 3 — MAC Flooding ve CAM Tablosu Taşırma

Yerel ağlardaki anahtarlama (switching) mekanizmasının çalışma mantığı ve güvenlik açıkları incelenmiştir.

## Temel Kavramlar

- **ARP (Address Resolution Protocol):** Yerel ağda bilinen bir IP adresine karşılık gelen MAC adresini bulmayı sağlayan protokol. Cihazlar haberleşmeden önce "Bu IP'nin MAC adresi nedir?" diye ağa sorar.
- **Flooding:** Bir sistemi kapasitesini aşacak hız/büyüklükte veri göndererek kilitlemeyi hedefleyen saldırı türü.

## Uygulama

Kali Linux üzerinde `macof` aracıyla ağa saniyede yüzlerce sahte (random) MAC adresi gönderilerek switch'in CAM (Content Addressable Memory) tablosu kasıtlı olarak doldurulmuştur. `sudo macof -i ...` komutu bu yoğun paket akışını üretir.

## Sonuç ve Kazanımlar

- Tablo taşınca switch belleği dolar ve trafiği yönetemez hale gelir.
- Switch güvenlik önlemi olarak **hub gibi davranmaya** başlar (fail-open) ve gelen tüm paketleri ağdaki herkese (broadcast) gönderir.
- Bu durum saldırganın trafiği dinlemesine (sniffing) ve Man-in-the-Middle saldırılarına zemin hazırlar.
- **Port Security** önlemlerinin neden hayati olduğu uygulamalı olarak kavranmıştır.

---

*Zeynep Sena Taşolar*
