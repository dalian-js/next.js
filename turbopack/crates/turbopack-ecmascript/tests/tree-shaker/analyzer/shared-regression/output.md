# Items

Count: 11

## Item 1: Stmt 0, `VarDeclarator(0)`

```js
export const order = [];

```

- Declares: `order`
- Write: `order`

## Item 2: Stmt 1, `Normal`

```js
order.push("a");

```

- Side effects
- Reads: `order`
- Write: `order`

## Item 3: Stmt 2, `VarDeclarator(0)`

```js
const random = Math.random();

```

- Side effects
- Declares: `random`
- Write: `random`

## Item 4: Stmt 3, `VarDeclarator(0)`

```js
const shared = {
    random,
    effect: order.push("b")
};

```

- Side effects
- Declares: `shared`
- Reads: `random`, `order`
- Write: `random`, `order`, `shared`

## Item 5: Stmt 4, `Normal`

```js
order.push("c");

```

- Side effects
- Reads: `order`
- Write: `order`

## Item 6: Stmt 5, `VarDeclarator(0)`

```js
export const a = {
    shared,
    a: "aaaaaaaaaaa"
};

```

- Declares: `a`
- Reads: `shared`
- Write: `shared`, `a`

## Item 7: Stmt 6, `VarDeclarator(0)`

```js
export const b = {
    shared,
    b: "bbbbbbbbbbb"
};

```

- Declares: `b`
- Reads: `shared`
- Write: `shared`, `b`

# Phase 1
```mermaid
graph TD
    Item1;
    Item2;
    Item3;
    Item4;
    Item5;
    Item6;
    Item7;
    Item8;
    Item8["ModuleEvaluation"];
    Item9;
    Item9["export order"];
    Item10;
    Item10["export a"];
    Item11;
    Item11["export b"];
```
# Phase 2
```mermaid
graph TD
    Item1;
    Item2;
    Item3;
    Item4;
    Item5;
    Item6;
    Item7;
    Item8;
    Item8["ModuleEvaluation"];
    Item9;
    Item9["export order"];
    Item10;
    Item10["export a"];
    Item11;
    Item11["export b"];
    Item2 --> Item1;
    Item3 --> Item2;
    Item4 --> Item3;
    Item4 --> Item2;
    Item4 --> Item1;
    Item5 --> Item4;
    Item5 --> Item1;
    Item6 --> Item4;
    Item7 --> Item6;
    Item7 --> Item4;
    Item9 --> Item5;
    Item9 --> Item1;
    Item10 --> Item6;
    Item11 --> Item7;
```
# Phase 3
```mermaid
graph TD
    Item1;
    Item2;
    Item3;
    Item4;
    Item5;
    Item6;
    Item7;
    Item8;
    Item8["ModuleEvaluation"];
    Item9;
    Item9["export order"];
    Item10;
    Item10["export a"];
    Item11;
    Item11["export b"];
    Item2 --> Item1;
    Item3 --> Item2;
    Item4 --> Item3;
    Item4 --> Item2;
    Item4 --> Item1;
    Item5 --> Item4;
    Item5 --> Item1;
    Item6 --> Item4;
    Item7 --> Item6;
    Item7 --> Item4;
    Item9 --> Item5;
    Item9 --> Item1;
    Item10 --> Item6;
    Item11 --> Item7;
```
# Phase 4
```mermaid
graph TD
    Item1;
    Item2;
    Item3;
    Item4;
    Item5;
    Item6;
    Item7;
    Item8;
    Item8["ModuleEvaluation"];
    Item9;
    Item9["export order"];
    Item10;
    Item10["export a"];
    Item11;
    Item11["export b"];
    Item2 --> Item1;
    Item3 --> Item2;
    Item4 --> Item3;
    Item4 --> Item2;
    Item4 --> Item1;
    Item5 --> Item4;
    Item5 --> Item1;
    Item6 --> Item4;
    Item7 --> Item6;
    Item7 --> Item4;
    Item9 --> Item5;
    Item9 --> Item1;
    Item10 --> Item6;
    Item11 --> Item7;
    Item8 --> Item5;
```
# Final
```mermaid
graph TD
    N0["Items: [ItemId(ModuleEvaluation)]"];
    N1["Items: [ItemId(Export((&quot;a&quot;, #2), &quot;a&quot;))]"];
    N2["Items: [ItemId(Export((&quot;b&quot;, #2), &quot;b&quot;))]"];
    N3["Items: [ItemId(Export((&quot;order&quot;, #2), &quot;order&quot;))]"];
    N4["Items: [ItemId(0, VarDeclarator(0))]"];
    N5["Items: [ItemId(1, Normal), ItemId(2, VarDeclarator(0)), ItemId(3, VarDeclarator(0))]"];
    N6["Items: [ItemId(4, Normal)]"];
    N7["Items: [ItemId(5, VarDeclarator(0))]"];
    N8["Items: [ItemId(6, VarDeclarator(0))]"];
    N1 --> N7;
    N0 --> N6;
    N2 --> N8;
    N3 --> N4;
    N5 --> N4;
    N6 --> N5;
    N6 --> N4;
    N7 --> N5;
    N8 --> N7;
    N8 --> N5;
    N3 --> N6;
```
# Entrypoints

