# ☀️ Proje: Hava Durumu Veri Analizi Raporu

**Proje Amacı:** Münih şehrine ait Mart-Haziran 2024 (kısmi) günlük hava durumu verilerini analiz ederek iklimsel trendleri, mevsimsel kalıpları ve aykırı hava olaylarını incelemek.

**Veri Seti:** `munich.csv` (20 Mart 2024 - 10 Haziran 2024 arası günlük yağış ve kar verisi)

---

## 1. Ana Bulgular ve Özet

Veri seti üzerinde yapılan keşifsel veri analizi (EDA) ve görselleştirme (Aşama 2 & 3) sonucunda aşağıdaki temel bulgulara ulaşılmıştır:

1.  **Aykırı Hava Olayı (Sel Felaketi):** Veri setindeki en baskın ve önemli olay, **1 Haziran 2024** tarihinde kaydedilen **78.40 mm**'lik günlük yağış miktarıdır. Bu, incelenen periyottaki diğer tüm günlerden dramatik bir şekilde yüksektir ve o dönemde bölgede yaşanan sel ve aşırı yağış haberlerini teyit etmektedir.
2.  **Kar Yağışı Gözlenmemiştir:** İncelenen dönem (20 Mart - 10 Haziran 2024) boyunca kayda değer (veya raporlanan) bir kar yağışı (`snowfall_sum`) gerçekleşmemiştir.
3.  **Mevsimsel Yağış Kalıbı:** Veriler, ilkbahar aylarından (Mart/Nisan) yaz başına (Mayıs/Haziran) geçişte yağış miktarının belirgin şekilde arttığını göstermektedir.
4.  **Yağış Dağılımı:** Yağışlı günlerin çoğunda (Bkz. Grafik 3: Histogram) 1-15 mm arasında hafif ila orta şiddette yağış görülmüştür. Ancak 1 Haziran'daki 78.40 mm ve 27 Mayıs'taki 35.10 mm gibi olaylar, ortalamayı yükselten ekstrem (aykırı) değerlerdir.

---

## 2. Detaylı Analiz ve Görsel Yorumlama

### A. Günlük Yağış Analizi (Grafik 1: Zaman Serisi)

Aşama 3'te oluşturduğumuz günlük yağış grafiği (Line Plot), verinin büyük bölümünün düşük seviyelerde seyrettiğini, ancak Mayıs sonu ve özellikle Haziran başında çok keskin bir "sıçrama" (spike) gösterdiğini net bir şekilde ortaya koymuştur. Bu sıçrama, 1 Haziran'daki 78.40 mm'lik kayıttır.

### B. Aylık Toplam Yağış (Grafik 2: Çubuk Grafik)

Aylık olarak grupladığımız (Aşama 2, `resample`) ve görselleştirdiğimiz (Aşama 3, Bar Plot) veriler, mevsimsel trendi doğrulamıştır:

* **Mart 2024 (Kısmi):** Veri 20 Mart'tan başladığı için ayın en kurak dönemi olarak görünmektedir (diğer aylara kıyasla).
* **Nisan 2024:** İlkbahar yağmurları görülmüş, ancak Mayıs ve Haziran'a göre daha sakin geçmiştir.
* **Mayıs 2024:** Yağış miktarında artış başlamıştır. Özellikle ayın son haftası (27 Mayıs: 35.10 mm, 30 Mayıs: 22.90 mm, 31 Mayıs: 23.20 mm) yüksek yağışlı geçmiştir.
* **Haziran 2024 (Kısmi):** İncelenen dönemin (sadece ilk 10 günü olmasına rağmen) **en yağışlı ayı** olmuştur. Bu durumun neredeyse tamamı, 1 Haziran'daki ekstrem yağıştan kaynaklanmaktadır.

### C. Yağış Frekansı (Grafik 3: Histogram)

Yağışlı günlerin dağılımını incelediğimiz histogram, veri setinin "sağa çarpık" (right-skewed) olduğunu göstermiştir. Bu, şu anlama gelir:
* Münih'te yağmur yağan günlerin **büyük çoğluğunda** (frekansı yüksek olan sol çubuklar) **az miktarda** yağış (örn: 1-10 mm) kaydedilmiştir.
* **Çok az sayıda günde** (frekansı düşük olan sağ çubuklar) **çok yüksek miktarda** yağış (örn: 35 mm veya 78 mm) görülmüştür. Bu da "aykırı hava olayı" tanımını desteklemektedir.

---

## 3. Sonuç ve Değerlendirme

Bu proje, kısa bir zaman aralığındaki (yaklaşık 2.5 ay) günlük verilerin bile iklimsel kalıpları (ilkbahardan yaza artan yağış) ve daha da önemlisi aykırı hava olaylarını tespit etmek için ne kadar değerli olduğunu göstermiştir.

Pandas, Numpy ve Matplotlib kütüphaneleri kullanılarak yapılan bu analiz, Münih'te 2024 yazının başında yaşanan ve ciddi etkilere yol açan **1 Haziran 2024** tarihli **ekstrem yağış olayını** (78.40 mm) verisel olarak net bir şekilde tanımlamıştır. Analiz, bölgenin mevsimsel olarak yağışlı bir döneme girdiğini, ancak bu dönemin normal seyrin dışında, tek bir günde yoğunlaşan şiddetli bir yağış olayı ile karakterize edildiğini ortaya koymuştur.
