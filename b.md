# 第二天
```js
import axios from 'axios';

function searchGit(name='omcbd'){

  return    (
            axios.get(`https://api.github.com/users/${name}`)
            .then((res) =>   ({
                getData:res.data
              })      //
                )

              .catch(function (error) {
                alert(error)
              })
            )
}
function getJson(){
  return  axios.get(`https://raw.githubusercontent.com/omcbd/data/master/card.json?${Math.random()}`) //json 文件只请求一次，并将数据加入缓存中， ?${Math.random()}  只要问号后的字符变化 就不会缓存,后台更新数据，刷新页面会显示
              .then(
                  function (res){
                    return {getJsonData:res.data }    //返回对象 return{}
                  }
              )

                .catch(function (error) {
                  alert(error)
                })

}
function getMd(path){
  return   axios.get(`https://raw.githubusercontent.com/omcbd/data/master/${path}.md?${Math.random()}`)
            .then((res) =>   ({
                getMdData:res.data
              })
                )

              .catch(function (error) {
                alert(error)
              })

}
export {searchGit,getJson,getMd}

```
