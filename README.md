# # Orbit Sim 

##  Özellikler
* **Fizik Motoru:** Gerçek fizik formülleri kullanılarak gezegenlerin anlık hız ve ivme hesaplamaları.
* **Görselleştirme:** Pygame ile dinamik yörünge çizimi ve gezegen hareketlerinin 2D düzlemde gösterimi.
* **Otomatik GIF Kaydı:** Simülasyon çıktılarının `imageio` kütüphanesi ile otomatik olarak GIF formatında dışa aktarılması.

##  Kullanılan Kütüphaneler
* **Python**
* **Pygame:** Oyun döngüsü ve grafik arayüz için.
* **Math:** Trigonometrik hesaplamalar ve vektör işlemleri için.
* **ImageIO:** Görüntü işleme ve animasyon oluşturma için.

## Örnek Çıktı 
![planet_simulation](https://github.com/user-attachments/assets/c640ce73-9879-4a9e-88e3-2b0718411d9c)



### 2. GMT 327 Projesi
#  Uydu Yörünge Analizi ve Görünürlük Hesaplayıcı

Bu projenin amacı Kepler yörünge elemanlarını kullanarak uyduların yörünge takibini yapan ve yerdeki bir istasyon için görünürlük analizi gerçekleştiren araçtır 

## Özellikler
* **Koordinat Dönüşümleri:** Kepler yörünge elemanlarından ECI (Earth-Centered Inertial) ve ECEF (Earth-Centered Earth-Fixed) koordinat sistemlerine dönüşüm.
* **Görünürlük Analizi:** Belirli bir yer istasyonu için uydunun Azimuth (Semt) ve Elevation (Yükseklik) açılarının hesaplanması.
* **Harita Tabanlı Görselleştirme:** `Cartopy` kullanılarak uydu izinin (Ground Track) dünya haritası üzerinde çizilmesi.
* **Zaman Analizi:** `Astropy` ile Julian Date ve Sidereal Time (Yıldız Zamanı) hesaplamaları.

##  Kullanılan Kütüphaneler
* **Python**
* **Astrophy:** Astronomik zaman ve koordinat hesaplamaları için .
* **Cartophy, Matplotlib:** Coğrafi veri görselleştirme ve harita projeksiyonu için.
* **Numpy:** Vektörel hesaplamlar ve matris operasyonları için.

## 📊 Örnek Çıktı
<img width="703" height="688" alt="Başlıksız" src="https://github.com/user-attachments/assets/97d460d3-a8de-46ef-a29b-756fed66cd75" />

*Bu proje Hacettepe Üniversitesi Jeomatik Mühendisliği bölümü GMT327 dersi kapsamında geliştirilmiştir.*


# 🌍 GMT 225 
# Jeodezik Koordinat Dönüşüm Hesaplayıcı 

## 🧮 İçerdiği Modüller

### 1. 3D Rotasyon Matrisleri (Rotation Matrices)
* Uzaydaki bir vektörün X, Y ve Z eksenleri etrafında döndürülmesini sağlayan temel rotasyon matrislerinin  kodlanması.
* Euler açıları kullanılarak sıralı rotasyon işlemlerinin gerçekleştirilmesi.

### 2. Kartezyen -> Elipsoidal Koordinat Dönüşümü (XYZ to BLH)
* Yer merkezli Kartezyen koordinatların ($X, Y, Z$), elipsoidal koordinatlara (Enlem $\phi$, Boylam $\lambda$, Yükseklik $h$) dönüştürülmesi.
* **İteratif Çözüm:** Enlem ($\phi$) hesaplamasında hassasiyeti artırmak için iteratif bir algoritma kullanılmıştır.
* Referans Elipsoid parametreleri (a, f, e²) kullanılarak jeodezik hesaplamalar yapılmıştır.

## 🛠 Kullanılan Kütüphaneler
* **NumPy:** Matris çarpımları (`np.dot`), lineer cebir işlemleri ve vektör manipülasyonu.
* **Math:** Temel trigonometrik fonksiyonlar.

---
*Bu proje Hacettepe Üniversitesi Jeomatik Mühendisliği bölümü GMT225 dersi kapsamında geliştirilmiştir.*




# 🛰️Satellite Ground Track Generator 

Bu proje, Python kullanarak belirlenen yörünge parametrelerine göre bir uydunun Dünya üzerindeki izini (Ground Track) simüle eden ve harita üzerinde görselleştiren bir araçtır

Simülasyon, Dünya'nın kendi ekseni etrafındaki dönüşünü ve uydunun yörünge hareketini senkronize bir döngü içinde hesaplayarak uydunun anlık konumunu haritaya işler.

##  Temel Özellikler
* **Dinamik Yörünge Takibi:** Zamanın her saniyesi için uydunun konumunu günceller ve Dünya'nın dönüşünü hesaba katarak (Earth Rotation) iz düşümünü hesaplar.
* **Koordinat Dönüşümleri:** Yörünge düzleminden coğrafi koordinatlara (Enlem/Boylam) anlık dönüşüm yapar.
* **Görselleştirme:** `Cartopy` ve `Matplotlib` kullanarak uydunun rotasını dünya haritası üzerinde çizer.

##  Kullanılan Kütüphaneler
* **Python 3.x**
* **NumPy:** Vektörel hesaplamalar ve nümerik işlemler için.
* **Astropy:** Astronomik birimler ve zaman dönüşümleri için.
* **Cartopy:** Coğrafi veri işleme ve harita projeksiyonları (PlateCarree vb.) için.
* **Matplotlib:** Grafik çizimi ve görselleştirme için.
* **Math:** Trigonometrik fonksiyonlar için.

## ⚙️ Nasıl Çalışır?
1. **Başlangıç:** Uydu yörünge parametreleri ve başlangıç zamanı tanımlanır.
2. **Döngü (Loop):** Kod, her saniye için:
    * Uydunun yörünge üzerindeki yeni konumunu hesaplar.
    * Dünya'nın o sürede ne kadar döndüğünü hesaplayıp koordinat sistemini günceller.
    * Bulunan (Enlem, Boylam) çiftini harita üzerine bir nokta olarak ekler.
3. **Sonuç:** Uydunun geçtiği güzergah (Ground Track) harita üzerinde net bir şekilde görülür.
4. <img width="1181" height="623" alt="image" src="https://github.com/user-attachments/assets/0d255a49-f171-41af-8482-62be02d2c8ba" />


