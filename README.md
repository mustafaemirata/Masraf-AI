# Masraf-AI

Masraf-AI, kullanıcıların harcama fişlerini fotoğraflayarak sisteme yükleyebildiği, yapay zeka destekli OCR ile fiş verilerini otomatik olarak analiz eden ve sonuçları onay için admine ileten bir **masraf yönetim ve takip** uygulamasıdır.

Kullanıcılar fişlerini kolayca ekler, sistem fiş üzerindeki bilgileri (tutar, tarih, kalem vb.) otomatik olarak çıkarır ve admin paneli üzerinden yetkili kişi bu masraf kalemlerini **onaylayabilir** ya da **reddedebilir**. Böylece kurum içi masraf onay süreçleri dijitalleşir, manuel kontrol yükü azalır.

---

##  Özellikler

-  **Fiş Ekleme:** Kullanıcılar mobil uygulama üzerinden fiş fotoğrafı çekip yükleyebilir.
-  **Otomatik Analiz:** Yüklenen fişler, arka planda çalışan PaddleOCR tabanlı Python API ile otomatik olarak okunup analiz edilir.
-  **Geçmiş Fişler:** Kullanıcılar daha önce yükledikleri fişleri ve durumlarını görüntüleyebilir.
-  **Admin Onay Süreci:** Analiz edilen masraf kalemleri admin paneline düşer; admin fişleri inceleyip onaylayabilir veya reddedebilir.
-  **Sonuç Görüntüleme:** Onaylanan/reddedilen masraflar ve analiz sonuçları kullanıcıya raporlanır.

---

##  Ekran Görüntüleri

### Fiş Ekleme
Kullanıcı, harcama fişini kamera veya galeriden seçerek sisteme yükler.

<img src="images/fis_ekleme.jpeg" alt="Fiş Ekleme" width="400"/>

### Analiz Süreci
Yüklenen fiş, OCR motoru tarafından işlenerek fiş üzerindeki veriler çıkarılır.

<img src="images/analiz.jpeg" alt="Analiz" width="400"/>

### Geçmiş Fişler
Kullanıcı daha önce yüklediği tüm fişleri ve onay durumlarını buradan takip edebilir.

<img src="images/gecmis_fisler.jpeg" alt="Geçmiş Fişler" width="400"/>

### Sonuçlar
Admin onayından geçen ya da reddedilen masraf kalemlerinin özet sonuçları.

<img src="images/sonuclar.png" alt="Sonuçlar" width="400"/>

---

##  Kullanılan Teknolojiler

| Katman | Teknoloji |
|---|---|
| Mobil Uygulama | **Flutter** |
| Veritabanı | **MySQL** |
| OCR / Analiz Servisi | **Python (PaddleOCR API)** |
| Admin Paneli | Web tabanlı yönetim paneli |

---

##  Nasıl Çalışır?

1. Kullanıcı Flutter uygulaması üzerinden fişini fotoğraflar ve yükler.
2. Yüklenen görsel, backend'de çalışan **PaddleOCR Python API**'sine iletilir.
3. API, fiş üzerindeki metinleri (tutar, tarih, satıcı, kalemler vb.) çıkarıp yapılandırılmış veriye dönüştürür.
4. Analiz sonucu **MySQL** veritabanına kaydedilir ve admin paneline yönlendirilir.
5. Admin, panel üzerinden fişi ve çıkarılan masraf kalemlerini inceler.
6. Admin, masrafı **onaylar** ya da **reddeder**; sonuç kullanıcıya yansıtılır.

---

##  Kurulum

> Proje bileşenleri: Flutter mobil uygulama, MySQL veritabanı ve Python tabanlı OCR API.

1. Depoyu klonlayın:
   ```bash
   git clone https://github.com/mustafaemirata/Masraf-AI.git
   cd Masraf-AI
   ```
2. Flutter bağımlılıklarını yükleyin:
   ```bash
   flutter pub get
   ```
3. MySQL veritabanını oluşturun ve bağlantı bilgilerini yapılandırın.
4. PaddleOCR Python API servisini başlatın (gerekli bağımlılıkları kurduktan sonra).
5. Uygulamayı çalıştırın:
   ```bash
   flutter run
   ```

---

##  Notlar

- Admin paneli, masraf kalemlerinin toplu şekilde incelenip onay/red işlemlerinin yapılabildiği ayrı bir arayüzdür.
- OCR servisi, fiş görsellerinden metin çıkarımı için **PaddleOCR** kullanır.

---

