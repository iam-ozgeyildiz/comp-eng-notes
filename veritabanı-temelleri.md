# VERİTABANINA GİRİŞ

> 📌 **Bilgilendirme:** Bu doküman, Mehmet Çelebioğlu'nun BTK Akademi *Veritabanına Giriş* kursundan hareketle oluşturulmuştur. Veritabanları hakkında temel bilgileri içerir.

**Veritabanı;** yapısal veriler topluluğudur. Erişilebilir, yönetilebilir, güncellenebilir, taşınabilir ve birbirleri ile ilişkiler tanımlanabilir veriler kümesidir.

---

### İÇERİK
* Giriş
* Temel Kavramlar
* Veri Tabanı Türleri
* Genel Veri Tipleri
* Veri Tabanı Tasarımı ve Normalizasyon

---

## 1. TEMEL KAVRAMLAR

### 1.1. Veri, Bilgi, Yorumlanmış Bilgi

#### 1.1.1. Veri (Data) Nedir?
Ham gerçeklerden, resim ve rakamlardan oluşan birer koleksiyondur.
* Evrendeki varlıklarla ilgili gerçeklerden oluşur; işlenmemiş, yorumlanmamış ve değerlendirilmemiştir.
* Veriler tek başına bir şey ifade etmezler, varlıkların özelliklerinden ibaretlerdir.
* Veriler dosyalarda veya veritabanlarında saklanabilir. *(Information ve Knowledge veritabanlarında saklanamaz.)*
* **Örnek:** `30`, `-7`, `kg`, `g`, `cm`, `m`, `ali`, `ayşe` ...

#### 1.1.2. Bilgi (Information) Nedir?
Bilgi; verilerin yorumlanmaya uygun biçimde sunulmasıdır. Veriler, programlar ve sorgular aracılığıyla bilgiye dönüştürülür.
* Bilgi, dosyalarda veya veritabanlarında saklanamaz.
* **Örnek 1:** `Yaş: 30` (30 verisine bir değer katarak bilgiye dönüştürdük.)
* **Örnek 2:** `Hava Durumu: -7 derece`
* **Örnek 3:** `10 kg portakal`

#### 1.1.3. Yorumlanmış Bilgi (Knowledge) Nedir?
Yorumlanan verilere dayalı olarak uygun eylemlere ilişkin bilgilerdir. Bir sonuç elde edilir.
* Dosya veya veritabanlarında saklanamaz.
* **Örnek 1:** Yaş 30 -> Artık orta yaş grubuna girmek üzereyim.
* **Örnek 2 (Information vs. Knowledge):**
  * *Information:* Hava -7 derece.
  * *Knowledge:* Sıkı giyinmeliyim.
* **Örnek 3 (Information vs. Knowledge):**
  * *Information:* Ankara - İstanbul arası 500 km'dir.
  * *Knowledge:* Ortalama 100 km hızla gidersem 5 saatte ulaşırım.

> 💡 **Information ve Knowledge Farkı:** Information, bir konunun gerçekleri veya ayrıntılarıdır. Knowledge ise deneyim veya eğitim yoluyla elde ettiğimiz farkındalık, anlayış veya becerilerdir.

---

### 1.2. Veri Tabanı Yönetim Sistemi Nedir?

#### 1.2.1. Database (Veritabanı) Nedir?
Verileri saklamak ve saklanan verilere erişim sağlanıp güncellenebilen her ortam veritabanıdır. Bu ortamlar elektronik olabilir veya olmayabilir.
* Database, disk üzerinde verilerin belirli bir hiyerarşi ile depolandığı dosyalardan oluşur.
* Depolanan verileri yönetecek bir mekanizmaya ihtiyaç vardır. Bu mekanizma olmadan depolanan bu verilerin herhangi bir fonksiyonu yoktur. Bu mekanizma **Database Management System**'dır.

#### 1.2.2. Database Management System (DBMS) Nedir?
Bir veritabanı oluşturmak ve yönetmek için kullanılan programlar koleksiyonudur.
**Görevleri:**
* **Veritabanı Tanımlamak:** (Define - Create)
* **Veritabanı Yapılandırmak:** (Construct - Alter, Grant)
* **Veritabanı Sorgulamak:** (Query - Select)
* **Veritabanı Manipüle Etmek:** (Manipulate - Insert, Update, Delete)

