# Array.prototype.map()
## The ES6+ feature I would like to examine is the map() method

### This method creates a new array with the results of calling a provided function on every element in the calling array. I used this method to update empty arrays such as gifs and emojis in order to display the data fetched by the respective APIs. You can read more about it here: [Array.prototype.map()](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/map)

### Let me show you a snippet of code:
```js 
function fetchGifs() {
  const API_KEY = 'URSRgSXuGgvVg6LKFDlUsp0bWM80ansC';
  fetch(`https://api.giphy.com/v1/gifs/search?q=${searchGif.value}&api_key=${API_KEY}&limit=10`)
    .then(res => res.json())
    .then((data) => {
      gifs = data.data
      const innerHTML = gifs.map((g, i) => `<img src="${g.images.fixed_height_small.url}" data-index="${i}" />`).join('')
      div.innerHTML = innerHTML
      searchGif.value = ''
    });
}

```
### Here I am mapping through the gifs data in order to push it to the gifs array.
### Lastly, a screenshot of my code to better understand the method:
![Map](/js.png)
