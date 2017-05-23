# messenger-export

A way of visualizing your exported Facebook messages exported from [here](https://github.com/bencooper222/Facebook-Messenger-Export).

## Build Setup

You need to have in a folder at the same level as `app` filled with your JSONs called (appropriatel) `jsons`. I'll be adding a config variable option later but for now this is what we got. That folder needs to have a `manifest.json` file and one JSON per thread called `1.json`, `2.json` and so on. 
``` bash
# install dependencies (npm install also works if you're less cool)
yarn install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build
```

For detailed explanation on how things work, consult the [docs for vue-loader](http://vuejs.github.io/vue-loader).
