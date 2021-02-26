This repository is a minimal example for a problem with [typedoc-plugin-pages](https://github.com/mipatterson/typedoc-plugin-pages).

## Setup

* `npm install`
* `npm run typedoc-pages`

Docs are built into `./docs-pages`

## Problem
* docs generated from code are usually grouped in a separate page-group
* when accessing a sub-module, the page-grouping breaks:
    * `/docs-pages/modules/two.html`:  
      ```
      markdown // example md page in this repo
        example
      API
        Modules
        one
        two // current
      {...module members}
      ```
    * `/docs-pages/modules/one.submodule.html`:  
      ```
      markdown
        example
        Modules // <-- wrongly grouped & no children*
      {...module members}
      ```

\* submodules removing the rest of the navigation occurs with typedoc only as well.
However there is no grouping of pages so the problem is not apparent.
Run `npm run typedoc-only` to build docs to `./docs` without pages plugin.
