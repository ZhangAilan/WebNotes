在 CSS 中，`overflow` 属性用于控制当一个元素的内容超出其指定的尺寸（宽度或高度）时，如何处理超出部分。它常用于管理具有固定大小容器的内容，避免溢出部分导致布局问题。`overflow` 可以设置为以下几个值：

### 1. `visible`（默认值）
- **解释**：内容会超出元素的框，显示出来，不会被裁剪或滚动。
- **适用场景**：当你希望内容超出元素的边界并完全可见时使用。
- **示例**：
  ```css
  div {
    width: 200px;
    height: 200px;
    overflow: visible;
  }
  ```

### 2. `hidden`
- **解释**：超出元素框的内容会被裁剪并不可见，但它不会产生滚动条。
- **适用场景**：当你希望隐藏溢出的内容并且不需要显示滚动条时使用。
- **示例**：
  ```css
  div {
    width: 200px;
    height: 200px;
    overflow: hidden;
  }
  ```

### 3. `scroll`
- **解释**：如果内容超出元素的框，无论是否溢出，都会显示滚动条，允许用户滚动查看内容。
- **适用场景**：无论内容是否溢出，始终显示滚动条。
- **示例**：
  ```css
  div {
    width: 200px;
    height: 200px;
    overflow: scroll;
  }
  ```

### 4. `auto`
- **解释**：如果内容超出元素的框，浏览器会自动添加滚动条；如果内容没有超出，则不显示滚动条。
- **适用场景**：你不确定内容是否会超出容器，使用此选项可以确保只有在必要时才显示滚动条。
- **示例**：
  ```css
  div {
    width: 200px;
    height: 200px;
    overflow: auto;
  }
  ```

### 5. `overflow-x` 和 `overflow-y`
- **解释**：`overflow-x` 和 `overflow-y` 允许分别设置水平和垂直方向上的溢出行为。
  - `overflow-x` 控制水平溢出。
  - `overflow-y` 控制垂直溢出。
- **示例**：
  ```css
  div {
    width: 200px;
    height: 200px;
    overflow-x: auto; /* 水平滚动 */
    overflow-y: hidden; /* 垂直内容隐藏 */
  }
  ```

### 总结
- `overflow: visible`：内容溢出时显示。
- `overflow: hidden`：内容溢出时裁剪。
- `overflow: scroll`：总是显示滚动条。
- `overflow: auto`：只有内容超出时显示滚动条。
- `overflow-x` 和 `overflow-y`：分别控制水平和垂直溢出。