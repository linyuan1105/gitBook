- 为什么在纹理中，平面顶点坐标使用的`三位`进行表示，而在普通绘制中却是`两位`？
> 
--------------------
- 为什么在纹理中，平面顶点坐标范围已经是归一化的,在普通的的二维绘制使用具体的宽高坐标？
> 其实最终还是需要对顶点坐标进行归一化处理的；顶点坐标归一化处理后，范围在[-1,1]之间；
> 在实际像素坐标上，左上角为[0,0]坐标点；而在归一化后的坐标点中，中心点为[0,0]
> 

---------------------
- 对于非2的n次幂的纹理，在使用mipmap时，参数需要进行不同的设置?
```javascript
if (isPowerOf2(image.width) && isPowerOf2(image.height)) {
      gl.generateMipmap(gl.TEXTURE_2D)
    } else {
      gl.texParameteri(
        gl.TEXTURE_2D, gl.TEXTURE_WRAP_S, gl.CLAMP_TO_EDGE
      )
      gl.texParameteri(
        gl.TEXTURE_2D, gl.TEXTURE_WRAP_T, gl.CLAMP_TO_EDGE
      )
      gl.texParameteri(
        gl.TEXTURE_2D, gl.TEXTURE_MIN_FILTER, gl.LINEAR
      )
    }
```
-------------------

