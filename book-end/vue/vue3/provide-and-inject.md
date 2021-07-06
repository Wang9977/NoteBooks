# provide&inject

provide/inject

* Vue 2.2.0 新增的API
* 功能：用于祖先组件向后代组件传值
* 使用方法

  * 普通

  ```text
  // 祖先组件
  <script>
      provide:{
          usr:'wy'
      }
  </script>
  ```

  ```text
  // 后代组件
  <script>
      inject:['usr']
  </script>
  ```

  * 响应式 利用computed属性

    ```javascript
    // 祖先组件
    provide() {
            return {
                user: 'wy',
                length: computed(()=> this.todos.length)
            }
    },
    ```

    ```text
    <template>
      <div>
        <h2>孙子组件</h2>
        {{user}}
        {{length.value}}
      </div>
    </template>
    <script>
    export default {
        inject:['user','length'],
    }
    </script>
    ```

