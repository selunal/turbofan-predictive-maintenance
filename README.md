# turbofan-predictive-maintenance
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
