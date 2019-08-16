## Function for GET `XMLHttpRequest`

```js
function sendGetRequest(url, callback) {
  const xhr = new XMLHttpRequest();
  xhr.onreadystatechange = function() {
    if (xhr.readyState === XMLHttpRequest.DONE) {
      if (xhr.status === 200) {
        callback(JSON.parse(xhr.responseText));
      }
      else {
        console.log('something went wrong');
      }
    }
  }
  xhr.open('GET', url);
  xhr.send();
}

sendGetRequest('https://chain-chess.glitch.me', console.log);
```
