在 CSS 中，`transition` 是一个属性，用于设置元素从一种样式到另一种样式的过渡效果。它允许属性的变化过程变得平滑，而不是瞬间发生。

---

### **语法**
```css
transition: [property] [duration] [timing-function] [delay];
```

- **`property`**：指定需要过渡的 CSS 属性，如 `width`、`background-color` 等。如果使用 `all`，表示对所有支持的属性生效。
- **`duration`**：设置动画持续时间（单位为秒 `s` 或毫秒 `ms`，如 `0.3s`）。
- **`timing-function`**：定义动画的加速或减速方式，常见值有：
  - **`ease`**：慢→快→慢（默认）。
  - **`linear`**：匀速。
  - **`ease-in`**：慢→快。
  - **`ease-out`**：快→慢。
  - **`ease-in-out`**：慢→快→慢。
  - **自定义贝塞尔曲线**：如 `cubic-bezier(0.25, 0.1, 0.25, 1)`。
- **`delay`**：动画开始前的延迟时间（单位为秒 `s` 或毫秒 `ms`，如 `0s`）。

---

### **单属性示例**

#### **宽度过渡**
```css
.box {
  width: 100px;
  transition: width 0.5s ease;
}

.box:hover {
  width: 200px;
}
```
- 当鼠标悬停时，宽度从 `100px` 平滑过渡到 `200px`，动画持续 `0.5s`，效果是慢→快→慢。

---

### **多属性过渡**

#### **改变多个属性**
```css
.box {
  width: 100px;
  background-color: blue;
  transition: width 0.5s ease, background-color 1s linear;
}

.box:hover {
  width: 200px;
  background-color: red;
}
```
- **宽度**的过渡持续 `0.5s`，使用 `ease`。
- **背景颜色**的过渡持续 `1s`，使用匀速 `linear`。

---

### **全属性过渡**

#### **过渡所有属性**
```css
.box {
  width: 100px;
  background-color: blue;
  transform: rotate(0deg);
  transition: all 0.5s ease;
}

.box:hover {
  width: 200px;
  background-color: red;
  transform: rotate(45deg);
}
```
- `all` 指对所有可过渡属性生效。
- 所有属性的动画时间为 `0.5s`，效果为慢→快→慢。

---

### **延迟示例**
#### **添加延迟**
```css
.box {
  width: 100px;
  transition: width 0.5s ease 0.2s; /* 延迟 0.2 秒 */
}

.box:hover {
  width: 200px;
}
```
- 鼠标悬停时，动画在 `0.2s` 后才开始。

---

### **贝塞尔曲线示例**
#### **自定义速度曲线**
```css
.box {
  width: 100px;
  transition: width 0.5s cubic-bezier(0.42, 0, 0.58, 1);
}

.box:hover {
  width: 200px;
}
```
- 使用自定义贝塞尔曲线实现更复杂的速度控制。

---

### **注意事项**
1. **非数值属性限制**：`transition` 只能作用于数值类型的 CSS 属性（如 `width`、`height`、`opacity`）。对于非数值属性（如 `display`），需要使用其他方法（如动画帧 `@keyframes`）。
2. **初始值与目标值**：确保指定了属性的初始状态和变化后的状态，否则动画可能无效。
3. **硬件加速**：对 `transform` 和 `opacity` 进行动画通常性能更优，避免直接修改 `width` 或 `top` 等可能引发重排的属性。

---

### **过渡 VS 动画**
- **`transition`**：用于两种状态之间的平滑过渡，必须有触发事件（如悬停或点击）。
- **`@keyframes` 动画**：用于复杂的多步骤动画，不依赖用户交互触发。

---

### 总结
`transition` 是一种轻量级的 CSS 动画方式，用于使元素的状态变化更加自然、流畅。通过调整持续时间、延迟时间和速度曲线，可以实现各种精美的过渡效果。