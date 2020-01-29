> 
> Markdown是一种纯文本格式的标记语言。通过简单的标记语法，使得普通文本内容具有一定的格式。
>
> 本文只要是介绍一些基本的语法，现在好多编辑器都可以编辑md文档，我个人推荐 [typora](https://www.typora.io/)。



## 一、引用

引用，文字前面加上`>`即可，也可以嵌套使用

示例：

~~~
>这是一个引用
>>嵌套的引用
~~~

效果：

>这是一个引用
>
>>嵌套的引用



## 二、标题

标题，文字前面加 # 来表示，# 代表一级标题，## 代表二级标题，以此类推...

示例：

```
# 一级标题
## 二级标题
### 三级标题
#### 四级标题
```

效果：

# 一级标题
## 二级标题
### 三级标题

#### 四级标题



## 三、字体

加粗字体左右两边加上两个`*`

倾斜字体两个加上一个`*`

倾斜加粗字体两边加上三个`*`

加删除线的字体两边加上两个`~`

示例：

```
**加粗文字**
*倾斜文字*
***斜体加粗文字***
~~加删除线文字~~
```

效果：

**加粗文字**
*倾斜文字*
***斜体加粗文字***
~~加删除线文字~~



## 四、分割线

标题下面都是自带分割线的，但有时需要自己加上需要怎么半，三个或三个以上的 `-` 或者 `*` 都可以。

示例：

~~~
---
***
~~~

效果：

---
***



## 五、图片

`![图片alt](图片地址 "图片title")`，alt就是显示在图片下面的文字，title是图片标题，当鼠标移到图片上时显示的内容，title可加可不加

示例：

```
![git](https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1580285637076&di=842eb15eed482d2d1ca9cd6c9e7e7c4b&imgtype=0&src=http%3A%2F%2Fpic2.zhimg.com%2Fv2-d37c3ddfbf67ac4e568adc623d923b73_1200x500.gif "git")
```

效果：

![git](https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1580285637076&di=842eb15eed482d2d1ca9cd6c9e7e7c4b&imgtype=0&src=http%3A%2F%2Fpic2.zhimg.com%2Fv2-d37c3ddfbf67ac4e568adc623d923b73_1200x500.gif "git")



## 六、超链接

`[超链接名](超链接地址 "超链接title")`

示例：

```
[百度](https://www.baidu.com/)
```

效果：

[百度](https://www.baidu.com/)



## 七、代码块

- 少量代码嵌套在文字段中，使用``。

  示例：

  ```
  我是文字段中的`代码`，`console.log('hello word!')`
  ```

  效果：

  我是文字段中的`代码`，`console.log('hello word!')`

- 代码段则是开头结尾都用```包起来，切开头结尾单独占一行

  示例：

  ```
  ​```
  console.log('hello')
  console.log('word')
  console.log('!')
  ​```
  ```

  效果：

  ```
  console.log('hello')
  console.log('word')
  console.log('!')
  ```



## 八、列表

* 无序列表

  使用`- ` `+ ` `*` 任何一种作为标记即可

  示例：

  ```
  - test
  + test
  * test
  ```

  效果：

  - test
  + test

  * test

* 有序列表

  使用数字加上英文的`.`即可

  示例：

  ```
  1. test
  2. test
  3. test
  ```

  效果：

  1. test
  2. test
  3. test