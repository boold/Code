# 使用js实现单向绑定

> 最详细解释的单向绑定
>
> 参考资料

[MDN](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/defineProperty)

[addEventListener()](http://www.runoob.com/jsref/met-element-addeventlistener.html)定义与用法

```html
<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Document</title>
</head>

<body>
  <input type="text" id="a">
  <span id="b"></span>
  <script>
    // var obj = {};
    // Object.defineProperty(obj,"hello",{
    //   set: () => {
    //     console.log("get方法被调用");
    //   },
    //   get: (val) => {
    //     console.log("se方法被调用"+val);
    //   }
    // })
    let obj = {};
    //Object.defineProperty(obj, prop, descriptor)
    // obj 要在其上定义属性的对象。
    // prop 要定义或修改的属性的名称。
    // descriptor 将被定义或修改的属性描述符。
    Object.defineProperty(obj, 'hello', {    //这里定义obj.hello为完成修改的属性
      set: (newVal) => {                     //当obj.hello的属性发生变化,就会以参数传进来 
        document.getElementById('a').value = newVal;    //set触发给a值同时把值给b实现绑定
        document.getElementById('b').innerHTML = newVal;
        obj.hello
      },
      get: ()=> {
        console.log("hahahaah");  
      }
    });
    //addEventListener() 方法用于向指定元素添加事件句柄。
    //element.addEventListener(event, function, useCapture)
    //event 所有 HTML DOM 事件
    //function 指定事件触发时执行的函数。
    //useCapture 指定事件是否在捕获或冒泡阶段执行。
    document.addEventListener('keyup', (e) => { //监听键盘的按键松开的事件
      console.log(e);
      obj.hello = e.target.value; //将监听到了变化的值给obj.hello,让他触发set属性
    })
  </script>
</body>

</html>
```

