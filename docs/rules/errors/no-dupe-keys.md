<!--
 generated docs file, do not edit by hand, see xtask/docgen 
-->
# no-dupe-keys

Disallow duplicate keys in object literals.

Object literals allow keys to be declared multiple times, however this causes unwanted
behavior by shadowing the first declaration.

## Invalid Code Examples

```js
let foo = {
    bar: 1,
    baz: 2,
    bar: 3
}
```

<details>
 <summary> More incorrect examples </summary>

```js
let foo = {
    bar,
    baz,
    get bar() {

    }
}
```

```js
let foo = {
    get bar() {

    },
    set bar(foo)  {

    }
}
```
</details><br>
<details>
 <summary> More correct examples </summary>

```js
let foo = {
    bar: {
        bar: {},
        baz: 5
    },
    baz: {}
}
```
</details>

[Source](https://github.com/RDambrosio016/RSLint/tree/master/crates/rslint_core/src/groups/errors/no_dupe_keys.rs)