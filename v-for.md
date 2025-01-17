在 Vue.js 中，`v-for` 是一个指令，用于在模板中循环渲染列表数据。它可以生成动态的 DOM 元素，适用于显示数组或对象中的数据。

---

### 基本语法
```vue
<div v-for="item in items" :key="item.id">
  {{ item.name }}
</div>
```

- **`item in items`**: 表示从 `items` 数据源中循环出每一项，`item` 是当前循环项的引用。
- **`:key`**: 提供唯一标识符，优化 Vue 的虚拟 DOM 性能（必须包含）。

---

### 用法详解

#### 1. **数组遍历**
```vue
<ul>
  <li v-for="(item, index) in items" :key="index">
    {{ index }} - {{ item }}
  </li>
</ul>
```
- **`(item, index)`**: 第二个参数 `index` 是当前项的索引值。
- **示例数据：**
  ```javascript
  data() {
    return {
      items: ['苹果', '香蕉', '橘子']
    };
  }
  ```
- **渲染结果：**
  ```
  0 - 苹果
  1 - 香蕉
  2 - 橘子
  ```

---

#### 2. **对象遍历**
当数据是对象时，可以遍历其键值对：
```vue
<ul>
  <li v-for="(value, key, index) in object" :key="key">
    {{ index }}: {{ key }} = {{ value }}
  </li>
</ul>
```
- **`(value, key, index)`**: 分别表示值、键和索引。
- **示例数据：**
  ```javascript
  data() {
    return {
      object: { name: 'Vue', version: '3.0' }
    };
  }
  ```
- **渲染结果：**
  ```
  0: name = Vue
  1: version = 3.0
  ```

---

#### 3. **指定渲染范围**
通过 `of` 或者过滤器来实现限定范围：
```vue
<li v-for="n in 10" :key="n">
  数字 {{ n }}
</li>
```
- 循环 1 到 10 的数字，等价于 `[1, 2, 3, ..., 10]`。

---

### 配合组件使用
`v-for` 可以用于动态渲染组件：
```vue
<my-component
  v-for="item in items"
  :key="item.id"
  :data="item"
></my-component>
```

- **动态数据传递：**
  每个 `item` 会作为 `data` 传递给子组件 `my-component`。

---

### 注意事项
1. **唯一性：**
   - 每个循环项必须设置 `:key`，以确保 Vue 能高效更新 DOM。
   - `key` 应该是唯一的，推荐使用主键、ID 等。
   
2. **性能优化：**
   - 避免使用数组索引作为 `:key`，特别是在数组内容可能变化的情况下。

3. **嵌套循环：**
   - 支持嵌套多个 `v-for`：
     ```vue
     <div v-for="(row, rowIndex) in grid" :key="rowIndex">
       <span v-for="(cell, colIndex) in row" :key="colIndex">
         {{ cell }}
       </span>
     </div>
     ```

---