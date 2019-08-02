### vue指令

1. v-for  					循環列表

2. v-on ：name        綁定事件   name：click/onFocus....    简写：” @click “

3. v-model              雙向綁定

4. v-html      一段h5

5. v-text        一段内容

6. v-bind :name    绑定一个内容    name:内容名/class/    可简写为  ： ‘’ :name“

7. v-if     条件渲染   不存在dom节点，

8. v-show   显示渲染  存在dom节点  但display=none  性能相对于v-if好一点，不会频繁的操作dom

9. v-once  将内容放在内存中，提高性能

10. `

    ```
            // 调用方法：Vue.set( target, key, value )  this.$set会重新渲染视图
    
            // target：要更改的数据源(可以是对象或者数组)
    
            // key：要更改的具体数据
    
            // value ：重新赋的值
    ```

    `

11. 在vue中，this.data数据时，其实是使用了vue示例代理的data数据，当给其赋值时，数据是数组和对象时，不管数组和对象是否为空，都是返回给原data一个新的数据，数据为字符串和数字时，没有影响，相当于直接修改原始data。可用Vue.set(object ,name ,value) / this.$set(object ,name ,value)直接去操作data数据。

### vue提供数组方法

1. pop   删除最后一项
2. push 数组增加一条
3. shift  第一项删除并返回删除数据
4. unshift  增加一条数据并返回长度
5. splice  数组的截取
6. sort 排序
7. reserve  取反

### 注意事项

1. 子组件中data一定要返回一个函数
2. 在table ul ol中子列表作为一个组件时，需在组件引用加上is属性来解决渲染bug  example：<tr is='子组件名'>
3. ref指定节点名，this.$refs.'name'获取dom节点
4. 在methods里去获取值时需要使用this关键字
5. 非props特性：子组件不接受父组件传递过来的属性-----1.属性会被渲染在子组件dom标签上 2.不能显示父组件传递过来的值
6. 在插槽中，想直接渲染原生的html需要在加上单引号或者双引号
7. v-html不支持模板字符串
8. 加上标签指向for属性，for指向的是一个标签的id值
9. 在父子组件相互调用其方法时，父组件只需在子组件上定义ref再通过其$refs在对应其方法即可，对于子组件只需使用$parent对应其方法/使用$emit派发监听事件

### vue-router

1. 安装
2. 配置路由
3. 根目录配置vue.config.js  //runtime
4. 配置路由入口<router-view></router-view>