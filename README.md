# ✂️ YTcutter Kurulum Rehberi

---

## 🌐 Topluluk Katkısı

Öğreneceğiniz yöntemlerle hazırlayacağınız o harika içerikleri **[r/eightborn_next](https://www.reddit.com/r/eightborn_next/)** subreddit’inde bağlantı sekmesiyle  paylaşırsanız:

- İzlenmeler doğrudan YouTube (veya ilgili platform) hanenize yansır.
- Yayıncılar editleri sunucuya girmeden önce hızlıca kaydırarak inceleyebilir.
- Editler dağılmadan tek bir platformda toplanır.
- Edit süreçleri hızlanır ve sadeleşir.
- Topluluk birlikte büyür.



👉 https://www.reddit.com/r/eightborn_next/

Şimdi, hazırsanız teknik detaylara geçelim! 🎬

---

Bu rehber, **yt-dlp** ve **FFmpeg** kullanarak videoları verimli bir şekilde indirmek ve belirli bölümlerini kesmek için yerel bir ortamın nasıl kurulacağını adım adım açıklar.

---

## 📂 Çalışma Alanı Kurulumu

> **Not:** Olası sorunlarını önlemek için tüm araçlar C: sürücüsü altında tek bir klasörde toplanacaktır.

1. Komut satırını açın (`cmd.exe`).

2. Aşağıdaki komutlarla çalışma alanını oluşturun:

```cmd
mkdir C:\YTcutter
cd C:\YTcutter
```

---

## 🛠️ Kurulum Adımları

### 1️⃣ YT-DLP Kurulumu

YouTube üzerinden video indirmek için kullanacağınız **[YT-DLP](https://github.com/yt-dlp/yt-dlp#release-files)** aracını indirin.

- İndirdiğiniz dosyayı `C:\YTcutter` klasörüne taşıyın.
- Şimdi konsol pencerenize geri dönün ve şu komutu girin:

```cmd
yt-dlp
```

> Kullanım bilgileri ekrana gelmelidir.  
> Eğer `command not found` hatası alırsanız dosyanın doğru klasörde olduğundan emin olun.

---

### 2️⃣ FFmpeg Kurulumu

İndirilen videoları kesmek, birleştirmek ve işlemek için gerekli olan **[FFMPEG](https://www.gyan.dev/ffmpeg/builds/ffmpeg-release-essentials.zip)** kütüphanesini indirin.

- Arşivi açın ve yalnızca `bin/ffmpeg.exe` dosyasını çıkartın.
- `ffmpeg.exe` dosyasını `C:\YTcutter` klasörüne kopyalayın ve şu komutu girin:

```cmd
ffmpeg
```

> FFmpeg yapılandırma çıktıları görünmelidir.

---

## 🚀 YT-DLP Akıllı Kesit İndirici Rehberi

Bu rehber, YouTube videolarının **yalnızca belirli bir bölümünü** (ör. 6–10 saniyelik bir klip) **en yüksek kalitede ve hatasız** şekilde indirmek için hazırlanmıştır.  
Süreci hızlandırmak adına komutları manuel yazmak yerine **Yapay Zeka (ChatGPT, Gemini vb.)** kullanılır.

> **Ön Hazırlık:**  
> `yt-dlp.exe` ve `ffmpeg.exe` dosyalarının `C:\YTcutter` klasörü içinde bulunduğundan emin olun.

---

## 🟢 1. Aşama: Yapay Zekayı Hazırlama (Prompt)

İndirme komutunu her seferinde elle yazmak yerine, yapay zekanın **standart ve hatasız** komut üretmesi için aşağıdaki **Görev Tanımı** metnini **bir kez** ChatGPT veya Gemini’ye gönderin.

### 📋 Kopyalanacak Metin (Prompt)

```plaintext
Sen bir `yt-dlp` komut satırı oluşturucususun. Görevin, sana vereceğim değişkenleri kullanarak YouTube videolarının belirli bölümlerini indirmeye yarayan komut satırı kodunu hazırlamaktır.

Kullanman gereken temel kod şablonu şudur:
yt-dlp --download-sections "*[BAŞLANGIÇ]-[BİTİŞ]" --force-keyframes-at-cuts "[VIDEO_LINKI]" -o [DOSYA_ADI]

Kurallar:
1. Sana "Zaman Aralığı", "Video Linki" ve "Dosya Adı" verilecek.
2. Bu verileri yukarıdaki şablonda ilgili yerlere yerleştir.
3. Çıktı olarak SADECE kodu ver, başka hiçbir açıklama, giriş veya sonuç cümlesi yazma.
4. Kod bloğu ("```bash") kullan.
```

---

## 🟡 2. Aşama: Video Bilgilerini Girme

Yapay zeka görevi kabul ettikten sonra, indirmek istediğiniz **her yeni video** için aşağıdaki şablonu doldurup gönderin.

> ⚠️ **DİKKAT:**  
> `Zaman Aralığı`, `Video Linki` ve `Dosya Adı` alanlarını mutlaka kendi videonuza göre değiştirin.

### 📋 Kopyalanacak Şablon

```plaintext
Aşağıdaki bilgilere göre yt-dlp kodunu oluştur:

- Zaman Aralığı: 02:21:35-02:21:45
- Video Linki: https://www.youtube.com/watch?v=aPCmVzlCRGo
- Dosya Adı: clip.mp4
```

Yapay zeka size **tek satırlık, çalışmaya hazır** bir komut verecektir.  
Bu kodu kopyalayın ve bir sonraki aşamaya geçin.

---

## 🔴 3. Aşama: İndirmeyi Başlatma (CMD)

Oluşturulan komutu bilgisayarınızda çalıştırmak için:

1. **Windows + R** tuşlarına basın  
2. Açılan pencereye `cmd` yazıp **Enter**’a basın  
3. Araçların bulunduğu klasöre geçin:

```cmd
cd C:\YTcutter
```

4. Yapay zekanın verdiği uzun komutu **yapıştırın** (Sağ tık veya `Ctrl + V`)  
5. **Enter**’a basarak indirmeyi başlatın

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

## 👋 Son Bir Hatırlatma

Paylaşımlarınızı **[r/eightborn_next](https://www.reddit.com/r/eightborn_next/)** subreddit’inde  
**“Bağlantı (Link)”** sekmesini kullanarak yaparsanız hem yayıncılar daha rahat görür hem de izlenmeleriniz artar.

👉 https://www.reddit.com/r/eightborn_next/

**Keyifli editlemeler! 🚀**

---
