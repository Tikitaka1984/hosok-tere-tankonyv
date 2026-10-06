# Hősök tere – interaktív tankönyv

Önálló, szerver nélküli webalkalmazás idegenvezető tanulóknak: tankönyvi lapok (EN/HU), gyakorló feladatok, magyar–angol szószedet, idegenvezető-műhely és helyszíni rali (QR-kódos belépéssel). Telepíthető (PWA) és offline is működik.

## Fájlok

| Fájl / mappa | Szerepe |
|---|---|
| `index.html` | maga az alkalmazás (a képek és a tartalom is benne van) |
| `manifest.json` | a telepíthetőséghez (név, ikonok, színek) |
| `sw.js` | offline működés (service worker) |
| `fonts/` | a betűtípusok (SIL Open Font License) |
| `icons/` | alkalmazásikonok |
| `vercel.json` | gyorsítótár-beállítás a Vercelhez |
| `LICENSE-fonts.txt` | a betűtípusok licence |
| `robots.txt` | a keresőmotorok kizárása (az oldal nem kerül a találatok közé) |

## Telepítés (kb. 20–25 perc)

### 1. GitHub-tároló
1. github.com → **New repository**. Név: `hosok-tere-tankonyv`, láthatóság: Public (vagy Private, ha a Vercel-fiók ehhez hozzáfér).
2. A tároló oldalán: **Add file → Upload files**.
3. Húzza be **a csomag teljes tartalmát** (az `index.html`-t és a többi fájlt, a `fonts` és `icons` mappákkal együtt). A mappák megtartják a szerkezetüket.
4. **Commit changes**.

### 2. Vercel
1. vercel.com → **Add New → Project** → válassza ki a `hosok-tere-tankonyv` tárolót → **Import**.
2. Beállítások: **Framework Preset: Other**. A Build Command és az Output Directory maradjon üres.
3. **Deploy**.
4. A projekt nevét (Project Name) érdemes `hosok-tere`-re állítani, így a cím: `https://hosok-tere.vercel.app` (ha foglalt, például `hosok-tere-tk`).

Ezután minden GitHub-módosítás magától újra közzétételre kerül.

## Keresők kizárása és képek

- Az oldal `noindex` jelöléssel, `robots.txt`-szel és `X-Robots-Tag` fejléccel kérik a keresőmotoroktól, hogy ne listázzák. A cím így csak a megosztott hivatkozással (QR-kód) érhető el. Ez nem jelent hozzáférés-védelmet.
- A Hősök emlékköve képe szemléltető ábra (az eredeti fotó eredete nem volt tisztázható). Saját fotóval a `index.html`-ben az `"emlekko"` kép cserélhető; Claude Code ezt elvégzi.
- A lábléc forrásjelzése: a képek tanórai anyagból származnak, oktatási célú használatra.

## Mielőtt a diákok használják

- [ ] **A képek szerzői jogi helyzetének tisztázása.** A képek a tanórai leckéből származnak; nyilvános közzététel előtt ellenőrizze, használhatók-e. Szükség esetén cserélje őket.
- [ ] **A Vercel ingyenes (Hobby) csomagjának feltételei:** ellenőrizze, hogy az iskolai oktatási használat belefér-e. Ha kétséges, ugyanez a csomag GitHub Pageszel is működik (Settings → Pages → a tároló főmappája).
- [ ] **A QR-kódok:** ha a végleges cím eltér a `https://hosok-tere.vercel.app` címtől, a QR-lapot újra kell generálni.
- [ ] **Próba:** vendégként (kijelentkezett böngészőben), mobiladaton nyissa meg a címet, majd olvassa be az 1., 8. és 20. állomás QR-kódját, és próbálja ki repülő üzemmódban is.

## Telepítés a telefonra (diákoknak)

- **Android (Chrome):** menü → *Telepítés* / *Hozzáadás a kezdőképernyőhöz*.
- **iPhone (Safari):** Megosztás → *Főképernyőhöz adás*.

Az offline működéshez egyszer meg kell nyitni az alkalmazást internetkapcsolattal (a gyorsítótár ekkor töltődik fel).

## Frissítés

1. Módosítsa a fájlt (például az `index.html`-t) a GitHubon.
2. **Fontos:** nyissa meg az `sw.js`-t, és növelje a verziószámot: `const V = 'hosok-tere-v1';` → `'hosok-tere-v2'`. Ettől kapják meg a diákok az új változatot (a következő megnyitáskor).

## Adatvédelem

Az alkalmazás nem gyűjt személyes adatot, nincs bejelentkezés, nincs külső kérés (a betűk is a csomagból töltődnek). A haladás (pecsétek, vázlatok, kvízeredmények) kizárólag a diák saját eszközén, a böngészőben tárolódik.

## Közvetlen hivatkozások (QR)

`https://CÍM/#/s/N` – ahol N az állomás sorszáma (1–20). Az állomások sorrendje: 1 oszlop, 2 hét vezér, 3–16 a 14 szobor (Szent Istvántól Kossuth Lajosig), 17 allegorikus alakok, 18 Hősök emlékköve, 19 Műcsarnok, 20 Szépművészeti Múzeum.
