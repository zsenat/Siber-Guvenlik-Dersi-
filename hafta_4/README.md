# Hafta 4 — Basit Hedef Erişim Testi (Ping Script)

Linux/Bash ortamında temel otomasyon becerisi kazanmak ve ağ üzerindeki hedeflerin erişilebilirliğini test etmek amacıyla geliştirilmiş bir Bash betiğidir.

## Amaç

Siber güvenlik testlerinde bir hedefin (IP veya web sitesi) ayakta olup olmadığını hızlıca kontrol etmek kritik bir adımdır. Bu çalışmanın amacı; her seferinde terminale uzun komutlar yazmak yerine, kullanıcıdan girdi (`read`) alıp bunu `ping` ile otomatik işleyen ilk temel Bash betiğini yazmayı öğrenmektir.

## Çalışma Mantığı

1. Çalıştırıldığında kullanıcıya hedef web sitesi veya IP adresini sorar.
2. Klavyeden girilen hedef adresi hafızaya kaydeder.
3. Hedefe ICMP paketleri göndererek (`ping`) sistemin ayakta olup olmadığını ve veri alışverişi yapıp yapamadığını test eder; sonucu ekrana raporlar.

---

*Zeynep Sena Taşolar*
