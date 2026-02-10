# OpenCV ve MediaPipe ile Pose Estimation (Vücut Duruş Tespiti)

Bu proje, bir video dosyası ya da kamera akışı üzerinden insan vücudunun iskelet yapısını (pose landmark) gerçek zamanlı olarak tespit eden ve görselleştiren bir Python uygulamasıdır.

---

## Özellikler

* **Gerçek Zamanlı İskelet Tespiti:** MediaPipe Pose modeli sayesinde 33 vücut landmark noktası anlık olarak tespit edilir ve ekranda çizdirilir.
* **Video & Kamera Desteği:** Hem kayıtlı video dosyaları hem de canlı kamera akışı (webcam) ile çalışacak şekilde yapılandırılmıştır.
* **FPS Göstergesi:** Ekranda anlık kare hızı (FPS) görüntülenerek performans takibi yapılabilir.
* **Spesifik Eklem Vurgulaması:** Belirli bir landmark noktası (örneğin sol dirsek - ID: 13) renkli bir daire ile özel olarak işaretlenebilir.
* **Hareket Analizi Altyapısı:** Kod, landmark koordinatlarından yararlanarak ileri düzey hareket tespiti için genişletilmeye uygun şekilde tasarlanmıştır.

---

## Potansiyel Kullanım Alanları

Kodun ilerleyen versiyonlarında şu hareket türleri tespit edilebilir:

* 🏃 **Koşu Analizi:** Ayaklar arası mesafe ve dizlerin bükülme açısının takibi.
* 🏀 **Basketbol Hareketleri:** Dirsek kırılımı, tek elin yukarı çıkması ve turnike bırakma hareketi.
* 🪢 **İp Atlama:** İki elin simetrik hareketi ve zıplama döngüsünün tespiti.
* ⚙️ **Genel Hareket Sınıflandırma:** Karakteristik açılar ve pozlar kullanılarak yapılan hareket türü tespit edilebilir.

---

## Kurulum

### Gereksinimler

* Python 3.9 veya üzeri
* Sanal ortam (venv) kullanılması **önerilir**

### Adımlar

```bash
# 1. Repoyu klonlayın
git clone https://github.com/umutugrasan/pose-estimation-mediapipe.git
cd pose-estimation-mediapipe

# 2. Sanal ortam oluşturun ve aktif edin
python -m venv venv

# Windows:
venv\Scripts\activate

# macOS / Linux:
source venv/bin/activate

# 3. Bağımlılıkları yükleyin
pip install -r requirements.txt
```

---

## Kullanım

```bash
python pose-estimation-mediapipe.py
```

> **Video Modu:** `cap = cv2.VideoCapture("video5.mp4")` satırına kendi video dosyanızın adını yazın.
>
> **Kamera Modu:** Aynı satırı `cap = cv2.VideoCapture(0)` olarak değiştirin.

---


Projede kullanılan vücut eklem noktalarının (landmark) referans şeması aşağıdadır:


![Pose Estimation](/pose_estimation_schema.png)



> ⭐ Bu projede ID: 13 (sol dirsek) mavi daire ile özel olarak işaretlenmiştir.

## Öğrenilenler

Bu süreçte aşağıdaki konularda pratik deneyim kazanılmıştır:

* Görüntü işleme (Computer Vision) temelleri ve OpenCV kullanımı.
* MediaPipe Pose modelinin entegrasyonu ve landmark koordinatlarının okunması.
* Vücut eklem noktalarının piksel koordinatlarına dönüştürülmesi.
* Video akışı üzerinde gerçek zamanlı görselleştirme ve FPS hesaplama.
* Sanal ortam (virtual environment) yönetimi ve bağımlılık takibi.

---

## Kullanılan Teknolojiler

| Kütüphane  | Versiyon   | Kullanım Amacı                  |
|------------|------------|---------------------------------|
| OpenCV     | 4.8.1.78   | Görüntü işleme ve görselleştirme|
| MediaPipe  | 0.10.7     | Pose landmark tespiti           |

---







