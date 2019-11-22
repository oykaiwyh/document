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

10. ```
        // 调用方法：Vue.set( target, key, value )  this.$set会重新渲染视图
    
            // target：要更改的数据源(可以是对象或者数组)
    
            // key：要更改的具体数据
    
            // value ：重新赋的值
    ```
    
    

11. 在vue中，this.data数据时，其实是使用了vue实例代理的data数据，当给其赋值时，数据是数组和对象时，不管数组和对象是否为空，都是返回给原data一个新的数据，数据为字符串和数字时，没有影响，相当于直接修改原始data。可用Vue.set(object ,name ,value) / this.$set(object ,name ,value)直接去操作data数据。

12. @click.stop    阻止上层事件的触发---父包含子，两者都有点击事件，给子加上该属性，就会阻止父的触发

13. Vue.use()      可将一些组件封装为插件的形式来达到加载速度的优化，在使用Vue.use（）时，如果插件是一个对象，必须提供 `install` 方法。如果插件是一个函数，它会被作为 install 方法。install 方法调用时，会将 Vue 作为参数传入。

    该方法需要在调用 `new Vue()` 之前被调用。

    当 install 方法被同一个插件多次调用，插件将只会被安装一次。

14. .sync方法：父组件加上该方法（相当于语法糖）可与子组件进行“数据绑定”，但在子组件中需要给其this.$emit('update:key,newvalue')的方法

15. vue路由跳转之前会执行一个函数beforeRouteLeave（to , from , next ），它在生命周期destroyed（）之前执行

16. 在vue中，只有在使用了vue提供的数组方法和一些深克隆的一些方法filter/map/some等，才会不会再更改数据时改变data（）里的值，同时，在vue中，直接const/let一个data数据时，不管将其封装在一个class类的方法，还是组件调用的方法中，都是一个浅复制的数据，如果数据是一个数组类型的，data数据会改变，但是视图不会及时更新，如果需要视图更新，可使用this.$set（）/ Vue.set方法来实现视图实时更新，然而数据是一个对象时，只要令浅复制的数据改变data里的数据就会及时改变，视图也会跟着更新。

17. vue 中slot插槽的使用：将 `<slot>` 元素作为承载分发内容的出口。

    - 普通插槽：在父组件中一个子组件里去嵌套一些dom元素,元素里不设置任何关于插槽的属性时，dom渲染时，在子组件中mounted时，所有的嵌套dom元素被挂载在子元素插槽slots里（this.$slots的default里）,如果子组件没有使用默认渲染插槽元素<slot></slot>，那么该嵌套元素就不会被渲染。

    - 具名插槽：当给一个嵌套元素给其一个插槽属性name（<div slot='header'/>），子组件拿到各个部分的slot值（<slot name='header'></slot>），dom渲染时，在子组件中mounted时，所有的嵌套dom元素被挂载在子元素插槽slots里（this.$slots的header里，default就消失了）。

    - 作用域插槽：样式由父组件设置，子组件绑定数据。绑定的数据父组件通过<div slot-scope='data'/>获取数据，子组件通过< slot :data='item'/>绑定数据。
      通过slot-scope绑定的元素可以在子组件通过this.$scopedSlots来获取

    - 后备内容：

      `注意事项`：关于this.$slot / this.$scopeedSlots 可查阅https://blog.csdn.net/guzhao593/article/details/89219229

18. `__ob__: Observer`这些数据是vue这个框架对数据设置的监控器，一般都是不可枚举的。console.log这样的打印函数，被打印的变量会执行自身的toString()，这样，即便内部属性是不可枚举，实际上也能看到。

    操作数据的过程中不要删除这些属性：

    因为你已经将数据绑定在了vue之中，vue就肯定要为数据添加监控器的，如果你强制删掉了这些监控器，那么这些数据也就失去了监控，那么你使用vue的意义何在……

    提交数据时可以通过：

    console.log(JSON.stringify(this.obj))，进行获取原始数据对象

    ![](.\image\3963753307-5ba8557ced1fa.png)

19. this.$nextTick()将回调延迟到下次 DOM 更新循环之后执行。
    在create里使用时，等待dom挂载之后在执行this.$nextTick(）回调的内容，可参考https://www.cnblogs.com/jin-zhe/p/9985436.html
    
20. 在vue中，main.js里导入的文件都会在Vue对象创建时执行

### vue提供数组方法

1. pop   删除最后一项
2. push 数组增加一条
3. shift  第一项删除并返回删除数据
4. unshift  增加一条数据并返回长度
5. splice  数组的截取     该方法会改变原始数组splice（index，count，value）从index位置开始count个替换为value      
   @ slice方法返回一个新的数组，不修改原始数组数据   slice（start ，end） 筛选start位置到 end-1 的位置的数组重新组成一个新数组，end未指定时，start开始切分原始数组结束
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

### 方法

#### 数组

- forEach（）                                  //是用来遍历数组的
- Object.keys（）                            //拿到对象中的key或者数组的下标   返回的都是数组
- pop   删除最后一项
- push 数组增加一条
- shift  第一项删除并返回删除数据
- unshift  增加一条数据并返回长度
- splice  数组的截取     该方法会改变原始数组splice（index，count，value）从index位置开始count个替换为value      
  @ slice方法返回一个新的数组，不修改原始数组数据   slice（start ，end） 筛选start位置到 end-1 的位置的数组重新组成一个新数组，end未指定时，start开始切分原始数组结束
- sort 排序
- reserve  取反
- map()                      方法创建一个新数组，其结果是该数组中的每个元素都调用一个提供的函数后返回的结果。
- indexOf()						//查找对应的信息，有就放回位置，没有就返回-1

#### 对象

- hasOwnProperty（）       针对于对象，查询对象是否包含某个属性

#### 其他

1. indexOf()						//查找对应的信息，有就放回位置，没有就返回-1
2. window.navigator.userAgent.toLocaleLowerCase()              //返回浏览器UA标识，即浏览器的内核 版本之类的信息，ie浏览器使用chrome渲染
3. JSON.stringify()                             //将数据json化，深拷贝
4. JSON.parse()                                  //将数据js对象化，深拷贝    必须是json数据
6. Object.keys（）                            //拿到对象中的key或者数组的下标   返回的都是数组
7. Object.keys(list).map(key=> list[key])    将一个{}存储的多数据变为数组[]存储
7. list.sort((A, B) => A.order - B.order)      大小排序
8. 获取对象属性值的两种方式  test['name']/test.name

   9.`Object.assign(A,B)` 方法用于将所有可枚举属性的值从一个B或多个源对象复制到目标对象A。它将返回目标对象A。

 10.filter()                            方法使用指定的函数测试所有元素，并创建一个包含所有通过测试的元素的新数组。

 11.`some()`         方法测试是否至少有一个元素可以通过被提供的函数方法。该方法返回一个Boolean类型的值。

 12.对象内包含对象  二维数组形式获取，var aa= {a:{bb:{}}}    c["a"] ['bb']

### vue-router

1. 安装
2. 配置路由
3. 根目录配置vue.config.js  //runtime
4. 配置路由入口<router-view></router-view>