#javascript90day-2

偏函数篇

偏函数也是高级函数的一种，即利用函数式编程的思想，创造通过指定部分参数来产生一个新的定制函数的形式

示例：

    function add(a){
      return function(b){
         return a+b;  
      }
    }

    var add5 = add(5);
    var result1 = add5(10);
    console.log("result1:", result);//=>15

    var add7 = add(7);
    var result2 = add7(10);
    consolel.log("result2:",result2);//=>17


    //通用的判断类型模版

    var toString = Object.prototype.toString;

    var isString = function(obj){
      return toString.call(obj) == '[object String]';
    }

    var isFunction = function(obj){
      return toString.call(obj) == '[object Function]';
    }

对上面的Object.prototype.toString进行一下解释：

在toString方法被调用时,会执行下面的操作步骤:

- 如果this的值为undefined,则返回"[object Undefined]".
- 如果this的值为null,则返回"[object Null]".
- 让O成为调用ToObject(this)的结果.
- 让class成为O的内部属性[[Class]]的值.
- 返回三个字符串"[object ", class, 以及 "]"连接后的新字符串.]"


