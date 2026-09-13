# Turbofan Engine Predictive Maintenance

NASA CMAPSS Turbofan Jet Engine dataset kullanılarak geliştirilen bir RUL 
(Remaining Useful Life) tahmin modeli.

## Sonuçlar
- Model: Random Forest Regressor
- MAE: 11.78 çevrim
- R²: 0.84

## Yöntem
- Feature engineering: rolling mean/std (5 çevrimlik pencere)
- RUL capping (üst sınır 125)
- Motor bazlı train/test ayrımı (veri sızıntısını önlemek için)

## En Belirleyici Sensörler
sensor_4 (LPT sıcaklığı), sensor_9 (çekirdek dönüş hızı), sensor_11 
(HPC çıkış basıncı) — HPC bozulması arıza modu ile fiziksel olarak tutarlı.

## Proje 2: Anomaly Detection (Isolation Forest)

Etiketli RUL verisi kullanılmadan (unsupervised), sensör verilerine bakarak 
motorların arızaya yaklaştığını tespit eden bir model.

**Sonuçlar:**
- Anomali işaretli satırların ortalama RUL'u: 10.1 çevrim (arızaya çok yakın)
- Normal satırların ortalama RUL'u: 110.5 çevrim
- Motorların yarısında, ilk anomali sinyali arızadan ortalama 12 çevrim önce geliyor

**Anlamı:** Gerçek etiket olmadan bile erken uyarı sistemi kurulabiliyor — 
predictive maintenance'ın unsupervised versiyonu.
