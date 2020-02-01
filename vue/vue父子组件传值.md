> Vue的特点就是组件式开发，弄清楚组件之间的通信，才能让开发更加顺手。



vue组件与组件之间有如下图所示，基本就分为三种关系。

- A与B，B与C，B与D的父子关系
- A与C，A与D的祖孙关系
- C与D的兄弟关系

![vue组件关系](/Users/fanlinhao/Documents/Web/assets/vue.png)

## 父子关系的组件传值

#### 1. props/$emit（props down , events up）

子组件通过props接受父组件的值，props 只可以从上一级组件传递到下一级组件（父子组件），即所谓的单向数据流，而且 props 只读，不可被修改，所有修改都会失效并警告。修改props只能通过$emit事件到父组件中。

```vue
// 父组件中
<template>
  <div class="section">
    <com-article :articles="articleList" @onEmitIndex="onEmitIndex"></com-article>
    <p>{{currentIndex}}</p>
  </div>
</template>

<script>
import comArticle from './test/article.vue'
export default {
  name: 'HelloWorld',
  components: { comArticle },
  data() {
    return {
      currentIndex: -1,
      articleList: ['红楼梦', '西游记', '三国演义']
    }
  },
  methods: {
    onEmitIndex(idx) {
      this.currentIndex = idx
    }
  }
}
</script>

// 子组件 article.vue
<template>
  <div>
    <div v-for="(item, index) in articles" :key="index" @click="emitIndex(index)">								{{item}}
  	</div>
  </div>
</template>

<script>
export default {
  props: ['articles'],
  methods: {
    emitIndex(index) {
      this.$emit('onEmitIndex', index)
    }
  }
}
</script>
```

