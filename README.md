# 🎹 Trainer Ataoglu

**iPad Air 13" için optimize edilmiş, Bluetooth MIDI destekli HTML5 piyano eğitim uygulaması.**

---

## 🖼️ Özellikler

- 🎵 **VexFlow** ile gerçek zamanlı nota görselleştirme (Treble + Bass clef)
- 🎹 **Web MIDI API** ile Kawai CX102 (ve tüm Bluetooth MIDI cihazları) entegrasyonu
- 🔊 **Tone.js** Salamander Grand Piano sampler ile yüksek kaliteli ses
- 🎓 **5 Eğitim Seviyesi** — Başlangıçtan ileri düzeye
- 🎼 **50 Parça kapasiteli** JSON veritabanı (3 parça + 3 egzersiz ile başlar)
- ✅ **Gerçek zamanlı doğrulama** — Doğru/yanlış nota geri bildirimi
- 📱 **iPad Air 13" (2732×2048)** ekranına tam optimize

---

## 🚀 Kurulum

### Seçenek 1 — Direkt Aç (Önerilen)

```bash
git clone https://github.com/KULLANICI_ADIN/trainer-ataoglu.git
cd trainer-ataoglu
```

`index.html` dosyasını **Safari** (iPad) veya **Chrome** (masaüstü) ile açın.

> ⚠️ Web MIDI API için HTTPS veya `localhost` gereklidir. Aşağıdaki local server seçeneğini kullanın.

### Seçenek 2 — Local HTTPS Server

```bash
# Python ile basit server
python3 -m http.server 8080

# Sonra tarayıcıda: http://localhost:8080
```

### Seçenek 3 — GitHub Pages

1. Repo → **Settings** → **Pages**
2. Source: `main` branch, `/ (root)`
3. `https://KULLANICI_ADIN.github.io/trainer-ataoglu` adresinden erişin

---

## 🎹 Kullanım

### MIDI Bağlantısı

1. Kawai CX102'yi iPad'e Bluetooth ile bağlayın
2. Uygulamada sağ üstteki **"MIDI Bağlantısı Yok"** butonuna tıklayın
3. Tarayıcı izin isterse **İzin Ver**'e tıklayın
4. Gösterge yeşile döndüğünde bağlantı kurulmuştur

### Eğitmen Modu

- Sol menüden seviye veya parça seçin
- Mavi renkli nota → o an basmanız gereken tuş
- Doğru tuş: **yeşil** ✅ → sonraki notaya geçer
- Yanlış tuş: **kırmızı** ❌ → doğru tuşa basana kadar bekler

### Dinleme Modu

- Alt barda **DİNLE** modunu seçin
- **▶ Play** ile parçayı dinleyin, BPM kaydırıcısıyla hızı ayarlayın

---

## 📁 Dosya Yapısı

```
trainer-ataoglu/
├── index.html          # Tek dosya uygulama (HTML + CSS + JS)
├── README.md
├── LICENSE
├── .gitignore
└── docs/
    └── KANBAN.md       # Proje geliştirme süreci dokümantasyonu
```

---

## 🗄️ Parça Veritabanına Yeni Parça Ekleme

`index.html` içindeki `DB.repertoire` dizisine JSON formatında ekleyin:

```js
{
  id: "fur_elise",
  title: "Für Elise",
  composer: "L. van Beethoven",
  level: 3,
  category: ["top50", "classics"],
  timeSignature: { beats: 3, noteValue: 8 },
  bpm: 120,
  treble: [
    { keys: ["e/5"],  duration: "8" },
    { keys: ["eb/5"], duration: "8" },
    { keys: ["e/5"],  duration: "8" },
    // ...devamı
  ],
  bass: [
    // sol el notaları (opsiyonel)
  ]
}
```

### VexFlow Nota Formatı

| Format | Anlamı |
|--------|--------|
| `"c/4"` | Do, 4. oktav (Middle C) |
| `"eb/5"` | Mi bemol, 5. oktav |
| `"f#/3"` | Fa diyez, 3. oktav |

| Duration | Anlamı |
|----------|--------|
| `"w"` | Tam nota |
| `"h"` | Yarım nota |
| `"q"` | Dörtlük |
| `"8"` | Sekizlik |
| `"16"` | Onaltılık |
| `"qd"` | Noktalı dörtlük |

---

## 🛠️ Teknoloji Yığını

| Kütüphane | Versiyon | Kullanım |
|-----------|----------|----------|
| [VexFlow](https://www.vexflow.com/) | 4.2.2 | Nota görselleştirme |
| [Tone.js](https://tonejs.github.io/) | 14.8.49 | Ses sentezi / playback |
| Web MIDI API | Native | MIDI cihaz iletişimi |
| Vanilla JS (ES6+) | — | Uygulama mantığı |
| CSS3 | — | Responsive UI |

---

## 🌐 Tarayıcı Desteği

| Tarayıcı | Web MIDI | Ses |
|----------|----------|-----|
| Chrome (masaüstü) | ✅ | ✅ |
| Safari (iPad) | ✅* | ✅ |
| Firefox | ❌ | ✅ |
| Edge | ✅ | ✅ |

> *Safari Web MIDI desteği iOS 16.4+ ile gelmiştir. Bluetooth MIDI için Web MIDI Browser uygulaması önerilebilir.

---

## 🗺️ Yol Haritası

- [ ] 50 parçanın tamamı eklenmesi
- [ ] İlerleme kaydı (localStorage)
- [ ] Metronom görsel göstergesi
- [ ] Parça yükleme (MusicXML / MIDI dosyası import)
- [ ] Çok kullanıcı profili
- [ ] PWA desteği (offline çalışma)

---

## 📄 Lisans

MIT License — Özgürce kullanabilir, değiştirebilir ve dağıtabilirsiniz.
