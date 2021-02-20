## 1.Vue兄弟传参
- vuex
- eventBus
  
## 2.基于vue seo的四种方案
```
vue SPA 单页面应用对SEO不友好，基于此的解决方案有：
1.SSR服务器渲染
2.静态化
3.预渲染prerender-spa-plugin
4.使用Phantomjs针对爬虫做处理
```

[Vue seo解决方案](https://segmentfault.com/a/1190000019623624) 

## 3.vue页面传值
- 标签跳转及传参(router-link)
- js控制跳转路由及传参(this.$touter.push)
- 路由组件传参
  ```
  页面接参方式如下
  使用path + 路径，query + 参数。则用this.$route.query.id取值。
  使用name +路由名称，params + 参数。则用this.$route.params.id取值。
  ```

## 4.`v-show`和`v-if`的区别
**相同点：** v-if与v-show都可以动态控制dom元素显示隐藏

**不同点：** v-if显示隐藏是将dom元素整个添加或删除，而v-show隐藏则是为该元素添加css--display:none，dom元素还在。

## 5.vue中mixin和mixins区别
mixin用于全局混入，会影响到每个组件实例
mixins是最常使用的扩展组件的方式。如果多个组件中有相同的业务逻辑,就可以将这些逻辑剥离出来，通过mixins混入代码，比如上拉下拉加载数据这种逻辑等。另外需要注意的是，minxins混入的钩子函数会先于组件内的钩子函数执行，并且在遇到同名选项的时候也会有选择的进行合并

## 6.this指向问题
es5中，this永远指向最后调用它的那个对象
- 第一种是函数调用模式，当一个函数不是一个对象的属性时，直接作为函数来调用时，this指向全局对象
- 第二种是方法调用模式，如果一个函数作为一个对象的方法来调用，this指向这个对象
- 第三种是构造器调用模式，如果一个函数用new调用时，函数执行前会新创建一个对象，this指向这个新创建的对象
- 第四种是apply，call和bind调用模式，这三个方法都可以显示的指定调用函数的this指向。其中apply方法接收两个参数：一个是this绑定的对象，一个是参数数组。call方法接收的参数，第一个是this绑定的对象，后面的其余参数是传入函数的参数。也就是说在使用call方法时，传递给函数的参数必须逐个列举出来。bind方法通过传入一个对象，返回一个this绑定了传入对象的新函数。这个函数的this指向除了使用new时会被改变，其它情况都不会改变

## 7.new操作符具体干了什么？如何实现
1. 首先创建了一个新的空对象
2. 设置原型，将对象的原型设置为函数的prototype对象
3. 让函数的this指向这个对象，执行构造函数的代码（为这个新对象添加属性）
4. 判断函数的返回值类型，如果是值类型，返回创建的对象。如果是引用类型，就返回这个引用类型的对象  
   实现：
   ``` javascript
   function objectFactory(){
     let newObject=null,
     constructor=Array.prototype.shift.call(arguments);
     result=null;
     if(typeof constructor!=='function'){
       console.log("type error");
       return;
     }
     //新建一个空对象，对象的原型为构造函数的prototype对象
     newObject=Object.create(constructor.prototype);
     //将this指向新建对象并执行函数
     result=constructor.apply(newObject,arguments);
     //判断返回对象
     let flag=result&&(typeof result ==="object" || typeof result=="function");
     //判断返回结果
     return flag?result:newObject
   }
   ```