### Vue官网API理解

**主要是对应vue官网的API写自己的理解及用法。开发中会遇到类似的复杂的用法**

## 目录

1. vue.extend(options)

    - [demo](https://github.com/dreamITGirl/vueAPI/blob/main/extend.html)
    - 用法:
    使用基础 Vue 构造器，创建一个“子类”。参数是一个包含组件选项的对象。
    - 注意点：
    vue.extend中的data必须是一个函数。和组件中的data类型一样

2. vue.nextTick([callback,context]

    - [demo](https://github.com/dreamITGirl/vueAPI/blob/main/nextTick.html)
    - 用法：
    在下次 DOM 更新循环结束之后执行延迟回调。在修改数据之后立即使用这个方法，获取更新后的 DOM。

3. vue.set(target,proxyName/index,value)

   - [demo](https://github.com/dreamITGirl/vueAPI/blob/main/set.html)
   - 用法：
   向响应式对象中添加一个 property，并确保这个新 property 同样是响应式的，且触发视图更新。
   它必须用于向响应式对象上添加新 property，因为 Vue 无法探测普通的新增 property 
   - 注意点：
   注意对象不能是 Vue 实例，或者 Vue 实例的根数据对象。

4. vue.delete(target,proxyName/index)
    - [demo](https://github.com/dreamITGirl/vueAPI/blob/main/delete.html)
    - 用法：
    删除对象的 property。如果对象是响应式的，确保删除能触发更新视图。
    这个方法主要用于避开 Vue 不能检测到 property 被删除的限制，但是你应该很少会使用它。
    - 注意点：
    目标对象不能是一个 Vue 实例或 Vue 实例的根数据对象。

5. vue.directive(id,[definition]) 和 vue.filter(id,[definition]) 类似
    - [demo](https://github.com/dreamITGirl/vueAPI/blob/main/directive.html)
    - 用法：注册全局/局部指令，自定义指令
    - 注意点都写在demo里。如果全局使用，建议封装成单个文件，按需引入即可。

6. vue.filter(id,[definition])
    - [demo](https://github.com/dreamITGirl/vueAPI/blob/main/filter.html)
    - 用法：注册全局/局部指令，自定义指令
    - 使用场景：
        - 用来格式化展示数据


