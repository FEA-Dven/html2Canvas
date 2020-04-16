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
                this.$Toast.clear();
                this.posterUrl = url;
                this.$store.commit("setPosterUrl", url); // 更新cookie里面的token
                if (this.drawTimes === 0) {
                  this.startMakePoster();
                  this.drawTimes++;
                }
              })
              .catch(err => {
                this.$Dialog({
                  title: "亲~网络异常，请重试",
                  message: JSON.stringify(err)
                });
              });
```
