# Auto škola Aster — sajt (dizajn prototip)

## Pregled
Reprezentativni jednostranični (one-page) sajt za auto školu **„Aster"**, napravljen kao portfolio primer. Sadrži: hero sekciju, „O nama", prednosti, obuku, kategorije, cenovnik, utiske korisnika (sa Google recenzije dugmetom), galeriju sa slajderom i lightbox zumom, i kontakt sa formom i mapom.

> **Napomena:** Svi podaci (naziv, adresa, telefoni, email, cene) su **izmišljeni** za potrebe portfolija.

## O fajlovima u paketu
Fajlovi su **dizajn referenca napravljena u HTML-u** — prototip koji pokazuje željeni izgled i ponašanje, a ne produkcioni kod za direktno kopiranje. Zadatak je **rekreirati ovaj dizajn u postojećem okruženju ciljnog koda** (React, Vue, Svelte, običan HTML/CSS…) koristeći njegove ustaljene obrasce, ili, ako okruženje ne postoji, izabrati odgovarajući framework i implementirati dizajn u njemu.

Glavni fajl `Auto skola Aster.dc.html` je autorski napisan kao „Design Component" i oslanja se na `support.js` runtime. Za produkciju se markup i inline stilovi mogu prevesti u standardni HTML/CSS ili komponente — struktura i stilovi su čitljivi direktno iz fajla.

## Fidelity
**High-fidelity (hifi)** — finalne boje, tipografija, razmaci i interakcije. UI treba rekreirati verno.

## Sekcije
1. **Hero (#pocetna)** — dvokolonski grid: levo naslov + CTA dugmad + telefon; desno fotografija vozila/instruktora u zaobljenom okviru sa „badge" karticom. Tamna pozadina (`#10275e → #2b56c9` gradijent).
2. **O nama (#o-nama)** — tekst o školi + fotografija (aerial vozni park) sa narandžastom statistikom.
3. **Prednosti (#prednosti)** — mreža kartica sa ikonom/naslovom/opisom.
4. **Obuka (#obuka)** — 3 kartice (teorijska/praktična/ispit).
5. **Kategorije (#kategorije)** — kartice B, C, CE, D + CTA kartica. (Bez emoji ikonica.)
6. **Cenovnik (#cenovnik)** — 3 kartice cena.
7. **Utisci (#utisci)** — istaknuta velika recenzija na tamnoj kartici sa agregatnim statistikama + dve kompaktne recenzije; dugme „Pogledajte recenzije na Google-u".
8. **Galerija (#galerija)** — horizontalni slajder u jednom redu (scroll-snap) sa strelicama; klik na sliku otvara lightbox sa zumom.
9. **Kontakt (#kontakt)** — kontakt podaci + forma + Google mapa (iframe).
10. **Footer** — logo, navigacija, društvene mreže.

## Interakcije i ponašanje
- **Mobilni meni:** hamburger dugme toggluje `.vj-mobmenu` (state `menuOpen`).
- **Galerija slajder:** strelice `galPrev`/`galNext` skroluju track za širinu ćelije (`scrollBy`, smooth). CSS scroll-snap centrira ćelije.
- **Lightbox:** klik na ćeliju (`openLb`) čita `<img>` iz ćelije i prikazuje uvećanu sliku u overlayu (`.vj-lb.show`); zatvara se klikom na pozadinu, ✕ dugme (`closeLb`). Blokira scroll body-ja dok je otvoren.
- **Kontakt forma:** `onSubmit` sprečava default i postavlja `sent=true` (prikaz potvrde).
- **Scroll-reveal:** IntersectionObserver fade-in + translateY na karticama (osim galerije).
- **Hover:** kartice dobijaju box-shadow; slike u galeriji `scale(1.08)`; dugmad `translateY(-2px)`.

## Design tokens
**Boje**
- Primarno plava: `#2b56c9`, tamna: `#10275e` / `#16213e`, svetlija: `#3a6be0`
- Akcenat narandžasta: `#ff7a1a` (hover `#ff9142`), tamni tekst na narandžastoj: `#3d1a00`
- Neutralne pozadine: `#f6f8fc`, `#eef2fa`, `#eaf0fb`, `#e9effc`
- Tekst: `#1a2238` (osnovni), `#3c4766` / `#4e5878` / `#5c6788` (sekundarni)
- Ivice: `#dde3ef`, `#cdd4e2`, `#cfdcf7`

**Tipografija**
- Naslovi: **Archivo** (700–900), negativan letter-spacing (-.02em)
- Telo: **Figtree** (400–700)
- H1 hero 60px/1.02; H2 sekcije 40px/1.08; telo 16–20px/1.5–1.62

**Radijusi:** 10–12px (badge/dugmad manja), 16–22px (kartice/slike), 999px (pilule/CTA)
**Senke:** kartice `0 10–14px 26–34px rgba(16,39,94,.1–.12)`; dugmad `0 8px 22–24px rgba(...)`

## Assets
Sve slike su u `assets/` (izvor: korisnički upload / Pexels / AI-generisano):
- `aster-hero.png` — vozilo „ASTER" + instruktor i kandidat (hero)
- `aster-parking-aerial.jpg` — vozni park iz vazduha (O nama)
- `aster-drive-city.png` — vozilo u vožnji ispred grada (galerija)
- `aster-parking-night.jpg` — vozila noću (galerija)
- `aster-classroom.jpg` — učionica (galerija)
- `aster-driving-pov.jpg` — čas vožnje, POV (galerija)

Fontovi: Google Fonts (Archivo, Figtree) preko `<link>`.
Mapa: Google Maps embed iframe.

## Fajlovi
- `Auto skola Aster.dc.html` — kompletan dizajn (markup + inline stilovi + logika)
- `support.js` — runtime za Design Component (potreban da se `.dc.html` otvori u browseru)
- `assets/` — sve fotografije
