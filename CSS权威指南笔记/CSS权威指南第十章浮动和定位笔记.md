- 浮动元素：首先会以某种方式将浮动元素从文档的正常流中删除，但还是会影响布局。

  float，left、right、none。

  clear，阻止元素周围有浮动元素。

- 定位：可以准确地定义元素框相对于其正常位置应该出现在哪里，或者相对于父元素，另一个元素甚至浏览器窗口本身的位置。

  - 定位类型：通过position属性，有四种不同类型的定位。static、relative、absolute、fixed
    - static：元素框正常生成，作为文档流的一部分。
    - relative：元素偏移某个距离，元素仍保持其未定位前的形状，它原本所占的空间仍保留。
    - absolute：元素框从文档流完全删除，并相当于其包含块定位，包含块可能是文档中的另一个元素或者是初始包含块。
    - fixed：类似于absolute，但是包含块是视窗本身
  - 包含块（可解释为定位上下文）：对于浮动元素，包含块指最近的块级祖先元素。对于定位，规则就比较麻烦
    - 根元素的包含块(初始包含块)由用户代理建立，在大部分浏览器中，是一个视窗大小的矩形
    - 对于非根元素，relative或static包含块由最近的块级框，表单元格或行内块祖先框的内容边界构成。
    - absolute包含块设置为最近的position值不是static的祖先元素(可以是任何类型)
      - 如果是块级元素，包含块则设定为该元素边框界定的区域
      - 行内元素，则设置为该元素的内容边界
      - 没有祖先元素，包含块定义为初始包含块
  - 偏移属性：上面的三种定位机制（relative、absolute、fixed）使用了4哥属性来描述定位元素各边相对于其包含块的偏移。top、right、bottom、left。例如top描述了定位元素的上外边距离其包含块的顶端多远。

- 溢出：overflow，visible默认，表示元素的内容在元素框之外也可见，hidden剪裁超出元素框的内容，且不会提供滚动接口让用户访问超出建材区域的内容，scroll裁剪，内容会在元素框的边界处剪裁，移除部分无法看到，不过可以提供某种滚动条来看到所有内容，auto允许用户代理来确定采用何种行为。

- 元素可见性：visibility，visible可见，hidden不可见，与display有区别，它只是不可见，但还在那里，display不仅不显示元素，还会从文档中删除。

- 绝对定位：从文档流中完全删除。然后相对于其包含块定位，根据偏移属性放置。

  便宜属性确定元素的高度和宽度。

  ```
  margin:auto 0;//垂直居中
  ```

- z轴上的放置：z-index，可以改变元素的相互覆盖的顺序。值较高的元素比值较低的元素离读者更近

- 固定定位fixed：和绝对定位类似，但是包含块是视窗
