# ✂️ YTcutter Kurulum Rehberi

> **📢 ÖNEMLİ: Test ve Paylaşım**
>
> Bu aracı kurup ilk videonuzu kestikten sonra, sistemin sorunsuz çalıştığını doğrulamak için editinizi (YouTube veya benzeri bir platforma yükleyerek) lütfen **[r/eightborn_next](https://www.reddit.com/r/eightborn_next/)** subreddit’inde paylaşın.

---

Bu rehber, **yt-dlp** ve **FFmpeg** kullanarak videoları verimli bir şekilde indirmek ve belirli bölümlerini kesmek için yerel bir ortamın nasıl kurulacağını adım adım açıklar.

---

## 📂 Çalışma Alanı Kurulumu

> **Not:** Yol (PATH) sorunlarını önlemek için tüm araçlar C: sürücüsü altında tek bir klasörde toplanacaktır.

1. Komut satırını açın (`cmd.exe`).

2. Aşağıdaki komutlarla çalışma alanını oluşturun:

```cmd
mkdir C:\YTcutter
cd C:\YTcutter
```

---

## 🛠️ Kurulum Adımları

### 1️⃣ YT-DLP Kurulumu

`yt-dlp`, YouTube ve benzeri platformlardan video indirmek için kullanılan bir komut satırı aracıdır.

- GitHub üzerinden **yt-dlp.exe** dosyasını indirin.
- İndirdiğiniz **yt-dlp.exe** dosyasını `C:\YTcutter` klasörüne taşıyın.
- Kurulumu doğrulayın:

```cmd
yt-dlp
```

> Kullanım bilgileri ekrana gelmelidir.  
> Eğer `command not found` hatası alırsanız dosyanın doğru klasörde olduğundan emin olun.

---

### 2️⃣ FFmpeg Kurulumu

`FFmpeg`, indirilen videoları kesmek ve işlemek için kullanılır.

- FFmpeg’in Windows sürümünü indirin.
- Arşivi açın ve yalnızca `bin/ffmpeg.exe` dosyasını çıkartın.
- `ffmpeg.exe` dosyasını `C:\YTcutter` klasörüne kopyalayın.
- Kurulumu test edin:

```cmd
ffmpeg
```

> FFmpeg yapılandırma çıktıları görünmelidir.

---

## 🚀 Kullanım Rehberi

Kurulum tamamlandıktan sonra aşağıdaki komut ile videonun belirli bir bölümünü indirebilirsiniz.

### Temel Komut Yapısı

```cmd
yt-dlp "YOUTUBE_LINKI" --download-sections "*BASLANGIC_SURESI-BITIS_SURESI"
```

### Parametreler

| Argüman            | Açıklama                     | Örnek                  |
|--------------------|------------------------------|------------------------|
| YOUTUBE_LINKI      | Videonun tam bağlantısı       | https://youtu.be/...   |
| BASLANGIC_SURESI   | Klip başlangıç zamanı         | 10:00                  |
| BITIS_SURESI       | Klip bitiş zamanı             | 10:30                  |

### Örnek

```cmd
yt-dlp "https://www.youtube.com/watch?v=dQw4w9WgXcQ" --download-sections "*10:00-10:30"
```

> **İpucu:** Süreden önceki `*` işareti zorunludur.

---

## 📁 Klasör Yapısı

Kurulum tamamlandığında klasör yapısı şu şekilde olmalıdır:

```text
C:\YTcutter\
│
├── yt-dlp.exe
├── ffmpeg.exe
└── (İndirilen videolar)
```

---

## 🌐 Topluluk Katkısı

Verdiğimiz bilgiler işinize yaradıysa, tek isteğimiz;  
sizin gibi yetenekli editörlerin hazırladığı editleri bu subreddit’te de paylaşmanızdır.

Böylece:

- Yayıncılar editleri RP’den önce hızlıca izleyebilir
- Edit süreçleri kolaylaşır
- Topluluk birlikte büyür

👉 https://www.reddit.com/r/eightborn_next/

**Keyifli editlemeler 🚀**