```
{
    ModuleEvaluation: 0,
    Export(
        "order",
    ): 3,
    Exports: 9,
    Export(
        "b",
    ): 2,
    Export(
        "a",
    ): 1,
}
```


# Modules (dev)
## Part 0
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 6
};
"module evaluation";

```
## Part 1
```js
import { a as a } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: -7
};
export { a };

```
## Part 2
```js
import { b as b } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: -8
};
export { b };

```
## Part 3
```js
import { c as order } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: -4
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 6
};
export { order };

```
## Part 4
```js
const order = [];
export { order as c } from "__TURBOPACK_VAR__" assert {
    __turbopack_var__: true
};

```
## Part 5
```js
import { c as order } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: -4
};
order.push("a");
const random = Math.random();
const shared = {
    random,
    effect: order.push("b")
};
export { random as d } from "__TURBOPACK_VAR__" assert {
    __turbopack_var__: true
};
export { shared as e } from "__TURBOPACK_VAR__" assert {
    __turbopack_var__: true
};

```
## Part 6
```js
import { c as order } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: -4
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 5
};
order.push("c");

```
## Part 7
```js
import { e as shared } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: -5
};
const a = {
    shared,
    a: "aaaaaaaaaaa"
};
export { a as a } from "__TURBOPACK_VAR__" assert {
    __turbopack_var__: true
};

```
## Part 8
```js
import { e as shared } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: -5
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 7
};
const b = {
    shared,
    b: "bbbbbbbbbbb"
};
export { b as b } from "__TURBOPACK_VAR__" assert {
    __turbopack_var__: true
};

```
## Part 9
```js
export { a } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: "export a"
};
export { b } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: "export b"
};
export { order } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: "export order"
};

```
## Merged (module eval)
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 6
};
"module evaluation";

```
# Entrypoints

```
{
    ModuleEvaluation: 0,
    Export(
        "order",
    ): 3,
    Exports: 9,
    Export(
        "b",
    ): 2,
    Export(
        "a",
    ): 1,
}
```


# Modules (prod)
## Part 0
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 6
};
"module evaluation";

```
## Part 1
```js
import { a as a } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: -7
};
export { a };

```
## Part 2
```js
import { b as b } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: -8
};
export { b };

```
## Part 3
```js
import { c as order } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: -4
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 6
};
export { order };

```
## Part 4
```js
const order = [];
export { order as c } from "__TURBOPACK_VAR__" assert {
    __turbopack_var__: true
};

```
## Part 5
```js
import { c as order } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: -4
};
order.push("a");
const random = Math.random();
const shared = {
    random,
    effect: order.push("b")
};
export { random as d } from "__TURBOPACK_VAR__" assert {
    __turbopack_var__: true
};
export { shared as e } from "__TURBOPACK_VAR__" assert {
    __turbopack_var__: true
};

```
## Part 6
```js
import { c as order } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: -4
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 5
};
order.push("c");

```
## Part 7
```js
import { e as shared } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: -5
};
const a = {
    shared,
    a: "aaaaaaaaaaa"
};
export { a as a } from "__TURBOPACK_VAR__" assert {
    __turbopack_var__: true
};

```
## Part 8
```js
import { e as shared } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: -5
};
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 7
};
const b = {
    shared,
    b: "bbbbbbbbbbb"
};
export { b as b } from "__TURBOPACK_VAR__" assert {
    __turbopack_var__: true
};

```
## Part 9
```js
export { a } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: "export a"
};
export { b } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: "export b"
};
export { order } from "__TURBOPACK_PART__" assert {
    __turbopack_part__: "export order"
};

```
## Merged (module eval)
```js
import "__TURBOPACK_PART__" assert {
    __turbopack_part__: 6
};
"module evaluation";

```
