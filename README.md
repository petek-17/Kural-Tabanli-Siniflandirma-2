# Kural-Tabanli-Siniflandirma-2
# ✈️ Kural Tabanlı Sınıflandırma ile Satış Segmentasyonu ve Gelir Tahmini

Bu proje, Gezinomi benzeri bir seyahat şirketinin satış verileri üzerinden **seviye tabanlı satış tanımları (persona)** oluşturarak, bu tanımlara göre **segmentasyon** yapmayı ve **potansiyel gelir tahmini** gerçekleştirmeyi amaçlamaktadır.

---

## 🧠 Amaç

Bir seyahat firması, yaptığı satışların belirli özelliklerini (şehir, konsept, mevsim) kullanarak:
- Yeni satış tanımları (`persona`) üretmek,
- Bu tanımları segmentlere ayırmak,
- Gelecekteki satışlardan beklenen **ortalama geliri** tahmin etmek istemektedir.

---

## 📁 Veri Seti

Veri setinde her satır bir satış işlemine karşılık gelir.

| Değişken         | Açıklama                              |
|------------------|---------------------------------------|
| `SaleCityName`   | Satışın gerçekleştiği şehir           |
| `ConceptName`    | Tatil/otel konsepti                   |
| `Seasons`        | Satışın gerçekleştiği sezon           |
| `Price`          | Satıştan elde edilen gelir (TL)       |

---

## 🛠 Kullanılan Araçlar ve Kütüphaneler

- Python 3
- pandas
- numpy

---

## 📊 Uygulanan Adımlar

### 1. Veri Analizi
- Satış verilerinin ilk keşfi (`value_counts`, `describe`)
- Veri temizliği ve tutarlılık kontrolü

### 2. Seviye Tabanlı Satış Tanımı (Persona)
- `CITY-CONCEPT-SEASON` birleşimleriyle benzersiz satış tanımları üretildi  
  Örn: `ANTALYA_ULTRA HER ŞEY DAHIL_HIGH`

### 3. Ortalama Gelire Göre Segmentasyon
- Her satış personası için ortalama gelir (`Price`) hesaplandı
- Satışlar 4 segmente ayrıldı: `A`, `B`, `C`, `D`

### 4. Yeni Satışların Gelir Tahmini
- Örneğin: “Yaz sezonunda Bodrum'da High Class Her Şey Dahil satışı” için segment ve tahmini gelir hesaplandı

---

## 📈 Örnek Kod

```python
# Yeni satış örneği: Bodrum, High Class Her Şey Dahil, Yaz
persona = "BODRUM_HIGH CLASS HER ŞEY DAHİL_SUMMER"
agg_df[agg_df["sales_level_based"] == persona]
