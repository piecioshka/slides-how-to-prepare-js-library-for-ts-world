class: middle, slide-front-page, slide-invert-colors

# Jak przygotować bibliotekę<br/>napisaną w <mark>JavaScript</mark>,<br/>na potrzeby projektu<br/>napisanego w <samp>TypeScript</samp>?

<img src="images/my-logo/logo-piecioshka-white-text.svg" />

---

Jesteś autorem biblioteki w npm? Myślisz o stworzeniu takiej? Jeśli tak,
to powinieneś pomyśleć o projektach napisanych w TypeScript, w których
warto zadbać o odpowiednie DefinitelyTyped, tak aby edytory wiedziały,
jak wygląda API Twojego liba. Podczas tej prelekcji dowiesz się, co to jest
DefinitelyTyped, jak je zbudować dla swojej biblioteki.

---

```ts
import { EventEmitter } from "super-event-emitter";

class CartService extends EventEmitter {

    addProduct(product: Product) {
        this.emit('new-product', { product });
    }

}
```

Could not find a declaration file for module 'super-event-emitter'. '/Users/piecioshka/projects-workshops/workshop-typescript-shop/node_modules/super-event-emitter/dist/super-event-emitter.js' implicitly has an 'any' type.
  Try `npm install @types/super-event-emitter` if it exists or add a new declaration (.d.ts) file containing `declare module 'super-event-emitter';`

---

jak się eksportuje obiekt z funkcjami, a jak zwykła funkcje


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
