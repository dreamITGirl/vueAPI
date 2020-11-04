### Vue官网API理解

**主要是对应vue官网的API写自己的理解及用法。开发中会遇到类似的复杂的用法**

## 目录

1. vue.extend(options)
   (demo)[https://github.com/dreamITGirl/vueAPI/blob/main/extend.html]
   用法:
   使用基础 Vue 构造器，创建一个“子类”。参数是一个包含组件选项的对象。
   注意点：
   vue.extend中的data必须是一个函数。和组件中的data类型一样

2. vue.nextTick([callback,context]
   (demo)[https://github.com/dreamITGirl/vueAPI/blob/main/nextTick.html] 
   用法：
   在下次 DOM 更新循环结束之后执行延迟回调。在修改数据之后立即使用这个方法，获取更新后的 DOM。
