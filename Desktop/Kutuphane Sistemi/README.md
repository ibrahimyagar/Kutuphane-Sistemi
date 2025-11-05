# 📚 Kütüphane Yönetim Sistemi

ASP.NET Core MVC ile geliştirilmiş profesyonel bir kütüphane yönetim sistemi. Bu sistem, kütüphanelerin kitap envanterini, kullanıcı işlemlerini ve kiralama süreçlerini dijitalleştirmek için tasarlanmıştır.

## 🎯 Proje Hakkında

Bu proje, modern web teknolojileri kullanılarak geliştirilmiş bir kütüphane yönetim sistemidir. Sistem, kitap yönetimi, kitap türü yönetimi, kullanıcı kimlik doğrulama ve kiralama işlemlerini içermektedir.

## ✨ Özellikler

### 📖 Kitap Yönetimi
- Kitap ekleme, güncelleme ve silme işlemleri
- Kitap bilgileri (ad, yazar, fiyat, tanım)
- Kitap görsel yükleme desteği
- Kitap türüne göre kategorilendirme

### 🏷️ Kitap Türü Yönetimi
- Kitap türü ekleme ve düzenleme
- Kitap türü listeleme ve silme
- Kategorilere göre filtreleme

### 📋 Kiralama İşlemleri
- Kitap kiralama kayıtları
- Öğrenci-kitap eşleştirmesi
- Kiralama geçmişi takibi

### 🔐 Güvenlik ve Yetkilendirme
- ASP.NET Core Identity ile kullanıcı yönetimi
- Rol tabanlı yetkilendirme (Admin, Öğrenci)
- Güvenli oturum yönetimi

## 🖼️ Ekran Görüntüleri

### Kitaplar Sayfası
![Kitaplar Sayfası](WebUygulamaProje1/images/kitaplar.png)

### Kitap Türleri Sayfası
![Kitap Türleri Sayfası](WebUygulamaProje1/images/kitapTurleri.png)

### Kitap Ekleme Sayfası
![Kitap Ekleme Sayfası](WebUygulamaProje1/images/kitapEkle.png)

### Kitap Kiralama Sayfası
![Kitap Kiralama Sayfası](WebUygulamaProje1/images/kitapKirala.png)

## 🛠️ Teknolojiler

- **ASP.NET Core 7.0** - Web framework
- **Entity Framework Core 7.0** - ORM (Object-Relational Mapping)
- **SQL Server** - Veritabanı
- **ASP.NET Core Identity** - Kimlik doğrulama ve yetkilendirme
- **Bootstrap 5** - Frontend framework
- **jQuery** - JavaScript kütüphanesi
- **Razor Pages** - View engine

## 📦 Proje Yapısı

```
WebUygulamaProje1/
├── Areas/
│   └── Identity/          # Kimlik doğrulama sayfaları
├── Controllers/          # MVC Controller'ları
│   ├── HomeController.cs
│   ├── KitapController.cs
│   ├── KitapTuruController.cs
│   └── KiralamaController.cs
├── Models/               # Veri modelleri
│   ├── Kitap.cs
│   ├── KitapTuru.cs
│   ├── Kiralama.cs
│   └── Repository Pattern Interface'leri
├── Views/                # Razor view dosyaları
├── Migrations/           # Entity Framework migration'ları
├── Utility/              # Yardımcı sınıflar
│   ├── UygulamaDbContext.cs
│   ├── UserRoles.cs
│   └── EmailSender.cs
└── wwwroot/             # Statik dosyalar (CSS, JS, images)
```

## 🚀 Kurulum

### Gereksinimler

- .NET 7.0 SDK veya üzeri
- SQL Server (LocalDB veya SQL Server Express)
- Visual Studio 2022 veya VS Code

### Adımlar

1. **Projeyi klonlayın:**
```bash
git clone https://github.com/ibrahimyagar/Kutuphane-Sistemi.git
cd Kutuphane-Sistemi
```

2. **Proje dizinine gidin:**
```bash
cd WebUygulamaProje1
```

3. **Veritabanı bağlantı stringini düzenleyin:**
   
   `appsettings.json` dosyasını açın ve `DefaultConnection` değerini kendi SQL Server bağlantı bilgilerinizle güncelleyin:
```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=KutuphaneDb;Trusted_Connection=True;MultipleActiveResultSets=true"
  }
}
```

4. **Migration'ları çalıştırın:**
```bash
dotnet ef database update
```

5. **Projeyi çalıştırın:**
```bash
dotnet run
```

6. **Tarayıcıda açın:**
   - Proje varsayılan olarak `https://localhost:5001` veya `http://localhost:5000` adresinde çalışacaktır.

## 👤 Kullanıcı Rolleri

### Admin
- Tüm kitap işlemleri (ekleme, güncelleme, silme)
- Kitap türü yönetimi
- Kiralama işlemleri yönetimi
- Kullanıcı yönetimi

### Öğrenci
- Kitap listesini görüntüleme
- Kiralama işlemleri

## 📝 Veritabanı Yapısı

### KitapTuru Tablosu
- `Id` (Primary Key)
- `Ad` (Kitap türü adı)

### Kitap Tablosu
- `Id` (Primary Key)
- `KitapAdi`
- `Yazar`
- `Tanim` (Açıklama)
- `Fiyat`
- `KitapTuruId` (Foreign Key)
- `ResimUrl`

### Kiralama Tablosu
- `Id` (Primary Key)
- `OgrenciId`
- `KitapId` (Foreign Key)

## 🔧 Geliştirme

### Repository Pattern
Proje, Repository Pattern kullanılarak geliştirilmiştir. Bu sayede:
- Kod tekrarı azalır
- Test edilebilirlik artar
- Veri erişim katmanı soyutlanır

### Dependency Injection
Tüm repository'ler ve servisler Dependency Injection ile yönetilmektedir.

## 📄 Lisans

Bu proje açık kaynak kodludur ve eğitim amaçlı geliştirilmiştir.

## 👨‍💻 Geliştirici

**İbrahim Yağar**

- GitHub: [@ibrahimyagar](https://github.com/ibrahimyagar)

## 🤝 Katkıda Bulunma

Projeye katkıda bulunmak için:
1. Bu repository'yi fork edin
2. Yeni bir branch oluşturun (`git checkout -b feature/yeni-ozellik`)
3. Değişikliklerinizi commit edin (`git commit -am 'Yeni özellik eklendi'`)
4. Branch'inizi push edin (`git push origin feature/yeni-ozellik`)
5. Bir Pull Request oluşturun

---

⭐ Bu projeyi beğendiyseniz yıldız vermeyi unutmayın!
