**Flexbox**（弹性盒布局）是一种 CSS 布局模型，专门用来高效地布局和对齐页面中的元素。它的设计目的是在容器内的元素之间分配空间，并能轻松实现元素的对齐和分布（无论是水平还是垂直方向）。Flexbox 非常适合用来实现响应式设计。

---

### **Flexbox 的基本概念**
Flexbox 的布局模型由两个主要角色组成：
1. **父容器**：使用 `display: flex;` 或 `display: inline-flex;` 定义的元素，称为弹性容器（Flex Container）。
2. **子元素**：在弹性容器内的所有直接子元素，称为弹性项目（Flex Items）。

---

### **Flexbox 的主要特性**
1. **轴的概念**：
   - **主轴（Main Axis）**：弹性容器中元素排列的主方向（默认是水平方向）。
   - **交叉轴（Cross Axis）**：垂直于主轴的方向。
   - 可以通过 `flex-direction` 属性更改主轴的方向。

2. **弹性伸缩**：
   子元素可以根据容器的剩余空间进行缩小或拉伸，动态适应不同屏幕的大小。

3. **对齐与排序**：
   Flexbox 提供了强大的对齐方式，包括沿主轴和交叉轴的对齐和分布功能。

---

### **常用属性**
#### **父容器属性**
1. `display: flex;` 或 `display: inline-flex;`
   - 定义一个 Flexbox 容器。

2. `flex-direction`
   - 决定主轴方向（元素的排列方向）。
     - `row`（默认）：主轴为水平方向，从左到右排列。
     - `row-reverse`：主轴为水平方向，从右到左排列。
     - `column`：主轴为垂直方向，从上到下排列。
     - `column-reverse`：主轴为垂直方向，从下到上排列。

3. `justify-content`
   - 定义沿主轴的对齐方式：
     - `flex-start`（默认）：靠主轴起点对齐。
     - `flex-end`：靠主轴终点对齐。
     - `center`：居中对齐。
     - `space-between`：元素间距均匀分布，第一个和最后一个元素贴近容器两端。
     - `space-around`：元素间距均匀分布，但两侧留有一定空间。

4. `align-items`
   - 定义沿交叉轴的对齐方式：
     - `stretch`（默认）：拉伸以适应容器高度。
     - `flex-start`：靠交叉轴起点对齐。
     - `flex-end`：靠交叉轴终点对齐。
     - `center`：居中对齐。
     - `baseline`：沿文本基线对齐。

5. `align-content`
   - 定义多行内容的对齐方式（适用于多行布局）。

#### **子元素属性**
1. `flex`
   - 定义子元素如何伸缩和分配空间：
     - `flex-grow`: 元素在剩余空间中分配的比例（默认 `0`）。
     - `flex-shrink`: 元素在空间不足时的缩小比例（默认 `1`）。
     - `flex-basis`: 元素的初始大小。

2. `align-self`
   - 允许单个子元素覆盖 `align-items` 的对齐方式。

---

### **Flexbox 的简单示例**
```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>

<style>
  .container {
    display: flex;
    justify-content: space-around; /* 水平均匀分布 */
    align-items: center;          /* 垂直居中 */
    height: 200px;
  }
  .item {
    width: 50px;
    height: 50px;
    background-color: skyblue;
  }
</style>
```

### **效果**
1. 子元素在水平方向上均匀分布。
2. 子元素在垂直方向上居中对齐。


### **适用场景**
- 创建水平/垂直居中的内容。
- 实现导航栏、卡片布局。
- 动态调整子元素的大小和间距。



## 以下是 **Flexbox** 的所有属性，分为 **父容器属性** 和 **子元素属性**。

### **1. 父容器属性**
这些属性作用于设置为 `display: flex` 或 `display: inline-flex` 的容器。

#### **核心属性**
1. **`display`**
   - 定义弹性容器。
   - 值：
     - `flex`：块级弹性容器。
     - `inline-flex`：行内弹性容器。

2. **`flex-direction`**
   - 决定主轴方向（子元素的排列方向）。
   - 值：
     - `row`（默认）：水平从左到右。
     - `row-reverse`：水平从右到左。
     - `column`：垂直从上到下。
     - `column-reverse`：垂直从下到上。

3. **`flex-wrap`**
   - 决定子元素是否换行。
   - 值：
     - `nowrap`（默认）：不换行。
     - `wrap`：换行，超出的子元素会移到下一行。
     - `wrap-reverse`：换行，下一行子元素在上方。

