# canvas-select 标注插件

常用于AI图片标注，视频帧标注

## 使用

```
npm i canvas-select
```
```html
<canvas width="500" height="500" class="container"></canvas>
```
```js
   const instance = new CanvasSelect(".container");
    instance.setData([
      {
        label: "你好", // label (非必填)
        type: 1, // 矩形 （必填）
        coor: [  // 矩形坐标，由2个点表示 (必填)
          [10, 10],
          [100, 100],
        ],
      },
      {
        label: "世界",
        type: 2, // 多边形
        coor: [ // 多边形坐标，由3个点以上表示 (必填)
          [30, 150],
          [120, 100],
          [50, 200],
        ],
      },
      ,
      {
        type: 2, // 多边形
        coor: [
          [230, 150],
          [320, 100],
          [250, 200],
        ],
      },
    ]);
    // 0 不创建，1创建矩形，2创建多边形
    instance.createType = 1
    // 选中
    instance.on("select", (info) => {
      console.log("select", info);
      // 可对选中对参数info进行修改
      // 调用instance.update()更新视图
    });
    // 添加
    instance.on("add", (info) => {
      console.log("add", info);
    });
    // data更新
    instance.on("update", function () {
      console.log("update");
    });
    // resize
    instance.on("resize", function (info) {
      console.log("resize", info);
    });
```
