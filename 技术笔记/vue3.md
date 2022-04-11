# **<p style="color:green">VUE3</p>**

## 新增

1. 组合式API
    1. setup选项
    2. ref 响应式变量<br/>
    <mark style="background-color: lightblue;">(ref 接收参数并将其包裹在一个带有 value property 的对象中返回，然后可以使用该 property 访问或更改响应式变量的值)</mark>

        ```javascript
        import { ref } from 'vue'

        const counter = ref(0)

        console.log(counter) // { value: 0 }
        console.log(counter.value) // 0

        counter.value++
        console.log(counter.value) // 1
        ```
    3. 在 setup 内注册生命周期钩子
        1. 组合式 API 上的生命周期钩子与选项式 API 的名称相同，但前缀为 on：即 mounted 看起来会像 onMounted

    4. watch 响应式更改
        1. 一个想要侦听的响应式引用或 getter 函数
        2. 一个回调
        3. 可选的配置选项

        ```javascript
        import { ref, watch } from 'vue'

        const counter = ref(0)
        watch(counter, (newValue, oldValue) => {
            console.log('The new counter value is: ' + counter.value)
        })
        ```
    5. 目的<br/>
    <mark style="background-color: lightblue;">可以是功能复用</mark>