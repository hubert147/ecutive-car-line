# Image Generation Guide — Replicate

Ten plik zawiera **8 promptów** do wygenerowania na Replicate (FLUX 1.1 Pro lub FLUX Schnell), które pasują 1:1 do opisów w `index.html`.

## Dlaczego nowe obrazki?

Obecna wersja używa zdjęć z oryginalnej strony executivecarline.co.uk, ale część z nich nie pasuje do nowych opisów sekcji:

| Sekcja w `index.html` | Obecne zdjęcie | Co faktycznie przedstawia | Status |
|---|---|---|---|
| Hero "Discover Scotland" | `f15dcb35` | Forth Bridge nad wodą | OK — ikoniczne |
| Service: Airport Transfers | `b5224978/l250` | Domek z czerwonymi ławkami | **MISMATCH** |
| Service: Hourly Chauffeur | `89544277` | Szofer z tabliczką na lotnisku | **MISMATCH** (to jest airport, nie hourly) |
| Service: Multi-Day Tours | `ff458c03` | Górski krajobraz | OK |
| Gallery: Highland landscapes | `785626f6` | Mercedes pod hotelem | **MISMATCH** |
| Gallery: Edinburgh icons | `b5224978/l0` | Edynburski widok | OK |
| Gallery: St Andrews | `ec7d4389` | mała foto, nieczytelna | **MISMATCH** |
| Gallery: Castles & culture | `7127a516` | kwiaty (prawdop. ślubne) | **MISMATCH** |
| Gallery: The Borders | `89544277` | Szofer (już użyty wyżej) | **MISMATCH** (duplikat) |

## Jak użyć Replicate

1. Wejdź na [replicate.com](https://replicate.com) → zaloguj (GitHub login)
2. Otwórz model **[black-forest-labs/flux-1.1-pro](https://replicate.com/black-forest-labs/flux-1.1-pro)** (najlepsza jakość, ~$0.04/obrazek) lub **[flux-schnell](https://replicate.com/black-forest-labs/flux-schnell)** (szybkie i tańsze, ~$0.003/obrazek)
3. Wklej prompt z poniższej listy
4. Ustaw **aspect_ratio** zgodnie z poniższą tabelą
5. Kliknij **Run** → poczekaj ~10-30s → **Download**
6. Zapisz pod nazwą podaną w sekcji "Filename"
7. Wrzuć do folderu `images/` w projekcie

## 8 promptów

### 1. Hero — `images/hero.jpg`
**Aspect ratio:** `16:9` (lub `21:9` dla bardziej cinematic)
**Prompt:**
```
Cinematic dramatic photograph of a luxury black Mercedes S-Class chauffeur car parked on a winding Scottish Highland road at golden hour, misty mountains and heather fields in the background, dramatic moody sky with soft golden light breaking through clouds, ultra realistic, professional automotive photography, shallow depth of field, atmospheric, premium luxury feel, 8k
```

### 2. Service: Airport Transfers — `images/service-airport.jpg`
**Aspect ratio:** `1:1`
**Prompt:**
```
Professional uniformed chauffeur in dark suit holding a sign at modern airport arrivals hall, polished marble floors, soft warm interior lighting, traveler greeting scene, cinematic professional photography, premium luxury service feeling, high end, sharp focus on chauffeur, blurred background, realistic, magazine quality
```

### 3. Service: Hourly Chauffeur — `images/service-hourly.jpg`
**Aspect ratio:** `1:1`
**Prompt:**
```
Elegant black luxury sedan parked outside historic Edinburgh townhouse on a cobblestone street, well-dressed chauffeur in suit opening rear door, evening blue hour lighting with warm amber streetlamp glow, sophisticated atmosphere, professional event photography, sharp detail, premium chauffeur service, cinematic
```

### 4. Service: Multi-Day Tours — `images/service-tours.jpg`
**Aspect ratio:** `1:1`
**Prompt:**
```
Stunning panoramic Scottish Highlands landscape with luxury Range Rover or black Mercedes V-Class on a scenic single-track road, dramatic Glen Coe-style mountains, cinematic morning mist, vast wilderness, premium tour vibe, professional landscape photography, golden hour lighting, ultra detailed, photorealistic, 8k
```

### 5. Gallery: Highland landscapes — `images/gallery-highlands.jpg`
**Aspect ratio:** `4:3` (this is the BIG hero tile in gallery)
**Prompt:**
```
Breathtaking Scottish Highlands panorama, Glen Coe valley with dramatic mountains, atmospheric mist rising over heather covered hills, lone road winding through wilderness, golden morning light, cinematic landscape photography, ultra realistic, deep moody color grading, no people, photorealistic, 8k professional travel photography
```

### 6. Gallery: Edinburgh icons — `images/gallery-edinburgh.jpg`
**Aspect ratio:** `16:9`
**Prompt:**
```
Iconic Edinburgh cityscape at dusk, Edinburgh Castle silhouette on volcanic rock, historic gothic architecture, warm street lights glowing in old town, dramatic sky with subtle clouds, blue hour cinematic photography, professional travel photography, ultra detailed, atmospheric, photorealistic, 8k
```

### 7. Gallery: St Andrews — `images/gallery-standrews.jpg`
**Aspect ratio:** `1:1`
**Prompt:**
```
St Andrews famous golf course at golden hour, the iconic Swilcan Bridge over green fairway, view towards historic clubhouse and St Andrews coastline, soft sunset light, premium travel photography, no people, cinematic, ultra detailed photorealistic, 8k professional landscape
```

### 8. Gallery: Castles & culture — `images/gallery-castles.jpg`
**Aspect ratio:** `1:1`
**Prompt:**
```
Majestic ancient Scottish castle on rugged cliff over loch at sunrise, Eilean Donan style fortress, mist over water, dramatic mountain backdrop, atmospheric morning light, cinematic travel photography, ultra realistic, photorealistic, premium aesthetic, 8k professional
```

### 9. Gallery: The Borders — `images/gallery-borders.jpg`
**Aspect ratio:** `4:3`
**Prompt:**
```
Rolling green hills of Scottish Borders countryside, picturesque sheep pastures, ancient stone abbey ruins in distance, winding country road, soft afternoon light, lush emerald valleys, professional landscape photography, ultra detailed, photorealistic, peaceful pastoral scene, 8k
```

## Po wygenerowaniu

Wrzuć wszystkie pliki do nowego folderu:

```
executive-car-line/
├── index.html
├── README.md
├── IMAGES.md
└── images/             ← stwórz ten folder
    ├── hero.jpg
    ├── service-airport.jpg
    ├── service-hourly.jpg
    ├── service-tours.jpg
    ├── gallery-highlands.jpg
    ├── gallery-edinburgh.jpg
    ├── gallery-standrews.jpg
    ├── gallery-castles.jpg
    └── gallery-borders.jpg
```

Daj znać kiedy będą gotowe — podmienię URL-e w `index.html` na te lokalne (`images/hero.jpg` itd.) jednym ruchem. Wystarczy że napiszesz "obrazki gotowe" i ścieżkę.

## Tip — kontrola kosztów

- **flux-schnell**: ~$0.003 × 9 obrazków = **~$0.03** (3 grosze za cały komplet)
- **flux-1.1-pro**: ~$0.04 × 9 = **~$0.36** (lepsza jakość, foto-realizm)

Rekomenduję **flux-1.1-pro** dla hero + 3 service'y (4 najważniejsze), a **flux-schnell** dla 5 mniejszych galeryjnych. Łączny koszt: ~$0.18.
