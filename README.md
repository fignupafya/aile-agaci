<h3 align="right">
  <a href="#-aile-ağacı-oluşturucu">🇹🇷 Türkçe</a> ·
  <a href="#-family-tree-builder-english">🇬🇧 English</a>
</h3>

# 🌳 Aile Ağacı Oluşturucu

Tarayıcıda çalışan, bağımlılıksız, açık kaynak aile ağacı editörü. Tek HTML dosyası — hiçbir kurulum, hesap, internet bağlantısı gerekmez. Tüm veriler tarayıcının `localStorage`'ında saklanır.

🌐 **Canlı demo**: [https://fignupafya.github.io/aile-agaci/](https://fignupafya.github.io/aile-agaci/)

## ✨ Özellikler

### Veri & Kişi
- 📸 **Fotoğraf yükleme** — dosya seç veya kart üzerine sürükle bırak (otomatik 250×250 JPEG'e küçültülür)
- 💞 **Esnek ilişki türleri** — Evli · Boşanmış · Nikâhsız partner · Eşcinsel partner · **Özel etiket**
- 👨‍👩‍👧 **Esnek ebeveyn-çocuk bağları** — Biyolojik · Evlat edinme · Taşıyıcı annelik · **Özel etiket**
- 📝 Zengin kişi alanları: doğum/ölüm yılı ve yeri, meslek, açıklama, fotoğraf
- ⚠ Tutarsızlık doğrulaması (çocuğun doğumu ebeveynden önce, yaş > 120, vs.)

### Etkileşim
- 🖱 **Drag-to-connect** — kişiyi başka kişiye sürükle, ilişki tipini modal'dan seç
- 🔒 **Shift + sürükle** — tek eksen kilidi (yatay/dikey) ile çizgileri düz tut
- 🖱 **Sağ tık bağlam menüsü** — Düzenle/Sil/+Eş/+Çocuk/+Ebeveyn/Odakla
- ⚡ Üzerine gelince beliren **hızlı + butonları** — ebeveyn/eş/çocuk anında
- 🎯 **Hover odak modu** — kişinin tüm soyağacı parlar, geri kalan soluklaşır
- ✎ **Çift tık** — kişiyi düzenle

### Görünüm
- 🖼 **PNG export** — tüm ağacı 2× retina çözünürlükle indir (Ctrl+E)
- 📐 **Bottom-up otomatik düzen** — Reingold-Tilford tarzı, yapraklardan başlayıp parent'a doğru genişlik hesabı
- 🔍 **Hızlı arama** — isim/meslek/doğum yeri ile autocomplete (Ctrl+F)
- 🗺 **Mini-harita** — sağ üstte, tıkla → o bölgeye uç
- 🔎 **Zoom & Pan** — mouse tekerleği zoom, boş alana tıkla-sürükle pan
- 🎨 9 renk seçeneği + 4 cinsiyet (erkek/kadın/non-binary/belirsiz)
- 🌐 **TR / EN dil desteği** — browser dilini otomatik algılar, seçim kalıcı

### Yönetim
- ↶↷ **Geri al / İleri al** — 50 adıma kadar (Ctrl+Z/Y)
- 💾 **Otomatik kayıt** — her değişiklik anında localStorage'a
- ⬇⬆ **JSON import/export** — yedek ve paylaşım
- 📊 **İstatistikler** — kişi/evlilik/boşanma/vefat/ortalama yaş (Ctrl+I)

## ⌨️ Klavye Kısayolları

| Kısayol | İşlev |
|---|---|
| `Ctrl + N` | Yeni kişi ekle |
| `Ctrl + F` | Ara |
| `Ctrl + Z / Y` | Geri al / İleri al |
| `Ctrl + I` | İstatistikler |
| `Ctrl + E` | PNG olarak indir |
| `Del` | Seçili kişiyi sil |
| `Esc` | Modal kapat / seçimi kaldır |
| `+ / − / 0` | Zoom in / out / sığdır |
| `?` | Yardım |

## 🚀 Kullanım

```
git clone https://github.com/fignupafya/aile-agaci.git
cd aile-agaci
```

Sonra `index.html` dosyasını çift tıkla — tarayıcıda açılır. Hepsi bu.

İlk açılışta otomatik olarak küçük bir örnek aile (Yılmaz ailesi) yüklenir. Sıfırdan başlamak için sağ üstteki 🗑 düğmesine tıkla.

## 🏗 Mimari

Tek HTML dosyası: `index.html`
- **State**: `localStorage` ile kalıcı
- **Layout**: Bottom-up Reingold-Tilford ağaç düzeni
- **Render**: DOM (kişi kartları) + SVG (ilişki çizgileri) + Canvas (PNG export)
- **Pan/Zoom**: CSS transform tabanlı (canvas boyutundan bağımsız, limitsiz)
- **i18n**: Inline `T` tablosu, `data-i18n` attribute'ları + `t(key)` fonksiyonu
- **Bağımlılık**: Sıfır. Ne npm, ne CDN, ne harici font.

### Veri Modeli

```js
state = {
  people:    [{id, name, gender, fam, x, y, dob, dod, dead, photo, desc, ...}],
  unions:    [{id, a, b, type, customLabel}],     // a + b evlilik/partner
  families:  [{id, parents:[id,id?], child, type, customLabel}]
}
```

## 🚢 Deploy

GitHub Pages'a her commit'te otomatik yayınlanıyor (`.github/workflows/pages.yml`). Fork'larsan kendi repository'inde Settings → Pages → Source: GitHub Actions seçince çalışmaya başlar.

## 📜 Lisans

MIT — istediğin gibi kullan, fork'la, değiştir.

---

# 🌳 Family Tree Builder (English)

A browser-based, dependency-free, open-source family tree editor. Single HTML file — no installation, account, or internet required. All data is stored in your browser's `localStorage`.

🌐 **Live demo**: [https://fignupafya.github.io/aile-agaci/](https://fignupafya.github.io/aile-agaci/)

## ✨ Features

### Data & People
- 📸 **Photo upload** — pick a file or drag-and-drop onto a card (auto-resized to 250×250 JPEG)
- 💞 **Flexible relationship types** — Married · Divorced · Unmarried partner · Same-sex partner · **Custom label**
- 👨‍👩‍👧 **Flexible parent-child bonds** — Biological · Adopted · Surrogate · **Custom label**
- 📝 Rich person fields: birth/death year and place, occupation, description, photo
- ⚠ Inconsistency validation (child born before parent, age > 120, etc.)

### Interaction
- 🖱 **Drag-to-connect** — drag a person onto another, pick a relation from the modal
- 🔒 **Shift + drag** — single-axis lock (horizontal/vertical) to keep lines straight
- 🖱 **Right-click context menu** — Edit/Delete/+Spouse/+Child/+Parent/Focus
- ⚡ **Quick + buttons** on hover — parent/spouse/child in one click
- 🎯 **Hover focus mode** — entire lineage highlights, others fade
- ✎ **Double-click** — edit person

### View
- 🖼 **PNG export** — entire tree at 2× retina resolution (Ctrl+E)
- 📐 **Bottom-up auto-layout** — Reingold-Tilford-style, widths computed from leaves up
- 🔍 **Quick search** — autocomplete by name/occupation/birthplace (Ctrl+F)
- 🗺 **Mini-map** — top-right corner, click → fly to that region
- 🔎 **Zoom & Pan** — mouse wheel zooms, click-drag empty area pans
- 🎨 9 color options + 4 genders (male/female/non-binary/unspecified)
- 🌐 **TR / EN language support** — auto-detects browser language, choice persists

### Management
- ↶↷ **Undo / Redo** — up to 50 steps (Ctrl+Z/Y)
- 💾 **Auto-save** — every change to localStorage instantly
- ⬇⬆ **JSON import/export** — backup and sharing
- 📊 **Statistics** — people/marriages/divorces/deaths/avg lifespan (Ctrl+I)

## ⌨️ Keyboard Shortcuts

| Shortcut | Action |
|---|---|
| `Ctrl + N` | New person |
| `Ctrl + F` | Search |
| `Ctrl + Z / Y` | Undo / Redo |
| `Ctrl + I` | Statistics |
| `Ctrl + E` | Download PNG |
| `Del` | Delete selected |
| `Esc` | Close modal / deselect |
| `+ / − / 0` | Zoom in / out / fit |
| `?` | Help |

## 🚀 Usage

```
git clone https://github.com/fignupafya/aile-agaci.git
cd aile-agaci
```

Then double-click `index.html` — opens in your browser. That's all.

On first load, a small example family (Yılmaz family) is loaded automatically. Click the 🗑 button (top-right) to start fresh.

## 🏗 Architecture

Single HTML file: `index.html`
- **State**: persisted via `localStorage`
- **Layout**: Bottom-up Reingold-Tilford tree layout
- **Render**: DOM (person cards) + SVG (relationship lines) + Canvas (PNG export)
- **Pan/Zoom**: CSS transform-based (independent of canvas size, unlimited)
- **i18n**: inline `T` table, `data-i18n` attributes + `t(key)` function
- **Dependencies**: Zero. No npm, no CDN, no external fonts.

### Data Model

```js
state = {
  people:    [{id, name, gender, fam, x, y, dob, dod, dead, photo, desc, ...}],
  unions:    [{id, a, b, type, customLabel}],     // a + b marriage/partnership
  families:  [{id, parents:[id,id?], child, type, customLabel}]
}
```

## 🚢 Deploy

Auto-published to GitHub Pages on every commit (`.github/workflows/pages.yml`). If you fork, go to Settings → Pages → Source: GitHub Actions to enable.

## 📜 License

MIT — use, fork, modify as you like.
