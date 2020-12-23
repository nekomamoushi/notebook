# Import JSON in TypeScript

## Reading Local JSON Files using import statement

To import JSON into Angular, you need to add the following code in `tsconfig.json`.

```
{
  ...
  "compilerOptions": {
    ...
    "resolveJsonModule": true
    ...
  }
  ...
}
```

After doing this, you can do the following in TypeScript.

```
import * as data from './data.json';
```

If we log the data object in the console, we see that our data resides in a default array.

So you need to assign it in a variable like this:

```
products: any = (data as any).default;
```

## Reading Local JSON Files Using Angular HttpClient

Import the HttpClientModule in your app:

```
import { HttpClientModule } from '@angular/common/http';

@NgModule({
  ...
  imports: [
    ...
    HttpClientModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule {}
```

Then:

```
this.httpClient.get("assets/data.json").subscribe(data =>{
  console.log(data);
  this.products = data;
})
```
