# Import JSON in TypeScript

To import JSON into your TypeScript code, you need to add the following code in `tsconfig.json`.

```
{
  "compilerOptions": {
    "target": "es6",
    "module": "commonjs",
    "allowSyntheticDefaultImports": true,
    "esModuleInterop": true,
    "resolveJsonModule": true
}
```

After doing this, you can do the following in TypeScript.

```
import graph from './data/graph.json';
```

You can then use graph and data as JSON objects in your TypeScript code.