4. **`justify-content`**
   - 定义子元素在主轴上的对齐方式。
   - 值：
     - `flex-start`（默认）：靠主轴起点对齐。
     - `flex-end`：靠主轴终点对齐。
     - `center`：居中对齐。
     - `space-between`：子元素间距均匀，首尾元素贴边。
     - `space-around`：子元素间距均匀，两侧留有空间。
     - `space-evenly`：子元素间距完全均匀。

5. **`align-items`**
   - 定义子元素在交叉轴上的对齐方式。
   - 值：
     - `stretch`（默认）：子元素在交叉轴上拉伸填充。
     - `flex-start`：靠交叉轴起点对齐。
     - `flex-end`：靠交叉轴终点对齐。
     - `center`：居中对齐。
     - `baseline`：沿文本基线对齐。

6. **`align-content`**
   - 定义多行子元素在交叉轴上的对齐方式（仅在多行布局时有效）。
   - 值：
     - `stretch`（默认）：拉伸填充容器。
     - `flex-start`：靠交叉轴起点对齐。
     - `flex-end`：靠交叉轴终点对齐。
     - `center`：居中对齐。
     - `space-between`：各行间距均匀分布，首尾行贴边。
     - `space-around`：各行间距均匀分布，两侧留有空间。
     - `space-evenly`：各行间距完全均匀。

---

### **2. 子元素属性**
这些属性作用于 Flexbox 容器中的直接子元素。

#### **核心属性**
1. **`order`**
   - 定义子元素的排列顺序。
   - 默认值：`0`。
   - 值：任何整数（正值、负值、0）。

2. **`flex`**
   - 简写属性，组合了以下三个属性：
     - `flex-grow`：定义子元素占用剩余空间的比例。
     - `flex-shrink`：定义子元素在空间不足时的缩小比例。
     - `flex-basis`：定义子元素的初始大小。
   - 示例：
     - `flex: 1;` 相当于 `flex-grow: 1; flex-shrink: 1; flex-basis: 0%;`
     - `flex: 0 1 auto;` 是默认值。

3. **`flex-grow`**
   - 定义子元素在剩余空间中的扩展比例。
   - 默认值：`0`（不扩展）。
   - 示例：
     - 如果一个子元素 `flex-grow: 1;`，另一个子元素 `flex-grow: 2;`，那么后者会占用两倍于前者的剩余空间。

4. **`flex-shrink`**
   - 定义子元素在空间不足时的缩小比例。
   - 默认值：`1`（可以缩小）。
   - 示例：
     - 如果一个子元素 `flex-shrink: 1;`，另一个 `flex-shrink: 0;`，当空间不足时，后者不会缩小。

5. **`flex-basis`**
   - 定义子元素的初始大小（在分配剩余空间之前）。
   - 默认值：`auto`。
   - 值可以是具体大小（如 `50px`、`30%`）或 `auto`。

6. **`align-self`**
   - 允许单个子元素覆盖父容器的 `align-items` 设置。
   - 值：
     - `auto`（默认）：继承父容器的 `align-items`。
     - 其他值与 `align-items` 一致：`flex-start`、`flex-end`、`center`、`baseline`、`stretch`。

---

### **3. Flexbox 相关属性关系图**
| 属性              | 作用对象   | 描述                                |
|-------------------|------------|-------------------------------------|
| `display`         | 父容器     | 定义容器为 Flexbox。               |
| `flex-direction`  | 父容器     | 定义主轴方向。                     |
| `flex-wrap`       | 父容器     | 定义子元素是否换行。               |
| `justify-content` | 父容器     | 定义主轴上的对齐方式。             |
| `align-items`     | 父容器     | 定义交叉轴上的对齐方式。           |
| `align-content`   | 父容器     | 定义多行子元素的对齐方式（多行）。 |
| `order`           | 子元素     | 定义子元素的排列顺序。             |
| `flex`            | 子元素     | 定义子元素的伸缩行为（简写）。     |
| `flex-grow`       | 子元素     | 定义子元素扩展比例。               |
| `flex-shrink`     | 子元素     | 定义子元素缩小比例。               |
| `flex-basis`      | 子元素     | 定义子元素的初始大小。             |
| `align-self`      | 子元素     | 覆盖父容器的对齐方式。             |

---