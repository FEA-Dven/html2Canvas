# html2Canvas
> 解决html2Canvas在ios13.4中失效问题
```
// 引入
import html2canvas from "../../lib/html2canvas";
```
```
// 使用, 全局window对象加入html2canvas，如果没有window就调用原来的，所以需要做判断
(window.html2canvas || html2canvas)(shareContent, opts)
              .then(canvas => {
                let url = canvas.toDataURL("image/png");
                console.log(url)
              })
              .catch(err => {
                // do sth
              });
```
