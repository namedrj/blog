```js
let url = `http://item.taobao.com/item.htm?a=1&b=2&c=&d=xxx&e`;

/**
 * 一个JavaScript函数把URL参数解析成Json对象
 * @param {string} url 
 */
function parseQueryString(url) {
  let x = url.indexOf('?') + 1;
  let parseStr = url.substr(x).split('&');
  let obj = {};
  for (let i = 0, len = parseStr.length; i < len; i++) {
    let tmp = parseStr[i].split('=');
    let key = tmp[0];
    let value = tmp[1];
    obj[key] = value;
  }
  return obj;
}
let res = parseQueryString(url);
console.log(JSON.stringify(res));
```
