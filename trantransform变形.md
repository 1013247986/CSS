## 变形属性transform

* scale 缩小放大
* skew 倾斜
* rotate 旋转

####缩放 scale

scale(0.5) 表示缩小一半 

scale(2) 表示放大两倍

```markdown
    缩放 scale 具有三种情况：
    1、 scale(X,Y)使元素水平方向和垂直方向同时缩放（也就是X轴和Y轴同时缩放）
    2、scaleX(x)元素仅水平方向缩放（X轴缩放）
    3、scaleY(y)元素仅垂直方向缩放（Y轴缩放）
    
    scale()的取值默认的值为1，当值设置为0.01到0.99之间的任何值，作用使一个元素缩小；而任何大于     或等于1.01的值，作用是让元素放大。
```

####倾斜 skew

skew(15deg, 15deg) 表示水平方向上倾斜15度，竖直方向倾斜15度

```markdown
    Skew()具有三种情况：
    1、skew(x,y)使元素在水平和垂直方向同时扭曲（X轴和Y轴同时按一定的角度值进行扭曲变形）；
    2、skewX(x)仅使元素在水平方向扭曲变形（X轴扭曲变形）；
    3、skewY(y)仅使元素在垂直方向扭曲变形（Y轴扭曲变形）*/
```

#### 旋转 rotate

rotate(45deg) 表示顺时针旋转45度

####位移 translate

translate(400px,50px) 表示向右移动400px,向下移动50px

```markdown
    translate我们分为三种情况：
    1、translate(x,y)水平方向和垂直方向同时移动（也就是X轴和Y轴同时移动）
    2、translateX(x)仅水平方向移动（X轴移动）
    3、translateY(Y)仅垂直方向移动（Y轴移动）
```

####transform-origin 变形--原点 

```css
div.box{transform-origin: left top;transform: rotate(45deg); }
```

```markdown
    改变元素原点到左上角，然后进行顺时旋转45度。
```

####matrix () 变形--矩阵 

```css
div.box{transform: matrix(1,0,0,1,100,100);} 
```

```markdown
    matrix() 6个属性的意思的：
    第一个宽度比例1就是原大小，
    第二个是上下倾斜1就是2倍，2就是3倍，0就是不倾斜
    第三个是左右倾斜，数字和第二个一样的意思，
    第四个是高度比例1就是原大小，
    第五个是X方向的像素位移，X方向就是左右，
    第六个是Y方向的像素位移，X方向就是上下
```