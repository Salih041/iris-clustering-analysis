# İris Veri Seti Üzerinde Karşılaştırmalı Kümeleme Analizi

Bu proje, K-Means ve Hiyerarşik Kümeleme algoritmalarının performansını ve veri ön işleme (ölçeklendirme) adımlarının sonuçlar üzerindeki etkisini analiz etmektedir.

**[Çalışmanın detaylı PDF raporuna (KMeans ve Hiyerarşik Kümeleme.pdf) buradan ulaşabilirsiniz.]**

## 1. Projenin Amacı

Bu çalışmada, klasik İris veri seti üzerinde iki temel gözetimsiz kümeleme algoritmasının (K-Means ve Hiyerarşik) performansı, iki farklı veri ön işleme senaryosu (Ham Veri ve Ölçekli Veri) altında karşılaştırılmıştır.

## 2. Kullanılan Metodoloji

Analiz için 4 farklı senaryo tasarlanmıştır:
* K-Means (Ham Veri)
* K-Means (Ölçekli Veri)
* Hiyerarşik Kümeleme (Ham Veri)
* Hiyerarşik Kümeleme (Ölçekli Veri)

**Modeller:**
* `KMeans(n_clusters=3, random_state=42, n_init=10)`
* `AgglomerativeClustering(n_clusters=3)` (Varsayılan 'ward' metodu ile)

## 3. Temel Bulgular

* **En İyi Performans:** Ham (ölçeksiz) veri üzerinde, her iki model de (K-Means ve Hiyerarşik) 150 örnekte **16'şar hata** yaparak neredeyse birebir aynı ve yüksek bir başarı sergilemiştir.

* **Ön İşlemenin Etkisi:** `StandardScaler` ile yapılan ölçeklendirme, İris'in 4 özniteliği de 'cm' cinsinden olduğu için verinin doğal yapısını bozmuş ve her iki modelin de performansını düşürmüştür.

* **Algoritma Dayanıklılığı:** Hatalı ön işleme (ölçekli veri) senaryosunda, K-Means'in performansı **bozulurken** (25 hata), Hiyerarşik Kümeleme'nin performansı **tamamen çökmüştür**. Bu, K-Means'in daha dayanıklı olduğunu göstermektedir.

## 4. Nihai Sonuç

İris veri setini kümelemek için en iyi yöntem ham veriyi kullanmaktır. Bu senaryoda iki model de performans açısından eşdeğerdir. Ancak K-Means'in farklı senaryolara karşı daha dayanıklı olduğu gözlenmiştir.

---
*Bu proje; 25.10.2025 tarihinde, Eskişehir Osmangazi Üniversitesi Bilgisayar Mühendisliği bünyesindeki gönüllü yapay zeka asistanlığı projesi kapsamında yapılmıştır.*
