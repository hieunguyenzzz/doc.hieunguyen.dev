---
name: Yarn
menu: Javascript
---


# yarn

## what is yarn
bla bla
## workspace

#### package.json

useful when developing module, so requiring workspace-a from a file located in workspace-b will now use the exact code currently located inside your project rather than what is published on npm

```json
{
  "private": true, 
  "workspaces": ["workspace-a", "workspace-b"]
}
```

`private` attribute is required

*workspace-a/package.json:*


```json
{
  "name": "workspace-a",
  "version": "1.0.0",

  "dependencies": {
    "cross-env": "5.0.5"
  }
}
```

*workspace-b/package.json:*

```json
{
  "name": "workspace-b",
  "version": "1.0.0",

  "dependencies": {
    "cross-env": "5.0.5",
    "workspace-a": "1.0.0"
  }
}
```

> Please note the fact that `/workspace-a` is aliased as `/node_modules/workspace-a` via a symlink

>  the /workspace-a/package.json#name field is used and not the folder name
