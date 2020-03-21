##基础线性渐变

**注意： Internet Explorer 9 及之前的版本不支持渐变。**

要创建最基本的渐变类型，您只需指定两种颜色即可。 这些被称为色标。 至少指定两个色标，也可以指定任意数量。

```css
.auto-spaced-linear-gradient {
  background: linear-gradient(red, yellow, blue, orange);
}
```

####渐变提示

默认情况下，渐变会平滑地从一种颜色过渡到另一种颜色。你可以通过设置一个值来将渐变的中心点移动到指定位置。 在如下示例中, 我们将渐变的中心点由50%设为10%。

```css
.color-hint {
  background: linear-gradient(blue, 10%, pink);
}
.simple-linear {
  background: linear-gradient(blue, pink);
}
```

####改变渐变方向

默认情况下，线性渐变的方向是从上到下， 你可以指定一个值来改变渐变的方向。

```css
.horizontal-gradient {
  background: linear-gradient(to right, blue, pink);
}
```

从左上角到右下角的线性渐变：

```css
#grad {
  height: 200px;
  background-image: linear-gradient(to bottom right, red, yellow);
}
```

####设置渐变角度

如果你想要更精确地控制渐变的方向，你可以给渐变设置一个具体的角度。

```css
.angled-gradient {
  background: linear-gradient(70deg, blue, pink);
}
```

在使用角度的时候, `0deg` 代表渐变方向为从下到上, `90deg` 代表渐变方向为从左到右，诸如此类正角度都属于顺时针方向。 而负角度意味着逆时针方向

####颜色终止位置

你不需要让你设置的颜色在默认位置终止。 你可以通过给每个颜色设置0，1%或者2%或者其他的绝对数值来调整它们的位置。如果你将位置设置为百分数， `0%` 表示起始点, 而100%表示终点，但是如果需要的话你也可以设置这个范围之外的其他值来达到你想要的效果。如果有些位置你没有明确设置，那么它将会被自动计算，第一种颜色会在0%处停止，而最后一种颜色是100%，至于其他颜色则是在它邻近的两种颜色的中间停止。 

```css
.multicolor-linear { 
   background: linear-gradient(to left, lime 28px, red 77%, cyan);
}
```

##重复的线性渐变

```css
#grad {
  /* 标准的语法 */
  background-image: repeating-linear-gradient(red, yellow 10%, green 20%);
}
```

##css径向渐变

颜色结点均匀分布的径向渐变：

```css
#grad {
  background-image: radial-gradient(red, yellow, green);
}
```

颜色结点不均匀分布的径向渐变：

```css
#grad {
  background-image: radial-gradient(red 5%, yellow 15%, green 60%);
}
```

####设置形状

shape 参数定义了形状。它可以是值 circle 或 ellipse。其中，circle 表示圆形，ellipse 表示椭圆形。默认值是 ellipse。

形状为椭圆形的径向渐变：

```css
#grad {
  background-image: radial-gradient(ellipse , red, yellow, green);
}
```

####重复的径向渐变

```css
#grad {
  background-image: repeating-radial-gradient(red, yellow 10%, green 15%);
}
```

####配合背景图使用

**注意:**渐变效果要写在url引入的背景图之前

```css
#grad {
  background:linear-gradient(to right bottom,transparent,#000),url(/img/bridge.103543.png);
}
```

