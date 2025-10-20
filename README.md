# 🎓 WordPress Plugin Development – Video Popup Projekt (9-trins forløb)

Et komplet undervisningsforløb, hvor du lærer at bygge et **WordPress-plugin** fra bunden.  
Du henter et færdigt plugin fra GitHub, duplikerer det, og udvider det trin for trin med tekst, video, styling, skrifttyper, ikoner og JavaScript.

Når du er færdig, har du dit eget plugin:  
🎬 **Video Popup – NG Wild Edition**

---

## 🗂️ Overblik – Mappestruktur for det færdige plugin

```plaintext
video-popup-ngw/
│
├── index.php
│
├── css/
│   └── style.css
│
├── js/
│   └── script.js   ← starter som tom fil (opbygges i opgave 8–10)
│
└── video/
    ├── ng_wild.mp4
    └── poster.jpg


```

## 🧩 Opgave 1 – Hent, duplikér og overfør dit plugin

### 🎯 Mål  
Lær at hente et plugin fra GitHub, omdøbe det, redigere `index.php` og overføre det til din WordPress-installation via **FileZilla Client**.

---

#### 🔹 Trin 1 – Download fra GitHub
1. Gå til 👉 [https://github.com/muratkilic1978/video-popup-form-exercise](https://github.com/muratkilic1978/video-popup-form-exercise)
2. Klik **“Code → Download ZIP”**
3. Find ZIP-filen i din **Overførsler / Downloads**-mappe  
4. **Udpak ZIP-filen**
   - Mac: dobbeltklik ZIP-filen  
   - Windows: højreklik → *Udpak alle…*

📁 Den udpakkede mappe hedder: **video-popup-form**


---

#### 🔹 Trin 2 – Duplikér og omdøb
1. Omdøb nu mappen `video-popup-form` -> **video-popup-ngw**.


---

#### 🔹 Trin 3 – Redigér `index.php`
1. Find meta tekst afsnittet øverst i `index.php`
2. Redigere den eksisterende meta tekst i `index.php` så den er identisk med nedenstående meta tekst.
##### a) Plugin-header
```php
/*
 * Plugin Name: Video Popup – NG Wild Edition
 * Plugin URI: http://localhost
 * Description: Popup med video og CTA — undervisningsversion til NG Wild.
 * Version: 1.0.1
 * Author: DIT NAVN
 * Author URI: http://localhost
 * License: GPL2
 */
```

#### 🔹 Trin 4 – Opdater `add_shortcode` navnet
1. Find linjen `add_shortcode` i `index.php`
2. Opdater `add_shortcode` navnet til `'show_video_popup_ngw'`
3. Når du er færdig skal resultatet se sådan ud:
 ##### b) Shortcode
```php
add_shortcode('show_video_popup_ngw', 'video_popup_form');
```

#### 🔹 Trin 5 – Overfør til WordPress

1. Åbn FileZilla Client
2. Forbind til din WordPress websted
3. Gå til mappen:
`/wp-content/plugins/`
4. Træk video-popup-ngw-mappen over fra din computer

#### 🔹 Trin 6 – Aktivér plugin’et i WordPress

1. Gå til Dashboard → Plugins → Installerede plugins
2. Aktivér Video Popup – NG Wild Edition
3. Tilføj shortcoden på enten en side eller et indlæg i WordPress:
```php
[show_video_popup_ngw]
```
4. Tjek at popup’en vises

### 🔹 Opgave 2 – Overskrift og brødtekst
1. Gå til Dashboard → Plugins → Installerede plugins
2. Deaktivér Video Popup – NG Wild Edition
3. Åben nu `index.php` filen
4. Find overskriften `h4` med id `attributten` **promotion-header-title** i `index.php` og opdater teksten med denne - `Oplev naturens vilde side`:
5. Find `span` med id `attributten` **promotion-subheader-title** i `index.php` og opdater teksten med denne - `Dyk ned i naturens mest fascinerende øjeblikke fra hele verden. Se klip fra National Geographic Wild og få et sjældent indblik i dyrenes adfærd.`
6. Gå til Dashboard → Plugins → Installerede plugins
7. Aktivér Video Popup – NG Wild Edition
8. Opdater siden hvor du tidligere indsatte shortcoden 
```php
[show_video_popup_ngw]
```
9. Tjek om de nye opdateringer er slået igennem

### 🔹Opgave 3 – Tilføj ny video
1. Gå til Dashboard → Plugins → Installerede plugins
2. Deaktivér Video Popup – NG Wild Edition
3. Åben nu `index.php` filen
4. Find `video`-elementet og opdater `height` til `270px` og `width` til `480px` - Når du er færdig skal resultatet se sådan ud:
```PHP
$content .= '<video id="video-container" width="480" height="270" muted loop autoplay controls>';
```
5. Find `source`-elementet og attributten `src` og opdater video kilden - så den peger på `video\ng_wild.mp4.` - Når du er færdig skal resultatet se sådan ud:
```PHP
$content .= '<source src="'.plugins_url('video-popup-ngw/video/ng_wild.mp4').'" type="video/mp4">';
```
6. Gå til Dashboard → Plugins → Installerede plugins
7. Aktivér Video Popup – NG Wild Edition
8. Opdater siden hvor du tidligere indsatte shortcoden 
```php
[show_video_popup_ngw]
```
9. Tjek om de nye opdateringer er slået igennem

### 🔹Opgave 4 – Ændr CTA-tekst og farver
1. Gå til Dashboard → Plugins → Installerede plugins
2. Deaktivér Video Popup – NG Wild Edition
3. Åben nu `index.php` filen
4. Find `button`-elementet og opdater teksten med  `Se flere vilde klip` 
5. Åben filen `style.css` inde i mappen `css`
6. Find selektoren `button.btn.btn-primary.btn-lg.active` og opdater egenskaberne og værdier så de er identisk med nedenstående:
```css
button.btn.btn-primary.btn-lg.active {
  background-color: #FFC107;  /* varm gul */
  border-color: #FFC107;
  color: #000;                /* god kontrast */
  width: 400px;
  height: 40px;
  font-size: medium;
}
```
7. Find selektoren `button.btn.btn-primary.btn-lg.active:hover` og opdater egenskaberne og værdier så de er identisk med nedenstående:
```css
button.btn.btn-primary.btn-lg.active:hover {
  background-color: #FFB300;  /* mørkere gul ved hover */
  color: #1c2130;
  transition: 0.3s;
}
```
8. Gå til Dashboard → Plugins → Installerede plugins
9. Aktivér Video Popup – NG Wild Edition
10. Opdater siden hvor du tidligere indsatte shortcoden 
```php
[show_video_popup_ngw]
```
11. Tjek om de nye opdateringer er slået igennem

### 🔹Opgave 5 – Tilføj Roboto-font
1. Gå til Dashboard → Plugins → Installerede plugins
2. Deaktivér Video Popup – NG Wild Edition
3. Åben nu `index.php` filen
4. Find funktionen `function register_plugin_assets()` og placer cursoren i mellem de 2 krøllede parenteser
5. Tilføj et nyt link til Google Font Roboto via `wp_enqueue_style()`. Forneden er vist hvordan det gøres: 
```php
function register_plugin_assets() {
  wp_enqueue_style('CustomStylesheet', plugins_url('video-popup-ngw/css/style.css'));
  /* Herunder tilføjes Roboto-fonten */
  wp_enqueue_style('RobotoFont','https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');
  wp_enqueue_script('CustomScript', plugins_url('video-popup-ngw/js/script.js'), array(), '1.0', true);
}
```
6. Åben filen `style.css` inde i mappen `css`
7. Lav en ny selektor øverst i `style.css` filen med navnet `body, #popup-container`
8. Indsæt nedenstående egenskaber og værdier så de er identisk med følgende:
```css
{ font-family: 'Roboto', sans-serif; }
```
8. Gå til Dashboard → Plugins → Installerede plugins
9. Aktivér Video Popup – NG Wild Edition
10. Opdater siden hvor du tidligere indsatte shortcoden 
```php
[show_video_popup_ngw]
```
11. Tjek om de nye opdateringer er slået igennem

### 🔹Opgave 6 – Tilføj coverbillede (poster.jpg)
1. Gå til Dashboard → Plugins → Installerede plugins
2. Deaktivér Video Popup – NG Wild Edition
3. Åben nu `index.php` filen
4. Find `video`-elementet og indsæt attributten `poster` lige efter attributten `controls` 
5. Sæt `poster` attributtens source til at pege billedet - `video\poster.jpg` - Husk at du skal bruge `plugins_url()` til at pege på `wp-comtent\plugins` mappen. Her er den korrekte PHP-kode:
```PHP
$content .= '<video id="video-container" width="480" height="270" muted loop autoplay controls poster="'.plugins_url('video-popup-ngw/video/poster.jpg').'">';
```

6. Gå til Dashboard → Plugins → Installerede plugins
7. Aktivér Video Popup – NG Wild Edition
8. Opdater siden hvor du tidligere indsatte shortcoden 
```php
[show_video_popup_ngw]
```
9. Tjek om de nye opdateringer er slået igennem

### 🔹Opgave 7 – Lav en funktion der muter videoen med vanilla javascript

1. Gå til Dashboard → Plugins → Installerede plugins
2. Deaktivér Video Popup – NG Wild Edition
3. Redigere den blanke fil `script.js` i mappen **js/**
4. Indtast nedenstående javascript kode:

```js
// Venter på at HTML'en er klar, før koden kører
document.addEventListener("DOMContentLoaded", () => {

  // Herinde skal al vores kode skrives
});
```
**Forklaring:**
WordPress og browseren kan indlæse filer i forskellig rækkefølge.
Ved at bruge DOMContentLoaded sikrer vi, at alle HTML-elementer findes, før vi prøver at "fange" dem.

 5. Find HTML-elementerne i koden (DOM) med `document.querySelector` eller med `document.getElementById` ved at indtaste nedenstående javascript kode:
```js
document.addEventListener("DOMContentLoaded", () => {
  const closeBtn = document.querySelector(".popupCloseButton"); // X-knappen
  const popup = document.getElementById("popup-container");     // hele boksen
  const video = document.getElementById("video-container");     // videoelementet
  const ctaBtn = document.getElementById("newUrl");             // CTA-knappen
});

```
**Forklaring:**
Vi laver “håndtag” til vores elementer, så vi kan styre dem senere (fx klikke på dem, skjule dem, pause video osv.).

6. Tilføj en ny funktion med navnet `function muteVideo()`, hvis fornemmeste opgave er at mute videoen. Indtast denne javascript kode. 
```js
document.addEventListener("DOMContentLoaded", () => {
  const closeBtn = document.querySelector(".popupCloseButton");
  const popup = document.getElementById("popup-container");
  const video = document.getElementById("video-container");
  const ctaBtn = document.getElementById("newUrl");

  // Funktion der muter og pauser videoen
  function muteVideo(){
    if (video) {
      video.muted = true;
      video.pause(); // Stopper videoen midlertidigt
    }
  }
});

```
**Forklaring**
Det er god UX at pause/mute videoen, når brugeren lukker eller forlader popup’en.
Sådan undgår vi, at lyden fortsætter i baggrunden.

7. Gå til Dashboard → Plugins → Installerede plugins
8. Aktivér Video Popup – NG Wild Edition
9. Opdater siden hvor du tidligere indsatte shortcoden 
```php
[show_video_popup_ngw]
```
10. Tjek om de nye opdateringer er slået igennem

### 🔹Opgave 8. Åben et nyt faneblad (National Geographic TV) når man klikker på knappen

1. Gå til Dashboard → Plugins → Installerede plugins
2. Deaktivér Video Popup – NG Wild Edition
3. Redigere den blanke fil `script.js` i mappen **js/**
4. Tilføj en `addEventListener`til knappen `ctaBtn`som åbner url'en - `https://www.natgeotv.com/dk`. Skriv denne js-kode under `muteVideo()` funktionen inde i din DOMContentLoaded-blok:

```js

document.addEventListener("DOMContentLoaded", () => {
  const closeBtn = document.querySelector(".popupCloseButton");
  const popup = document.getElementById("popup-container");
  const video = document.getElementById("video-container");
  const ctaBtn = document.getElementById("newUrl");

  // Funktion der muter og pauser videoen
  function muteVideo(){
    if (video) {
      video.muted = true;
      video.pause(); // Stopper videoen midlertidigt
    }
  }
  // Når der klikkes på knappen
  ctaBtn.addEventListener("click", function() {
    // Åbn NatGeo TV i nyt faneblad
    window.open("https://www.natgeotv.com/dk", "_blank", "noopener");
    // Mute og pause videoen bagefter ved at kalde på muteVideo() funktionen
    muteVideo();
  });

 });

```
**Forklaring:**
- `window.open()` åbner en ny fane med det valgte link.
- `_blank` betyder “nyt faneblad”,
- `"noopener"` beskytter mod, at det nye vindue kan få adgang til din side (sikkerhed).
- `muteVideo()` kaldes til sidst for at dæmpe og pause videoen.

5. Gå til Dashboard → Plugins → Installerede plugins
6. Aktivér Video Popup – NG Wild Edition
7. Opdater siden hvor du tidligere indsatte shortcoden 
```php
[show_video_popup_ngw]
```
8. Tjek om de nye opdateringer er slået igennem

### 🔹Opgave 9. Klik på X-ikonet i hjørnet, så popup-vinduet forsvinder

1. Gå til Dashboard → Plugins → Installerede plugins
2. Deaktivér Video Popup – NG Wild Edition
3. Redigere den blanke fil `script.js` i mappen **js/**
4. Tilføj en `addEventListener`til knappen `closeBtn`som lukker popup-vinduet. Skriv denne js-kode efter den forrige `addEventListener` - inde i din DOMContentLoaded-blok:

```js

document.addEventListener("DOMContentLoaded", () => {
  const closeBtn = document.querySelector(".popupCloseButton");
  const popup = document.getElementById("popup-container");
  const video = document.getElementById("video-container");
  const ctaBtn = document.getElementById("newUrl");

  // Funktion der muter og pauser videoen
  function muteVideo(){
    if (video) {
      video.muted = true;
      video.pause(); // Stopper videoen midlertidigt
    }
  }
  // Når der klikkes på knappen
  ctaBtn.addEventListener("click", function() {
    // Åbn NatGeo TV i nyt faneblad
    window.open("https://www.natgeotv.com/dk", "_blank", "noopener");
    // Mute og pause videoen bagefter ved at kalde på muteVideo() funktionen
    muteVideo();
  });

  // Når der klikkes på X-knappen
  closeBtn.addEventListener("click", () => {
    // Skjul popup’en
    popup.style.display = 'none';

    // Mute og pause videoen
    muteVideo();
  });

});

```

**Forklaring:**
- popup.style.display = 'none'; skjuler hele boksen (samme som “display: none;” i CSS).
- Derefter kalder vi muteVideo(); for at undgå, at lyden kører videre.

5. Gå til Dashboard → Plugins → Installerede plugins
6. Aktivér Video Popup – NG Wild Edition
7. Opdater siden hvor du tidligere indsatte shortcoden 
```php
[show_video_popup_ngw]
```
8. Tjek om de nye opdateringer er slået igennem