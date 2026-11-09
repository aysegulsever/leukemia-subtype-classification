# Üretken Yapay Zekâ (GenAI) Kullanım Beyanı

**Proje:** ALL/AML lösemi alt tipi sınıflandırması (Ara Rapor)

**Araç ve sürüm:** Claude (Anthropic), Sonnet 5.5 (tablodaki tüm satırlarda aynı araç kullanılmıştır)

**Genel not:** Çalışmada taslak fikirler, kod örnekleri, literatür özetleri ve biçimlendirme konularında Claude'dan yardım aldım. Kodu Colab'da kendim çalıştırdım, çıktıları kendim inceledim ve rapordaki sayıları kendi çıktılarımla karşılaştırdım. Kod ve metinlerin sorumluluğu bana aittir.

## 1. Kullanım tablosu

| Amaç | Bölüm / dosya | Benim yaptığım değişiklik | Nasıl doğruladım |
| --- | --- | --- | --- |
| Ödev kılavuzunun adım adım açıklanması | Plan | Kılavuzu kendim okudum ve adımları zamanıma göre sıraladım | Puan tablosuyla karşılaştırdım |
| Depo yapısı ve git komutları | Depo, ilk commit | Komutları kendim çalıştırdım; boş klasör, `main`/`master` ve söz dizimi hatalarını çözdüm; GitHub'a yüklemeyi en sona bırakmaya karar verdim | `git status`, `git log` çıktıları |
| Golub verisini yükleme, etiket eşleme, veri kalitesi, log2 dönüşümü | Not defteri, hücre 1–4 | Kodu Colab'da çalıştırdım, çıktıları (boyutlar, sınıf sayıları, sütun sırası) paylaştım ve inceledim | 7129×78, 47 ALL / 25 AML, NaN/INF kontrolü, histogramlar |
| Gen filtresi, PCA, t-SNE ve UMAP | hücre 5–6 | Çıktıları inceledim; t-SNE girdisiyle ilgili hatalı açıklamayı düzelttirdim | 3.571 gen, PC1 %16,1 / PC2 %11,4, kodun okunması |
| Diferansiyel ifade (Mann–Whitney U + BH), ısı haritası, eğitim/test parti testi | hücre 7–8 | Çıktıları paylaştım ve yorumların çıktılara uymasını sağladım | q < 0,05: 986 gen; ısı haritasındaki kümeleme |
| İkinci veri seti seçenekleri | Rapor, Veri Setleri | Final raporuna uygunluğu sorarak seçimi (GSE14062) ben yaptım | GEO sayfası ve örnek başlıkları |
| GSE14062 yükleme, etiket ayıklama, EDA, ortak gen karşılaştırması | hücre 9–14 | `ModuleNotFoundError` hatasını `pip install` ile çözdüm; hücre numaralandırmasındaki karışıklığı fark edip not defterini tek düzenli akışa getirdim; eşik hücresini tek hücrede birleştirdim | 106 ALL / 34 AML / 24 MLL+, 753 ortak gen, Spearman ρ, işaret uyumu çıktıları |
| Literatür taraması, kaynakça ve özet tablosu | Rapor, İlgili Çalışmalar | Kaynakların bağlantılı olarak doğrulanmasını ben istedim; taslağı inceledim | Kaynak bilgileri yayıncı sayfalarından toplandı; DOI sayfalarının kişisel kontrolü ve eksik başlıkların tamamlanması devam ediyor |
| Finale kadar plan ve IEEE (LaTeX) rapor taslağı | Rapor, Finale Kadar Plan | Metni inceledim, şekilleri Overleaf'e yükledim | Notebook çıktıları ve ödev kılavuzuyla karşılaştırdım |
| README, `requirements.txt` ve GitHub'a yükleme adımları | Depo | Komutları kendim çalıştırdım, hataları ve çıktıları paylaştım | `git log`, GitHub sayfası |

## 2. Önemli istemlerin özeti

- **Kapsam:** Kılavuzu paylaşıp ara rapor için yapılacakları sordum.
- **Kod:** Her EDA adımı için Colab hücresi istedim, çıktıları geri paylaşıp yorumları çıktılarıma göre düzelttirdim.
- **Veri seti:** Seçenekleri sordum; GSE14062'yi seçtim.
- **Literatür:** Kaynak listesi ve bilgi doğrulaması istedim; tarama genel web araması ve yayıncı sayfaları üzerinden yapıldı.
