class: slide-front-page

.logo[
![](./images/warsawjs/logo.svg)
]
.details[
![](images/piotr-kowalski.jpg)
## Piotr Kowalski
## <em>"Jak przygotować bibliotekę<br/>do projektu w <samp>TypeScript</samp>" [PL]</em>
## <small>2019-09-11</small>
## <a href="https://www.linkedin.com/in/piecioshka">linkedin.com/in/piecioshka</a>
]

---

class: middle, slide-invert-colors, slide-fullscreen-background
background-image: url(images/me.jpg)

# O mnie

???

* Zawodowo od 2008
* 300+ repozytoriów na `GitHub`
* 30+ paczek w rejestrze `npm`

---

class: slide-columns-3, list-unstyled, list-circled

### npm packages (=37)

.size20[

* vanilla-javascript
* eslint-config-piecioshka
* export-eslint-config
* **[complete-string](https://github.com/piecioshka/complete-string)**
* underscore.assert
* underscore.slice
* underscore-methods-usage-statistics
* is-url-umd
* super-event-emitter
* **[html5-video-error-translator](https://github.com/piecioshka/html5-video-error-translator)**
* gamepad-api
* shower-gamepad
* **[executor-editor](https://github.com/piecioshka/executor-editor)**
* debug-umd
* **[node-slice](https://github.com/piecioshka/node-slice)**
* **[is-letter](https://github.com/piecioshka/is-letter)**
* wooden-ladder
* pokemon-picker
* encoding-checker
* github-track-followers
* less-compile-file
* boilerplate-babel-webpack
* create-ts-project
* move-master
* **[mobile-keyboard-translator](https://github.com/piecioshka/mobile-keyboard-translator)**
* makiwara
* find-emails-in-string-cli
* xhr-sniffer
* **[simple-data-table](https://github.com/piecioshka/simple-data-table)**
* xpath-to-css-template-string-tag
* react-bounty
* slider-before-after
* solidarity-nodejs
* solidarity-builder
* github-contribution-stats-cli
* find-google-docs-in-string
* brute-force-generator

]

---

class: slide-background-red

### Pytania do publiczności

* Czy jesteś autorem biblioteki w npm?
* Czy myślisz o stworzeniu takiej biblioteki?
* Czy pisałeś kiedyś w TypeScript?
* Z jakich edytorów korzystacie?

---

class: slide-background-purple

### 4 scenariusze

.size40[

* Brak definicji typów
* Definicje typów są dostarczone razem z kompilatorem (tsc)
* Biblioteka nie jest dostarczana z definicjami typów, ale można je zainstalować osobno
* Biblioteka jest dostarczana z wbudowanymi własnymi definicjami typów

]

---

class: middle, slide-background-blue

# _CommonJS_ vs _ES Module_

---

### Module definition: _CommonJS_

.size30[

```js
// Plik: main.js
const videos = require('./video-list');
console.log(videos.length); // 3
```

```js
// Plik: video-list.js
module.exports = [
    { title: 'Rocky', url: '' },
    { title: 'Terminator', url: '' },
    { title: 'Rambo', url: '' },
];
```

]

---

### Module definition: _ECMAScript Modules_

.size30[

```js
// Plik: main.js
import videos from './video-list';
console.log(videos.length); // 3
```

```js
// Plik: video-list.js
export default [
    { title: 'Rocky', url: '' },
    { title: 'Terminator', url: '' },
    { title: 'Rambo', url: '' },
];
```

]

---

class: middle, slide-background-blue

# DefinitelyTyped

Repozytorium dla _Type Definitions_.

---

class: slide-background-blue

### Type Definitions

* od TypeScript v2.0 bez `typings`
* Nie definiujemy wartości
* Strategie:
    + Obok każdego pliku
    + Jeden opisujący API
* Domyślnie: `index.d.ts`
* `package.json` — Klucz `types`
* "Automatyczny" `@types/NAZWA_PAKIETU`

---

class: middle, slide-background-blue

# types-publisher

<https://github.com/Microsoft/types-publisher>

---

class: middle, slide-background-blue

# TypeSearch

<http://microsoft.github.io/TypeSearch/>

---

class: middle, slide-invert-colors

# DEMO ✨ .size50[super-event-emitter @ 4.1.10]

<https://www.npmjs.com/package/super-event-emitter>

???

* <https://github.com/piecioshka/demo-how-to-prepare-js-library-for-ts-world>
* <https://github.com/piecioshka/super-event-emitter/compare/d8ca0847e0d2bb4add01571030eba933bb1d1cde..a41667e5b312fceafb10612aabd9dff12ac713d2>

---

class: slide-background-green

### Wnioski

* Zdefiniuj `index.d.ts`
* Gdy eksportujesz moduł to:
    + Zdefiniuje Moduł
    + Eksportuj Klasy
* Wspieraj:
    + `default import`
    + destructuring
* Dodaj `index.d.ts` do plików paczki :)

---

class: middle, slide-invert-colors

# DEMO ✨ .size60[complete-string @ 2.1.2]

<https://www.npmjs.com/package/complete-string>

???

* <https://github.com/piecioshka/demo-how-to-prepare-js-library-for-ts-world>

---

class: slide-background-green

### Wnioski

* Wspieraj:
    + `default import` — nie musisz znać API
* Nie trzeba dodawać `index.d.ts` do `dist/`
    + domyślnie jest brany plik `index.d.ts`
* Dodaj `index.d.ts` do plików paczki :)

---

class: slide-background-purple

### CommonJS, Klasa

.half-width.left.p-1.size25[

```ts
// my-cookie/index.ts
class Cookie {
    cook() {
        // ...
    }
}

module.exports = { Cookie };
```

]

.half-width.left.p-1.size25[

```ts
// my-cookie/index.d.ts
declare module "my-cookie" {
    export class Cookie {
        cook(): void;
    }
}
```

]

---

class: slide-background-purple

### CommonJS, Obiekt

.half-width.left.p-1.size25[

```ts
// my-cookie/index.ts
module.exports = {
    cook() {
        // ...
    }
};
```

]

.half-width.left.p-1.size25[

```ts
// my-cookie/index.d.ts
declare module 'my-cookie' {
    namespace Cookie {
        cook: () => void;
    }
    export = Cookie;
};
```

]

---

class: slide-background-purple

### ESM, Funkcja

.size40[

```ts
// my-cookie/index.ts
export function makeCookie() {
    // ...
}
```

```ts
// my-cookie/index.d.ts
export function makeCookie(): void;
```

]

---

class: middle, slide-background-blue

# Module Augmentation

---

class: center

<img
    style="width: 500px;"
    src="./images/screenshots/fb.png"
    />

---

class: middle, slide-background-blue

## Generowanie _Type Definitions_

.size50[

```bash
tsc --declaration index.ts
```

]

---

class: middle, slide-invert-colors

# DEMO ✨

---

class: middle, center, slide-invert-colors, no-display-my-logo

# <samp>Dziękuję!</samp>

<img
    src="images/my-logo/logo-piecioshka-white-text.svg"
    alt=""
    style="width: 500px"
/>

.size30[
» [fb.com/piecioshka.trener](https://fb.com/piecioshka.trener) «
]
