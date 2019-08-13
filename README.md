## 三维饼图

通过将三维坐标转换为二维坐标实现原生canvas绘制三维饼图

``` js
var cvs = document.getElementById("canvas");
    cvs.width = window.innerWidth;
    cvs.height = window.innerHeight;
    var ctx = cvs.getContext("2d");
    var fallLength = 50000;//焦距
    var centerX = cvs.width / 2;
    var centerY = cvs.height / 2;
var Vector = function (x, y, z) {
    this.x = x;
    this.y = y;
    this.z = z;
    this.get2d = function () {
        var scale = fallLength / (fallLength + this.z);
        var x = centerX + this.x * scale;
        var y = centerY + this.y * scale;
        return {x: x, y: y};
    }
};
```

## 示例 

[https://kwongdroid.github.io/demos/3dpie.html](https://kwongdroid.github.io/demos/3dpie.html)
