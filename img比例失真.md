#### object-fit

对于图片，我们总是建议同时写上高和宽，避免因为图片尺寸错误带来的布局问题

```css
ul li img {
    width: 150px;
    height: 100px;
}
```

同时，给 `<img>` 标签同时写上高宽，可以在图片未加载之前提前占住位置，避免图片从未加载状态到渲染完成状态高宽变化引起的重排问题。

当然，限制高宽也会出现问题，譬如图片被拉伸了，非常的难看

这个时候，我们可以借助 `object-fit`，它能够指定可替换元素的内容（也就是图片）该如何适应它的父容器的高宽。

```css
ul li img {
    width: 150px;
    height: 100px;
    object-fit: cover;
}
```

利用 `object-fit: cover`，使图片内容在保持其宽高比的同时填充元素的整个内容框。

`object-fit` 还有一个配套属性 `object-position`，它可以控制图片在其内容框中的位置。（类似于 `background-position`），m默认是 `object-position: 50% 50%`，如果你不希望图片居中展示，可以使用它去改变图片实际展示的 position 

```css
ul li img {
    width: 150px;
    height: 100px;
    object-fit: cover;
    object-position: 50% 100%;
}
```

