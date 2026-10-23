# Safety 4.0 Bootcamp – Laboratuvar Föyleri (ISP Group Banbury Mixer Sürümü)

**Ad Soyad:** Berfin Aslan  
**Grup:** Gece-B
**Tarih:** 23.10.2026

## Seçilen Makine
**ISP Group – Banbury Mixer PLC-SCADA Otomasyon Sistemi**

Banbury mixer, lastik ve kauçuk fabrikalarının karışım tesislerinde kullanılan bir iç karıştırıcıdır. İçindeki iki büyük rotor hamuru ezip karıştırır, üstteki hidrolik ram hamuru aşağı bastırır, hazır karışım alttaki boşaltma kapağından dökülür. ISP Group bu makineyi hammadde tartımından raporlamaya kadar tek bir PLC-SCADA sistemiyle yönetir. Senaryoda makine bir lastik fabrikasının karışım tesisinde çalışmaktadır.

**ISP Group sayfasındaki temel özellikler:**
- Tek PLC-SCADA sistemi (Siemens / Allen Bradley / Mitsubishi)
- Reçete bazlı step cycle programı, otomatik hammadde tartımı ve dozajlama
- Yardımcı ünitelerin kontrolü (TCU, hidrolik ünite, yağlama sistemi)
- SCADA ve andon bilgi ekranları
- ERP üzerinden reçete alma ve rapor gönderme
- Operatör adıyla kullanıcı bazlı işlem takibi
- Makinelerle haberleşip gerçek zamanlı veri toplayan i-MES yazılımı

> Not: Otomasyon bilgileri ISP Group'un web sitesindeki "Banbury Mixer Otomasyonu" ve "i-MES" sayfalarından alınmıştır. Emniyet ekipmanları (kapak kilitleri, acil stop, ram kilidi) belgede yer almadığı için iç karıştırıcı emniyet standardı EN 12013 esas alınarak ele alınmıştır.

## Laboratuvarlar

| Lab | Konu | Çıktı | Dosya |
|-----|------|-------|-------|
| 1 | Safety Architecture | Safety Function Map | `Lab1_Safety_Architecture.pdf` |
| 2 | IEC 62443 Mini Workshop | Zone / Conduit Diagram | `Lab2_IEC62443_Mini_Workshop.pdf` |
| 3 | Threat & Risk + Risk Matrix | Risk Register | `Lab3_Threat_Risk_Matrix.pdf` |
| 4 | Secure Remote Access | Secure Architecture | `Lab4_Secure_Remote_Access.pdf` |

## Özet
- **Tehlikeler:** dönen rotorlara kapılma, inen hidrolik ram ve boşaltma kapağıyla ezilme, sıcak hamur ve TCU suyuyla yanık, hidrolik basınç
- **Emniyet fonksiyonları:** kapak açıkken rotor ve ram hareketini durdurma, acil stop, bakımda ram'ın inmesini önleme (mekanik kilit + LOTO)
- **Kritik bulgu:** reçete ERP → i-MES → SCADA → PLC zinciriyle ağ üzerinden iniyor; ram basıncı ve sıcaklık reçetede olduğu için bozuk bir reçete fiziksel zarar üretebilir; emniyet zinciri PLC'den ayrı olmalı
- **Hedef mimari:** DMZ'de ara sunucu / jump server, VPN + MFA, rol bazlı kişisel hesaplar, reçete ve program değişiklik kaydı, varsayılan kapalı servis erişimi

*Bu föyler bir eğitim çıktısıdır; resmî denetim veya uygunluk değerlendirmesi değildir.*
