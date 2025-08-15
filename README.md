S&P 500 Yükseliş/Düşüş Tahmin Modeli
Bu proje, S&P 500 borsa endeksinin (^GSPC) bir sonraki işlem gününde yükselip yükselmeyeceğini tahmin eden bir makine öğrenimi modelini içerir. Proje, Python tabanlı bir Jupyter Notebook (sp500.ipynb) kullanılarak geliştirilmiştir. Tarihi borsa verileri yfinance kütüphanesiyle çekilmiş, veri temizleme ve özellik mühendisliği yapılmış, ardından Random Forest Classifier kullanılarak tahmin modeli oluşturulmuştur.
Projenin Amacı

Amaç: S&P 500 endeksinin günlük kapanış fiyatlarının bir sonraki gün artıp artmayacağını tahmin etmek.
Yöntem: Tarihi veriler kullanılarak makine öğrenimi modeli eğitilir ve geri test (backtesting) ile performans değerlendirilir.
Veri Kaynağı: Yahoo Finance üzerinden S&P 500 endeksi (^GSPC) verileri (1927-2025).
Model: Scikit-learn kütüphanesindeki Random Forest Classifier.
Performans: Yeni özellikler eklendikten sonra model, %57.13 hassasiyet (precision score) elde etmiştir.

Özellikler

Veri Toplama: Yahoo Finance’ten S&P 500 endeksine ait tarihi veriler (Open, High, Low, Close, Volume).
Özellik Mühendisliği: Hareketli ortalamalara oranlar (close_ratio) ve geçmiş trendler (trend) gibi yeni özellikler.
Geri Test: Zaman serisi farkındalığıyla modelin geçmiş verilerdeki performansı test edilir.
Görselleştirme: Tahminler ve gerçek değerler matplotlib ile görselleştirilir.

Gereksinimler
Projenin çalışması için aşağıdaki Python kütüphanelerine ihtiyaç vardır:

yfinance: Borsa verilerini çekmek için.
pandas: Veri manipülasyonu ve analizi için.
numpy: Sayısal hesaplamalar için.
matplotlib: Veri görselleştirme için.
scikit-learn: Makine öğrenimi modeli için.

Kurulum için aşağıdaki komutları çalıştırabilirsiniz:
pip install yfinance pandas numpy matplotlib scikit-learn

Kurulum ve Kullanım

Depoyu Klonlayın:
git clone https://github.com/kullanici_adi/sp500-tahmin-modeli.git
cd sp500-tahmin-modeli


Gereksinimleri Kurun:Yukarıdaki kütüphaneleri yüklemek için:
pip install -r requirements.txt

(Not: requirements.txt dosyasını oluşturmak için bağımlılıkları manuel olarak eklemeniz gerekebilir.)

Jupyter Notebook’u Çalıştırın:
jupyter notebook sp500.ipynb


Hücreleri Çalıştırın:

Notebook’taki hücreleri sırayla çalıştırarak verileri çekin, temizleyin, modeli eğitin ve tahminleri değerlendirin.
Not: Notebook, 1927’den 2025’e kadar veri çeker. İnternet bağlantısı gereklidir.



Proje Yapısı

sp500.ipynb: Ana Jupyter Notebook dosyası. Veri çekme, temizleme, modelleme ve geri test adımlarını içerir.
README.md: Bu dosya, projenin açıklamasını ve kullanım talimatlarını içerir.

Kod Akışı

Veri Çekme: yfinance ile S&P 500 verileri çekilir (^GSPC).
Veri Temizleme: Eksik veriler kaldırılır ve hedef değişken (Target) oluşturulur (bir sonraki günün kapanış fiyatı mevcut günden büyükse 1, değilse 0).
Özellik Mühendisliği: Hareketli ortalamalara oranlar (close_ratio_2, close_ratio_5, vb.) ve geçmiş trendler (trend_2, trend_5, vb.) eklenir.
Model Eğitimi: Random Forest Classifier (n_estimators=200, min_samples_split=50) kullanılır.
Geri Test: Veri, 2500 günlük başlangıç eğitimi ve 250 günlük test adımlarıyla test edilir.
Değerlendirme: Hassasiyet skoru hesaplanır (%57.13).
Görselleştirme: Tahminler ve gerçek değerler grafikle gösterilir.

Performans

İlk model (temel özelliklerle): %52.79 hassasiyet.
Geliştirilmiş model (hareketli ortalamalar ve trendlerle): %57.13 hassasiyet.
Tahmin Dağılımı:
Düşüş (0): 4600 gün
Yükseliş (1): 870 gün


Gerçek Değer Dağılımı:
Yükseliş (1): %53.69
Düşüş (0): %46.31



Gelecek İyileştirmeler

Daha fazla özellik ekleme (örneğin, teknik göstergeler: RSI, MACD).
Farklı makine öğrenimi modelleri deneme (örneğin, XGBoost, LSTM).
Hiperparametre optimizasyonu (Grid Search veya Random Search).
Daha uzun vadeli tahminler için modelin uyarlanması.

Katkıda Bulunma
Katkıda bulunmak isterseniz:

Depoyu forklayın.
Yeni bir dal oluşturun (git checkout -b ozellik-ekleme).
Değişikliklerinizi yapın ve commit edin (git commit -m "Yeni özellik eklendi").
Dalınızı itin (git push origin ozellik-ekleme).
Bir Pull Request oluşturun.

İletişim
Sorularınız veya önerileriniz için: devrim.boz16@gmail.com
