# Import JSON in TypeScript

To import JSON into your TypeScript code, you need to add the following code to a typings file.


```
// This will allow you to load `.json` files from disk
declare module "*.json"
{ const value: any;
  export default value;
}

// This will allow you to load JSON from remote URL responses
declare module "json!*"
{ const value: any;
  export default value;
}
```

After doing this, you can do the following in TypeScript.

```
import * as graph from './data/graph.json';
import data from "json!http://foo.com/data_returns_json_response/";
```

You can then use graph and data as JSON objects in your TypeScript code.
