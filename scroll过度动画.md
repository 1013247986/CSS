#### 过渡与动画

在我们的交互过程中，**适当的增加过渡与动画，能够很好的让用户感知到页面的变化**。

譬如我们页面上随处可见 loading 效果，其实就是这样一种作用，让用户感知页面正在加载，或者正在处理某些事务.

#### 滚动平滑：使用 `scroll-behavior: smooth` 让滚动丝滑

使用 `scroll-behavior: smooth`，可以让滚动框实现平稳的滚动，而不是突兀的跳动。看看效果，假设如下结构

```html

<div class="g-container">
  <nav>
    <a href="#1">1</a>
    <a href="#2">2</a>
    <a href="#3">3</a>
  </nav>
  <div class="scrolling-box">
    <section id="1">First section</section>
    <section id="2">Second section</section>
    <section id="3">Third section</section>
  </div>
</div>
```

不使用 `scroll-behavior: smooth`，是突兀的跳动切换

给可滚动容器添加 `scroll-behavior: smooth`，实现平滑滚动

#### 使用 `scroll-snap-type` 优化滚动效果

`sroll-snap-type` 可能算得上是新的滚动规范里面最核心的一个属性样式。

**scroll-snap-type**：属性定义在滚动容器中的一个临时点（snap point）如何被严格的执行。

光看定义有点难理解，简单而言，这个属性规定了一个容器是否对内部滚动动作进行捕捉，并且规定了如何去处理滚动结束状态。让滚动操作结束后，元素停止在适合的位置.

```css
// 父元素
{
    overflow:auto;
    scroll-snap-type:x mandatory;
}
// 子元素
{
    sorll-snap-align:conter;
}
```

