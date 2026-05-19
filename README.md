# 🌳 Aile Ağacı Oluşturucu

Tarayıcıda çalışan, bağımlılıksız, açık kaynak aile ağacı editörü. Tek HTML dosyası — hiçbir kurulum, hesap, internet bağlantısı gerekmez. Tüm veriler tarayıcının `localStorage`'ında saklanır.

![preview](./preview.png)

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
git clone <repo-url>
cd Karmasik_Aile_Agaci
```

Sonra `index.html` dosyasını çift tıkla — tarayıcıda açılır. Hepsi bu.

İlk açılışta otomatik olarak küçük bir örnek aile (Yılmaz ailesi) yüklenir. Sıfırdan başlamak için sağ üstteki 🗑 düğmesine tıkla.

## 🏗 Mimari

Tek HTML dosyası: `index.html`
- **State**: `localStorage` ile kalıcı
- **Layout**: Bottom-up Reingold-Tilford ağaç düzeni
- **Render**: DOM (kişi kartları) + SVG (ilişki çizgileri) + Canvas (PNG export)
- **Bağımlılık**: Sıfır. Ne npm, ne CDN, ne harici font.

### Veri Modeli

```js
state = {
  people:    [{id, name, gender, fam, x, y, dob, dod, dead, photo, desc, ...}],
  unions:    [{id, a, b, type, customLabel}],     // a + b evlilik/partner
  families:  [{id, parents:[id,id?], child, type, customLabel}]
}
```

## 📜 Lisans

MIT — istediğin gibi kullan, fork'la, değiştir.
