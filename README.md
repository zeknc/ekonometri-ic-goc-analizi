# 📊 Analiz Dosyaları

Bu klasör, projenin ekonometrik analizlerinde kullanılan EViews çalışma dosyalarını içermektedir.

## 📁 Dosyalar

### 1. `goc_ısz.wf1`
**İçerik:** İç göç ve işsizlik oranı arasındaki ilişkinin analizi  
**Değişkenler:**
- GOC (İç Göç)
- ISZ (İşsizlik Oranı)

**Analizler:**
- Zaman serisi grafiği
- Korelasyon analizi
- Temel istatistikler

---

### 2. `goc_isz_gsmh.wf1`
**İçerik:** İç göç, işsizlik ve GSYİH'nin birlikte analizi (Ana analiz dosyası)  
**Değişkenler:**
- GOC (İç Göç)
- ISZ (İşsizlik Oranı)
- GSYIH (Gayri Safi Yurt İçi Hasıla)
- LOGGOC (İç göçün logaritması)

**Analizler:**
- Regresyon modelleme
- Breusch-Godfrey LM testi
- ACF/PACF analizi
- Model diagnostik testleri
- Tahmin ve öngörü

---

## 🚀 Nasıl Kullanılır?

### EViews ile Açma:

1. **EViews yazılımını açın**
2. **File → Open → Workfile** seçin
3. `.wf1` dosyasını seçin
4. Workfile yüklenecektir

### Değişkenleri Görüntüleme:

```
# EViews komut satırında:
show goc isz gsyih        # Verileri görüntüle
plot goc isz gsyih        # Grafik çiz
```

### Regresyon Modelini Çalıştırma:

```
# EViews komut satırında:
equation eq1.ls loggoc c isz gsyih
eq1.view results
```

---

## 📌 Notlar

- **EViews Versiyonu:** Bu dosyalar EViews 10 veya üzeri versiyonlarla uyumludur
- **Veri Dönemi:** 2008-2023 (16 yıllık veri)
- **Veri Kaynağı:** TÜİK ve TCMB

---

## 🔍 Model Detayları

### Model 1 (Tam Model):
```
LOGGOC = β₀ + β₁(ISZ) + β₂(GSYIH) + ε
```

**Sonuç:** İşsizlik katsayısı anlamsız (p > 0.05)

---

### Model 2 (İndirgenmiş Model):
```
LOGGOC = β₀ + β₁(GSYIH) + ε
```

**Sonuç:** GSYİH katsayısı anlamlı (p < 0.05)  
**Katsayı:** 0.106335 (pozitif ilişki)

---

## 📚 İlgili Dosyalar

- **Detaylı Rapor:** `/report/proje_raporu.pdf`
- **Ham Veri:** `/data/ic_goc_issizlik_data.xlsx`
- **Grafikler:** `/images/`

---

## 👨‍🎓 Yazar

**Zehra Ekinci**  
İstatistik ve Bilgisayar Bilimleri Bölümü  
Bilecik Şeyh Edebali Üniversitesi

**Danışman:** Prof. Dr. Serpil Türkyılmaz
