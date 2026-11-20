# Client-Server Haberleşmesi ve Wireshark ile Paket Analizi

Bu çalışmada Python'un `socket` kütüphanesi kullanılarak bir Client ile Server arasında TCP bağlantısı kuruldu. İki taraf JSON formatında mesajlaştı ve aradaki trafik Wireshark ile yakalanıp analiz edildi.

## Proje Hakkında

- Client ve Server aynı bilgisayar üzerinde (`127.0.0.1:4000`) çalıştırıldı.
- Veri gönderimi ve alımı JSON formatında gerçekleştirildi.
- Client, Server'a çıkarma (`cikar`) ve çarpma (`carp`) işlemleri için sayısal veriler gönderdi.
- Server gelen isteği işledi ve işlem sonucunu Client'a geri gönderdi.
- Client-Server arasındaki TCP trafiği Wireshark ile yakalandı ve analiz edildi.
- Yakalanan paketlerde TCP bayrakları incelendi. Özellikle PSH (Push) ve ACK (Acknowledgment) bayraklarını taşıyan paketler gözlemlendi.
- Client-Server arasındaki veri alışverişi TCP Stream üzerinden incelendi.

## Kullanılan Teknolojiler

- Python
- Socket
- TCP
- JSON
- Wireshark

## Çalışma Mantığı

1. Server `127.0.0.1:4000` adresini dinlemeye başlar.
2. Client bu adrese TCP bağlantısı açar.
3. Client, işlem bilgisini JSON olarak gönderir:

```json
{
    "func": "cikar",
    "a": 5,
    "b": 3
}
```

4. Server `func` alanına bakar:
   - `cikar` → `a - b`
   - `carp` → `a * b`
   - diğer durumlar → `"Geçersiz işlem"`
5. Server sonucu JSON olarak geri gönderir:

```json
{
    "result": 2
}
```

6. Client sonucu ekrana yazdırır ve bağlantıyı kapatır.

## Çalıştırma

Önce Server'ı başlatın:

```bash
python server.py
```

Ardından ayrı bir terminalde Client'ı çalıştırın:

```bash
python client.py
```

Farklı bir işlem denemek için `client.py` içindeki `"func"` değerini `"cikar"` ya da `"carp"` olarak değiştirin.

## Örnek Çıktılar

Çıkarma işlemi (`a = 5`, `b = 3`):

```
Sonuç: 2
```

Çarpma işlemi (`a = 5`, `b = 3`):

```
Sonuç: 15
```

## Hazırlayan

Zeynep Sena Taşolar
