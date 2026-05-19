Akıllı Tarım Destek Sistemi - Paydaş Analizi ve Temel Gereksinim Raporu
1. Paydaş Analizi ve Beklentiler
Projenin başarısı, sistemi kullanacak olan farklı grupların (paydaşların) ihtiyaçlarının doğru anlaşılmasına bağlıdır. Sistemin temel paydaşları ve beklentileri aşağıda listelenmiştir:

1.1. Çiftçiler (Birincil Son Kullanıcılar)
Profil: Tarla/sera sahibi, genellikle teknik ve yazılım bilgisi sınırlı olan son kullanıcılar.

İhtiyaçlar: Tarlasındaki bitkilerin durumunu karmaşık grafikler yerine net ve basit ifadelerle görmek isterler.

Sistemden Beklentileri:

Son derece basit, Türkçe ve anlaşılır bir kullanıcı arayüzü (mümkünse mobil uyumlu).

Don, aşırı yağış veya hastalık gibi durumlarda önceden SMS veya uygulama içi anlık uyarılar (Push Notification) almak.

"Ne zaman sulamalıyım?", "Hangi gübreyi atmalıyım?" gibi yapay zeka tabanlı doğrudan eylem önerileri.

1.2. Ziraat Mühendisleri ve Danışmanlar (Uzman Kullanıcılar)
Profil: Çiftçilere danışmanlık veren, teknik veriyi okuyup yorumlayabilen uzmanlar.

İhtiyaçlar: Yapay zekanın sunduğu önerilerin arkasındaki teknik verileri (nem oranları, NPK değerleri, sıcaklık geçmişi) detaylı incelemek.

Sistemden Beklentileri:

Sensörlerden veri tabanına (SQL) akan detaylı ve tarihsel verilerin analiz grafikleri.

Yapay zekanın koyduğu bitki sağlığı teşhislerine (görüntü analizleri sonucuna) manuel müdahale edebilme ve doğrulama yetkisi.

1.3. Tarım Kooperatifleri ve Birlikler (Yönetici/Kurumsal Kullanıcılar)
Profil: Bölgedeki çiftçileri yöneten, hasat planlaması yapan kurumlar.

İhtiyaçlar: Bireysel tarlalardan ziyade, bölgesel olarak genel durumu görmek.

Sistemden Beklentileri:

Bölgedeki genel hastalık yayılım haritası (örn: bir tarlada başlayan hastalığın diğerlerine sıçrama riski).

Sistemde toplanan veriler ışığında bölgesel rekolte (hasat miktarı) tahmin raporları.

1.4. Geliştirici Ekip ve Sistem Yöneticileri (Yani Siz)
Profil: Arka planda Java mimarisini, veri tabanını ve AI entegrasyonunu yöneten mühendisler.

Sistemden Beklentileri:

API'lerin ve sensörlerin kesintisiz çalışması.

Kolay bakım yapılabilen, temiz kod standartlarına (GitHub üzerinde düzenli PR'lar ile) uygun sürdürülebilir bir proje mimarisi.

2. Projenin Temel Gereksinimleri (Requirements)
Paydaş analizinden yola çıkarak, projenin başarılı sayılabilmesi için sağlaması gereken temel gereksinimler iki ana başlıkta toplanmıştır:

2.1. İşlevsel Gereksinimler (Functional Requirements)
Sistemin "ne yapması" gerektiği:

Sistem, belirlenen API'lerden hava durumu verisini ve IoT sensör/simülasyonlarından toprak verisini otomatik olarak SQL veri tabanına kaydetmelidir.

Kullanıcı sisteme bitki görseli yükleyebilmeli ve arka plandaki yapay zeka servisi bu görseli analiz edip hastalık tespiti yapabilmelidir.

Sistem, toplanan verileri birleştirerek çiftçiye "Sulama Yap", "İlaçlama Yap" gibi aksiyon bildirimleri üretebilmelidir.

2.2. İşlevsel Olmayan Gereksinimler (Non-Functional Requirements)
Sistemin "nasıl çalışması" gerektiği:

Kullanılabilirlik: Arayüz (özellikle çiftçiler için) maksimum 3 tıklama ile ana verilere ulaşılabilecek sadelikte olmalıdır.

Güvenilirlik ve Hata Toleransı: API veya sensör bağlantıları kopsa bile sistem çökmemeli, son alınan verilerle çalışmaya devam edip hata logları tutmalıdır (Veri toplama tasarım belgesinde tanımlandığı üzere).

Performans: Sistemdeki sorgular, veri tabanı büyüse bile kullanıcıya analiz sonucunu maksimum 3 saniye içinde döndürmelidir.

3. Proje Hedefleri ve Geliştirme Öncelikleri
1. Aşama (Yüksek Öncelik): Temel altyapının kurulması (Hava durumu API'si entegrasyonu, veri tabanı tablolarının oluşturulması, temel veri okuma/yazma işlemleri).

2. Aşama (Orta Öncelik): Yapay zeka karar destek motorunun entegrasyonu (Bitki sağlığı görsel analizi ve kural tabanlı öneri sistemi).

3. Aşama (Düşük Öncelik / İleri Dönem): Ziraat mühendisleri ve kooperatifler için gelişmiş raporlama ve analiz dashboard'larının (panellerinin) kodlanması.
