# Yapay Sinir Ağları ile Makine Öğrenmesi Modeli
Bu projede, çeşitli memnuniyet verilerini kullanarak yapay sinir ağları ile makine öğrenmesi modeli oluşturacağız. Veriler üzerinde ön işleme, model oluşturma, eğitme ve değerlendirme adımlarını gerçekleştireceğiz.

# Veri Yükleme ve Hazırlık
Veriler, metin formatında data değişkenine kaydedilir ve ardından data.csv dosyasına yazılır.
pandas kullanarak veriler data.csv dosyasından yüklenir.

# Veri Ön İşleme
Yas ve Cinsiyet sütunlarındaki kategorik veriler sayısal değerlere dönüştürülür (18-24 -> 0, 25+ -> 1, Kadin -> 0, Erkek -> 1).
Memnuniyet sütunu da sayısal değerlere dönüştürülür (Memnun -> 2, NeMemnunNeMemnunDegil -> 1, MemnunDegil -> 0).

# Hedef ve Bağımsız Değişkenlerin Ayrılması
X değişkeni, Yil, Yas, Cinsiyet ve Yuzde sütunlarından oluşur.
y değişkeni, Memnuniyet sütunundan oluşur.

# Verilerin Standartlaştırılması
StandardScaler kullanılarak veriler standartlaştırılır, böylece her özelliğin ortalaması 0 ve standart sapması 1 olur.

# Verilerin Eğitim ve Test Setlerine Ayrılması
Veriler %70 eğitim ve %30 test setlerine ayrılır (train_test_split kullanılarak).

# Yapay Sinir Ağı Modeli Oluşturma
Sequential model oluşturulur ve sırayla katmanlar eklenir:

İlk katman: 12 nöron, relu aktivasyon fonksiyonu.
İkinci katman: 8 nöron, relu aktivasyon fonksiyonu.
Çıkış katmanı: 3 nöron (sınıf sayısı kadar), softmax aktivasyon fonksiyonu.

# Modeli Derleme
Model, sparse_categorical_crossentropy kayıp fonksiyonu ve adam optimizasyon algoritması ile derlenir.

# Modeli Eğitme
Model, eğitim verileri üzerinde 100 epoch boyunca, her bir epoch'ta 10 veriyi işleyerek (batch_size=10) eğitilir.
Eğitim sırasında, doğrulama verileri (validation_split=0.2) kullanılarak modelin doğrulama kaybı hesaplanır.

# Tahmin Yapma ve Değerlendirme
Test verileri kullanılarak tahminler yapılır (predict fonksiyonu ile) ve tahmin edilen sınıf etiketleri elde edilir (np.argmax kullanılarak).

# Modelin Performansını Değerlendirme
classification_report ve confusion_matrix kullanılarak modelin performansı değerlendirilir ve sonuçlar yazdırılır.

# Eğitim ve Doğrulama Kayıplarını Görselleştirme
Eğitim ve doğrulama kayıpları matplotlib kullanılarak görselleştirilir.
