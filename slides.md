class: middle, slide-invert-colors

# slides-how-to-fix-library-for-ts-world

## Subtitle

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
Proszę o rekomendację:
[fb.com/piecioshka.trener](https://fb.com/piecioshka.trener)
]
