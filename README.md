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

7. data
   - [demo](https://github.com/dreamITGirl/vueAPI/blob/main/data.html) 
   - 限制：组件中，data必须是一个函数
   - [详细解析](https://cn.vuejs.org/v2/api/#data)：
    - data是Vue实例的数据对象。Vue会递归将data的property转化为getter/setter,从而让data中的property能够响应数据变化。
    对象必须是纯粹的对象(含有0个或多个的key/value对)。 
    **data中创建的实例和created创建的实例有什么区别？**
    - 在浏览器API创建的原生对象，原型上的property会被忽略。也就是说，data只能是数据，不推荐观察拥有状态行为的对象。一旦观察过，
    就无法在根数据对象上添加响应式的property。这也是在data中创建的实例和在created创建的实例的区别

    - 实例创建后，可以通过vm.$data访问原始数据对象。Vue实例代理了data对象上所有的property.
    **为什么组件中的data必须是一个函数？**
    - 当组件被定义，data就必须返回一个初始化数据的对象函数，因为组件可能会被用来创建多个实例，如果data仍然是一个对象，则所有的实例
    都将**共享引入**同一个数据对象！通过提供data函数，每次创建一个新的实例后，我们能够调用data函数，从而返回初始化数据的一个全新的数据副本对象。
    如果有需要的时候，可以通过```vm.$data```传入```JSON.parse(JSON.stringify(...))```得到深拷贝的原始数据对象

    


