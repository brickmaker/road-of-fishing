# WebGL中对象点击检测

应该有好多种方式，这里参考《WebGL Programming Guide: Interactive 3D Graphics Programming with WebGL》中的方式简单梳理一下。

目前自己已知的从WebGL管线中得到处理后的数据只有`readPixels()`这个函数，因此肯定是通过这个函数返回的像素颜色来判断是否点击。

判断需要基于两点：

1. 是否发生了点击
2. 是否点击到了物体

发生点击使用传入uniform的方法，告诉shader当前发生了点击，需要做相应的检测。

点到了哪一个物体比较难判断，这里书中给的方法还是挺trick的：把物体绘制成红色，然后用`readPixels()`读取点击到的位置，如果是红色，则说明点击的位置有物体。

由于中间会发生把物体都画成纯色的过程，因此需要画两次，使视觉上感受不到这个过程，整体流程如下：

```js
check:
    gl.uniform1i(u_Clicked, 1)

    draw(...)
    pixels = new Uint8Array(4); // Array for storing the pixel value

    gl.readPixels(x, y, 1, 1, gl.RGBA, gl.UNSIGNED_BYTE, pixels)
    if (pixels[0] == 255) // The mouse in on cube if R(pixels[0]) is 255
    picked = true

    gl.uniform1i(u_Clicked, 0)
    draw(...)

    return picked
```

> 参考自《WebGL Programming Guide: Interactive 3D Graphics Programming with WebGL》Chapter10, PickObject例子