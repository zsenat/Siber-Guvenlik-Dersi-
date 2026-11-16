# Hafta 8 — ICMP Spoofing ve Ortadaki Adam (MITM) Saldırısı

İnternette cihazlar birbiriyle konuşurken karşıdakinin gerçekten o kişi olduğunu çoğu zaman doğrulamaz. "Ping" dediğimiz ICMP protokolü de böyledir: bir cihaz "orada mısın?" diye sorar, diğeri "buradayım" diye cevap verir — ama bu cevabın gerçekten o cihazdan geldiğini kontrol eden bir mekanizma yoktur.

Bu lab'da iki makine (`.31` ve `.32`) normal şekilde ping'leşirken, araya giren bir saldırgan (`.25`) kendini `.31`'miş gibi göstererek sahte cevaplar üretip ağa bırakır. İki tarafın ortasına yerleşip trafiğe müdahale ettiği için buna **ortadaki adam (man-in-the-middle)** saldırısı denir.

## Saldırı nasıl yakalanıyor?

Sahte paket gerçeğine çok benzer ama küçük bir iz bırakır. Paketler ağda dolaşırken üzerinde bir "ömür sayacı" (TTL) taşır ve her duraktan geçtiğinde bu sayı azalır. Gerçek cevap doğrudan geldiği için sayacı farklı, saldırganın uydurduğu cevap fazladan bir durak geçtiği için farklıdır.

`mitm.pcap`'te aynı mesajın iki kere, üstelik farklı TTL ile göründüğü fark edilir — işte bu tutarsızlık, araya birinin girdiğinin kanıtıdır.

## Dosyalar

- `icmp_spoof.py` — sahte paket üreten Scapy kodu
- `sender.pcap`, `dest.pcap` — normal trafik yakalamaları
- `mitm.pcap` — saldırı anı yakalaması

*Zeynep Sena Taşolar*
