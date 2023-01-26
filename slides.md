class: slide-front-page

.logo[
![](./images/warsawjs/logo.svg)
]
.details[
![](images/piotr-kowalski.jpg)
## Piotr Kowalski
## <em>"Jak przygotować paczkę do projektu w <del>TypeScript</del>" [PL]</em>
## <small>2019-09-11</small>
## <a href="https://www.linkedin.com/in/piecioshka">linkedin.com/in/piecioshka</a>
]

---

class: center, slide-background-red, slide-thanks

# Dziękuję ❤️

<iframe src="/test-get-user-media/"></iframe>

---

class: middle, slide-invert-colors
background-image: url(images/me.jpg)
background-size: contain

# O mnie

<del>Q</del> <i>Czy tworzyłeś software używając języka TypeScript?</i>

---

class: slide-columns-3, list-unstyled, list-circled, slide-background-green
background-image: url(images/for-slides/IMG_0648.jpg)
background-size: cover

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

.text-center[
<del>Q</del> <i>Czy jesteś autorem biblioteki w npm?</i>
]

---

class: slide-background-purple, slide-grid, slide-grid-2-columns, slide-grid-with-apla
background-image: url(images/for-slides/IMG_0540.jpg)
background-size: cover

### Scenariusze

.grid-board.size35[

`1` <del>Brak</del> definicji typów

`2` Definicje typów <em>są dostarczone</em> razem z kompilatorem (`tsc`)

`3` Biblioteka <mark>nie jest dostarczana</mark> z definicjami typów, ale można
je zainstalować osobno

`4` Biblioteka <var>jest dostarczana</var> z wbudowanymi własnymi definicjami typów

]

---

class: middle, slide-background-blue
background-image: url(images/for-slides/IMG_0861-winter.jpg)
background-size: cover

# DefinitelyTyped

Repozytorium dla _Type Definitions_.

<del>Q</del> <i>Czy ktoś słyszał o DT?</i>

---

class: slide-background-blue
background-image: url(images/for-slides/IMG_0861-winter.jpg)
background-size: cover

### Type Definitions

.size40[

* Definiujemy _sygnatury_ oraz _strukturę_ obiektów
* Nie definiujemy wartości
* Od TypeScript v2.0 bez _typings_
* _index.d.ts_
    + Domyślnie
    + _package.json_ » _types_

]

.text-center[
<del>Q</del> <i>Czy ktoś używał "typings"?</i>
]

---

class: slide-background-blue
background-image: url(images/for-slides/IMG_0861-winter.jpg)
background-size: cover

### Type Definitions _Przykład_

.size25[

```ts
type Handler = (payload?: any) => void;

declare module "super-event-emitter" {

  export class EventEmitter {
    on(name: string, fn: Handler, context?: any): EventEmitter;
    once(name: string, fn: Handler, context?: any): EventEmitter;
    off(name?: string, fn?: Handler): EventEmitter;
    emit(name: string, params?: any): EventEmitter;

    static mixin(target: T): T;
    static VERSION: string;
  }

  export default EventEmitter;
}
```

]

---

class: middle, slide-background-blue
background-image: url(images/for-slides/IMG_0861-winter.jpg)
background-size: cover

### Automatyzacja

.size40[

* `@types/NAZWA_PAKIETU`
* [types-publisher](https://github.com/Microsoft/types-publisher)
* [TypeSearch](http://microsoft.github.io/TypeSearch/)

]

.text-center[
<del>Q</del> <i>Z jakich edytorów korzystacie?</i>
]

---

class: middle, center, no-display-my-logo, slide-invert-colors
background-image: url(images/for-slides/IMG_0704.jpg)
background-size: cover

## <mark>CommonJS Modules</mark> vs <mark>ECMAScript Modules</mark>

---

class: slide-invert-colors
background-image: url(images/for-slides/IMG_0704.jpg)
background-size: cover

### <mark>CommonJS Modules</mark> definition

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

class: slide-invert-colors
background-image: url(images/for-slides/IMG_0704.jpg)
background-size: cover

### <mark>ECMAScript Modules</mark> definition

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

class: middle, slide-invert-colors

# DEMO ✨ #1

* [super-event-emitter](https://www.npmjs.com/package/super-event-emitter)
* [4.1.10 vs 4.1.12](https://github.com/piecioshka/super-event-emitter/compare/d8ca0847e0d2bb4add01571030eba933bb1d1cde..a41667e5b312fceafb10612aabd9dff12ac713d2)

---

class: slide-background-green
background-image: url(images/for-slides/IMG_0757.jpg)
background-size: cover

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

class: slide-background-purple
background-image: url(images/for-slides/IMG_0772.jpg)
background-size: cover

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
background-image: url(images/for-slides/IMG_0772.jpg)
background-size: cover

### CommonJS, Obiekt

.half-width.left.p-1.size25[

```ts
// my-cookie/index.ts
const Cookie = {
    cook() {
        // ...
    }
};

module.exports = Cookie;
```

]

.half-width.left.p-1.size25[

```ts
// my-cookie/index.d.ts
declare module "my-cookie" {
    namespace Cookie {
        cook: () => void;
    }

    export = Cookie;
}
```

]

---

class: slide-background-purple
background-image: url(images/for-slides/IMG_0772.jpg)
background-size: cover

### ESM, Funkcja

.half-width.left.p-1.size25[

```ts
// my-cookie/index.ts
export function cook() {
    // ...
}
```

]

.half-width.left.p-1.size25[

```ts
// my-cookie/index.d.ts
export function cook(): void;

                                //
```

]

---

class: center
background-color: #e9ebee

<img
    style="width: 700px;"
    src="./images/screenshots/fb.png"
    />

---

class: middle, slide-background-blue
background-image: url(images/for-slides/IMG_0861-winter.jpg)
background-size: cover

## **Generowanie _Type Definitions_**

.size50[

```bash
tsc --declaration index.ts
```

]

---

class: middle, slide-invert-colors

# DEMO ✨ #2

---

class: middle, slide-background-blue
background-image: url(images/for-slides/IMG_0861-winter.jpg)
background-size: cover

# Module Augmentation

---

class: middle, slide-invert-colors

# DEMO ✨ #3

---

class: middle, center, slide-invert-colors, no-display-my-logo

# <del>Dziękuję!</del>

<img
    src="images/my-logo/logo-piecioshka-white-text.svg"
    alt=""
    style="width: 500px"
/>

.size30[
» [facebook.com/piecioshka.dev](https://facebook.com/piecioshka.dev) «
]

---

class: slide-invert-colors, no-display-my-logo
background-image: url(images/with-team.jpg)
background-size: cover

# Thanks<br/><del>Team</del>

---

class: slide-invert-colors, no-display-my-logo
background-image: url(images/with-rob.jpg)
background-size: cover

# Thanks<br/><em>Rob</em>