Uygulamalar ve kullanıcılar, diskler üzerindeki verilere doğrudan erişemezler. Buradaki verileri yöneten yönetim sistemine bağlanarak ilgili işlemler gerçekleştirilir.

---

### 1.3. Veri Tabanı Temel İçerikleri
Tüm veritabanları dört temel içerikten oluşur:

**1. User Data (Kullanıcı Verisi):** Kullanıcılar tarafından veritabanına işlenen verilerdir. Kullanıcılar tarafından değiştirilebilir, silinebilir, yenileri oluşturulabilir.

**2. Meta Data (Data Dictionary / Veri Sözlüğü):** Veri hakkında veri (data about data) demektir.
* Dosyaların, tabloların ve tablo alanlarının yapısını içerir (tanımları, index yapıları, data type'ları, size'ları vb.).
* Veri işleme ve sorgulama işlemlerinde görüntüleme ve biçimlendirme kurallarının bulunduğu yerdir. Güvenlik ve erişim kuralları, tetikleyiciler, operasyonel kurallar ve veritabanının kendisiyle ilgili (lisans, ram, disk, mimari vs.) hepsi metadata verileridir.
* ⚠️ **ÖNEMLİ:** Metadata kullanıcılar tarafından doğrudan güncellenemez, oluşturulamaz veya silinemez. Veritabanı tanımı ve nesneleri üzerinde yapısal değişiklikler yapıldığında veya güvenlik/erişim kurallarında güncelleme yapıldığında metadata otomatik olarak oluşup güncellenir.

**3. Access Engine (DBMS Interfaces):** Pek çok alt bilgiden oluşur.
* Bağımsız sorgu dili ve arayüzlerinden oluşmaktadır. Her veritabanında bir sorgulama dili ve bir arayüz vardır. (Örn: Relational database'de SQL ortak dildir.)
* Programlama dilleriyle DML (Data Manipulation Language) gerçekleştirmek için programcı arayüzleri (insert, update, delete vb.):
  * Ön derleyiciler
  * Procedure ve API servis tanımlayıcılar
* Kullanıcı dostu arayüzler (Menü tabanlı, grafik tabanlı arayüzler).

**4. Tools & Utilities (Araçlar ve Yardımcı Programlar):**
Görevleri şunlardır:
* Harici bir ortamdan verilerin veritabanına yüklenmesi (Load Data)
* Veritabanının periyodik olarak yedeklenmesi / yedekten dönülmesi (Backup & Recovery)
* Veritabanı bozulmalarına karşı otomatik yedekleme ve yedekten dönülmesi (Archive & Restore)
* Veritabanı dosya yapılarının yeniden düzenlenmesi ve versiyon yükseltmesi (Upgrade)
* Rapor oluşturma yardımcı programları
* Performans izleme yardımcı programları

> *(Bu araçların veritabanlarında isimleri/syntax'ları fark etse bile görevleri aynıdır. Genellikle otomatik olarak kurulurlar, harici durumlarda manuel yükleme gerekir.)*

---

### Veritabanı Kullanımının Avantajları ve Dezavantajları

**Avantajları:**
1. Veri tekrarını engeller.
2. Verimlilik ve etkililik sağlar.
3. Veri bütünlüğünü korur. *(PK = Primary Key, FK = Foreign Key)*
4. Gizlilik ve güvenlik sağlar.
5. Yedekleme ve yedekten dönme imkanı sunar.

**Dezavantajları:**
* Veritabanı büyüdükçe daha çok karmaşıklaşır.
* Arıza ve felaket anında olumsuz etkiler yaratabilir.
* Çok maliyetlidir.

> 💡 Yanlış veritabanı seçimi maliyeti arttıracaktır, aynı zamanda seçilen veritabanı doğru yapılandırılmalıdır. (Aşağıdaki soruların en azından 3-4 tanesine cevabımız "evet" ise veritabanı kullanılmalıdır.)

---

## 2. VERİ TABANI TÜRLERİ

