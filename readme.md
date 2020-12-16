
# Jikan.js for client side plain JavaScript 

## usage 

```js 
await import("https://cdn.jsdelivr.net/gh/yuis-ice/jikanjs/jikanjs.js")
typeof(jikanjs)
```

## example 

> print for example all episodes titles of the anime "No Game No Life"
> [zuritor/jikanjs: A small Wrapper for the unofficial MAL API jikan.moe](https://github.com/zuritor/jikanjs#examples)

```js 

(async () => {
    await import("https://cdn.jsdelivr.net/gh/yuis-ice/jikanjs/jikanjs.js")
    
    
    jikanjs.loadAnime(19815, 'episodes').then((response) => {
        response.episodes.forEach(element => {
            console.log(`${element.episode_id}: ${element.title} - ${element.title_romanji} - ${element.title_japanese}`);
        })
    }).catch((err) => {
        console.error(err); // in case a error happens
    });

})();

```

## reproduction

```
npm i -g browserify
npm i jikanjs 
``` 

main02.js 

```js 
const jikanjs  = require('jikanjs');
```

```
browserify main02.js > bundle02.js
```

cp bundle02.js jikanjs.js
