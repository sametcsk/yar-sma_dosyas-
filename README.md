# Bilişsel Skor Tahmini - Veri Bilimi Yarışması

Bu repository, katıldığımız veri bilimi yarışması kapsamında geliştirdiğimiz makine öğrenmesi modellerini, veri ön işleme adımlarını ve tahminleme süreçlerini içermektedir. Projenin temel amacı, verilen eğitim veri setini kullanarak en düşük hata payıyla hedef değişkeni tahmin etmektir.

## Proje Amacı ve Yaklaşımımız

Yarışma verisinden en iyi performansı elde edebilmek için kapsamlı bir veri analizi ve özellik mühendisliği (feature engineering) süreci yürüttük. Modellerin genelleme yeteneğini artırmak için aykırı değer analizi, eksik veri tamamlama ve yeni değişken türetme adımlarını uyguladık. 

Çözüme ulaşırken tek bir yönteme bağlı kalmadık; probleme **iki farklı teknik açıyla** yaklaştığımız iki ayrı çözüm (notebook) hazırlayıp yükledik:
- **Birinci Yaklaşım:** Veriyi detaylı bir şekilde işleyip, LightGBM ve CatBoost gibi güçlü ağaç tabanlı algoritmalarla manuel olarak uçtan uca modeller kurmaya ve optimize etmeye odaklandık.
- **İkinci Yaklaşım:** AutoGluon altyapısını kullanarak otomatik makine öğrenmesi (AutoML) süreçlerini değerlendirdik. Bu aşamada farklı modellerin çıktılarını istifleme (stacking) ve ağırlıklı harmanlama (weighted blending) yöntemleriyle birleştirerek performansı maksimize etmeyi ve aşırı öğrenmeyi (overfitting) engellemeyi hedefledik.

## Dosya Yapısı

- train.csv: Modellerin eğitildiği orijinal eğitim veri seti.
- test_x.csv: Model performansını ölçmek ve nihai tahminleri oluşturmak için kullanılan test veri seti.
- train_processed.csv / test_processed.csv: Veri ön işleme ve özellik mühendisliği adımlarından geçmiş, doğrudan model eğitimine hazır hale getirilmiş veriler.
- Kod Dosyaları (Notebook'lar): Bahsedilen iki farklı teknik yaklaşımı barındıran temel kod dosyalarımız. Her iki dosyada da Keşifçi Veri Analizi (EDA), veri hazırlığı, model eğitimi ve tahmin adımları kendi yöntemlerine uygun olarak ayrı ayrı işlenmiştir.

## Çalıştırma Hakkında Önemli Not

Modellerin eğitim aşaması (özellikle AutoGluon kullanımı ve çapraz doğrulama adımları) yüksek işlem gücü gerektirmekte ve oldukça uzun sürebilmektedir. Dosya boyutlarını makul tutmak ve tarayıcı üzerinde kodların daha rahat incelenebilmesini sağlamak amacıyla, notebook dosyalarındaki hücre çıktılarını temizleyerek repository'ye yükledik.

Kodların akışı tamamen eksiksizdir. İşlemleri kendi ortamınızda test etmek veya sonuçları yeniden üretmek isterseniz notebook dosyalarını baştan çalıştırabilirsiniz. Ancak eğitim sürecinin kullandığınız donanım kapasitesine bağlı olarak ciddi zaman alabileceğini dikkate almanızı öneririz.

Ayrıca yarışma sürecinin tamamlanmasının ardından, **Private Leaderboard'da ilk 10 içerisinde yer almamız durumunda**, notebook dosyalarını tüm hücre çıktıları ve eğitim loglarıyla birlikte güncelleyerek repository'ye tekrar yükleyeceğiz.
