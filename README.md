# Calcite missing dependency

Calcite is missing the `@types/sortablejs` dependency, resulting in a type
error in a consuming application.

## Reproduction

1. Checkout this repository - `git clone https://github.com/maxpatiiuk/calcite-missing-dependency`
2. Run `npm install`
3. Run `npx tsc`
4. See error:

   ```yaml
   > npx tsc

   node_modules/@esri/calcite-components/dist/types/components/value-list/value-list.d.ts:2:22 - error TS7016: Could not find a declaration file for module 'sortablejs'. '/Users/mak13180/site/esri/calcite-components-examples/preact-typescript/node_modules/sortablejs/Sortable.min.js' implicitly has an 'any' type.
     Try `npm i --save-dev @types/sortablejs` if it exists or add a new declaration (.d.ts) file containing `declare module 'sortablejs';`

   2 import Sortable from "sortablejs";
                          ~~~~~~~~~~~~

   node_modules/@esri/calcite-components/dist/types/utils/sortableComponent.d.ts:1:22 - error TS7016: Could not find a declaration file for module 'sortablejs'. '/Users/mak13180/site/esri/calcite-components-examples/preact-typescript/node_modules/sortablejs/Sortable.min.js' implicitly has an 'any' type.
     Try `npm i --save-dev @types/sortablejs` if it exists or add a new declaration (.d.ts) file containing `declare module 'sortablejs';`

   1 import Sortable from "sortablejs";
                          ~~~~~~~~~~~~


   Found 2 errors in 2 files.

   Errors  Files
        1  node_modules/@esri/calcite-components/dist/types/components/value-list/value-list.d.ts:2
        1  node_modules/@esri/calcite-components/dist/types/utils/sortableComponent.d.ts:1
   ```
