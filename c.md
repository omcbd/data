# marked & highlight.js
npm i marked highlight.js --save
```js
import marked from 'marked'
import hljs from 'highlight.js'
marked.setOptions({
 +      highlight: function (code) {
 +        return hljs.highlightAuto(code).value;
 +      }
 +    });
 render(){
 let content = marked('')     //md 格式字符串
  return <div dangerouslySetInnerHTML={{__html: content} />
 ```
