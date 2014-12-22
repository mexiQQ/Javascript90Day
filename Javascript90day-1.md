# Javascript90Day-1

今天来学习两点：

- javascript 高级函数
- ECMA5中的sort函数

## javascript 高级函数

  就是采用了函数式编程思想的函数

## 之所以拿出 sort 函数来讲，就是因为原生API中 sort 函数体现了这种思想

arrayObject.sort(sortby)

如果调用该方法时没有使用参数，将按字母顺序对数组中的元素进行排序，说得更精确点，是按照字符编码的顺序进行排序。要实现这一点，首先应把数组的元素都转换成字符串（如有必要），以便进行比较。
如果想按照其他标准进行排序，就需要提供比较函数，该函数要比较两个值，然后返回一个用于说明这两个值的相对顺序的数字。比较函数应该具有两个参数 a 和 b，其返回值如下：

- 若 a 小于 b，在排序后的数组中 a 应该出现在 b 之前，则返回一个小于 0 的值。
- 若 a 等于 b，则返回 0。
- 若 a 大于 b，则返回一个大于 0 的值。

一个特殊的例子：

    //此例子表明默认采取字符编码排序，所以5在40后面
    <script type="text/javascript">

    var arr = new Array(6)
    arr[0] = "10"
    arr[1] = "5"
    arr[2] = "40"
    arr[3] = "25"
    arr[4] = "1000"
    arr[5] = "1"

    document.write(arr + "<br />")
    document.write(arr.sort())

    </script>

    //正确的比较方法
    <script type="text/javascript">
    function sortNumber(a,b)
    {
    return a - b
    }

    var arr = new Array(6)
    arr[0] = "10"
    arr[1] = "5"
    arr[2] = "40"
    arr[3] = "25"
    arr[4] = "1000"
    arr[5] = "1"

    document.write(arr + "<br />")
    document.write(arr.sort(sortNumber))

    </script>
