# 📋 KANBAN — Trainer Ataoglu Geliştirme Süreci

Bu belge, uygulamanın Kanban metodolojisiyle geliştirme geçmişini ve kart tanımlarını içerir.

---

## ✅ KART 1 — Proje İskeleti & iPad UI/UX
**Durum:** TAMAMLANDI

- iPad Air 13" (2732×2048 → 1366×1024 CSS px) grid layout
- TopBar / Sidebar / Main / BottomBar yapısı
- Koyu altın tema, Playfair Display + DM Mono tipografi
- Scan-line texture, animasyonlu loading ekranı
- Toast bildirim sistemi

**DoD:** ✅ Overflow yok, iPad çözünürlüğünde kayma yok

---

## ✅ KART 2 — Web MIDI API & Kawai CX102
**Durum:** TAMAMLANDI

- `navigator.requestMIDIAccess()` ile cihaz taraması
- noteOn / noteOff / velocity ayrıştırma
- Hot-plug desteği
- Renk değiştiren bağlantı göstergesi (Kırmızı/Sarı/Yeşil)
- Debug LOG paneli (son 40 MIDI eventi)

**DoD:** ✅ MIDI no ve nota adı console'a yazılıyor

---

## ✅ KART 3 — Ses Sentezleyicisi (Tone.js)
**Durum:** TAMAMLANDI

- Salamander Grand Piano sampler (CDN üzerinden)
- BPM'e duyarlı `playSequence()` fonksiyonu
- Play / Pause / Stop / Reset transport
- Otomatik AudioContext başlatma (kullanıcı etkileşimi sonrası)

**DoD:** ✅ Play butonuyla doğru frekans ve zamanlama

---

## ✅ KART 4 — Notasyon & İçerik Veritabanı
**Durum:** TAMAMLANDI

- VexFlow 4.2.2 entegrasyonu
- Treble + Bass clef desteği
- Diyez/bemol (Accidental) desteği
- JSON veritabanı yapısı (50 parçaya ölçeklenebilir)
- 3 parça: Ode to Joy, Twinkle, Minuet in G
- 3 egzersiz: C Gam, Beş Parmak, Kırık Akor

**DoD:** ✅ JSON → VexFlow hatasız çizim

---

## ✅ KART 5 — Core Trainer Loop
**Durum:** TAMAMLANDI

- Beklenen nota mavi renk
- Doğru tuş → yeşil, sonraki notaya geç, ses çal
- Yanlış tuş → kırmızı titreşim, bekle
- Doğru/Yanlış/İsabet istatistikleri
- Progress bar

**DoD:** ✅ MIDI eşleşme akışı sorunsuz çalışıyor

---

## 🗺️ Backlog (Gelecek Kartlar)

| # | Kart | Öncelik |
|---|------|---------|
| 6 | 50 parçanın tamamını ekleme | Yüksek |
| 7 | localStorage ile ilerleme kaydı | Orta |
| 8 | MusicXML / MIDI dosyası import | Orta |
| 9 | Metronom görsel göstergesi | Düşük |
| 10 | PWA / offline destek | Düşük |
