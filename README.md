# Astro Namespace Issue

**Issue**: https://github.com/snowpackjs/astro/issues/1237

**CodeSandbox**: https://codesandbox.io/s/github/jonathantneal/astro-namespace-issue

---

### Bug Description

When using the attribute namespace `on`, the entire project throws.

**Usage**:
```html
<button on:click>
  click me
</button>
```

**Error**:
```
node_modules/astro/dist/compiler/codegen/index.js:665
            throw new Error("Unexpected (enter) node type: " + node.type);
                  ^

Error: Unexpected (enter) node type: EventHandler
    at Object.enter (node_modules/astro/dist/compiler/codegen/index.js:665:19)
    at AsyncWalker.visit (node_modules/astro/node_modules/estree-walker/src/async.js:49:22)
    at AsyncWalker.visit (node_modules/astro/node_modules/estree-walker/src/async.js:79:25)
    at async AsyncWalker.visit (node_modules/astro/node_modules/estree-walker/src/async.js:79:14)
    at async AsyncWalker.visit (node_modules/astro/node_modules/estree-walker/src/async.js:79:14)
    at async AsyncWalker.visit (node_modules/astro/node_modules/estree-walker/src/async.js:79:14)
    at async asyncWalk (node_modules/astro/node_modules/estree-walker/src/index.js:34:9)
error Command failed with exit code 1.
info Visit https://yarnpkg.com/en/docs/cli/run for documentation about this command.
```

### Steps to Reproduce

1. `git clone git@github.com:jonathantneal/astro-namespace-issue.git` and `cd astro-namespace-issue`
2. `yarn`
3. `yarn start`
4. Visit the page (e.g. `http://localhost:3000/`)
5. Error! `Unexpected (enter) node type: EventHandler`
