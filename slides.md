class: middle, slide-front-page, slide-invert-colors

# Jak przygotować bibliotekę<br/>napisaną w <mark>JavaScript</mark>,<br/>na potrzeby projektu<br/>napisanego w <samp>TypeScript</samp>?

<img src="images/my-logo/logo-piecioshka-white-text.svg" />

---

class: middle, slide-invert-colors, slide-fullscreen-background
background-image: url(images/me.jpg)

# O mnie

---

class: slide-background-purple

### Pytania do publiczności

* Czy jesteś autorem biblioteki w npm?
* Czy myślisz o stworzeniu takiej biblioteki?
* Czy pisałeś kiedyś w TypeScript?
* Z jakich edytorów korzystacie?

---

class: slide-background-green

### Program

* Co to jest DefinitelyTyped?
* Jak zbudować definicję typów?
* Jak się eksportuje obiekt z funkcjami, a jak zwykłą funkcje?

---

```ts
import { EventEmitter } from "super-event-emitter";

class CartService extends EventEmitter {

    addProduct(product: Product) {
        this.emit('new-product', { product });
    }

}
```

Could not find a declaration file for module 'super-event-emitter'.

```text
'super-event-emitter/dist/super-event-emitter.js' implicitly has an 'any' type.
Try `npm install @types/super-event-emitter` if it exists or add a new declaration (.d.ts) file containing `declare module 'super-event-emitter';`
```

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
