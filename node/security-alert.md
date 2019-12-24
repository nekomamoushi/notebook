# NPM Security Alert

The use case for this is when there is a security vulnerability and you MUST update a nested dependency otherwise your project would be vulnerable. But this should only be used as a last resource, you should first update your top-level dependencies and file an issue for them to update the vulnerable sub-dependencies (npm ls <vulnerable dependency> can help you with that).

# NPM Force Resolution

```
npm install npm-force-resolutions
```

# What to do

First add a field resolutions with the dependency version you want to fix to your package.json:

```
"resolutions": {
  "serialize-javascript": "^2.1.1"
}
```

Then add npm-force-resolutions to the preinstall script so that it patches the package-lock file before every npm install you run:

```
"scripts": {
  "preinstall": "npx npm-force-resolutions"
}
```

Maybe clear the node_modules:

```
rm -rf node_modules
```

Now just run npm install as you would normally do:

```
npm install
```

## References

[link](https://github.com/angular/angular-cli/issues/16414)
