# Techdoc examples

## Build

### requirements

- ndenv or node v9.3.0
- yarn
- Gitbook version 3.2.3

### initialize

```
$ yarn
$ yarn gitbook install
```

### start local server

```
$ yarn gitbook serve
```

and access `http://localhost:4000`.

### build artifact

```
$ yarn gitbook build . _book/html
$ yarn gitbook pdf . _book/techdoc-example.pdf
```

Output is in `/_book`.
