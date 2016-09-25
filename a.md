# axios
```js
function getMd(add) {
 +  let address = `https://raw.githubusercontent.com/newming/demodata/master/blog/${add}.md`;
 +  return axios.get(address)
 +    .then( (res) => (
 +      { getMd:res.data }
 +    ))
 +    .catch(function (error) {
 +      alert(error);
 +    });
 ```
