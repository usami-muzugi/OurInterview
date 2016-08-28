# Java Number类

一般地，当需要使用数字的时候，我们通常使用内置数据类型，如：byte、int、long、double等。

然而，在实际开发过程中，我们经常会遇到需要使用对象，而不是内置数据类型的情形。为了解决这个问题，Java语言为每一个内置数据类型提供了对应的包装类。

所有的包装类（Integer、Long、Byte、Double、Float、Short）都是抽象类Number的子类。

这种由编译器特别支持的包装称为装箱，所以当内置数据类型被当作对象使用的时候，编译器会把内置类型装箱为包装类。相似的，编译器也可以把一个对象拆箱为内置类型。Number类属于java.lang包。

### Number 方法

下面的表中列出的是 Number 子类实现的方法：

| 序号   | 方法与描述                                    |
| ---- | ---------------------------------------- |
| 1    | [xxxValue](#xxxValue)将number对象转换为xxx数据类型的值并返回。 |
| 2    | [compareTo()](http://www.runoob.com/java/number-compareto.html)将number对象与参数比较。 |
| 3    | [equals()](http://www.runoob.com/java/number-equals.html)判断number对象是否与参数相等。 |
| 4    | [valueOf()](http://www.runoob.com/java/number-valueof.html)返回一个 Number 对象指定的内置数据类型 |
| 5    | [toString()](http://www.runoob.com/java/number-tostring.html)以字符串形式返回值。 |
| 6    | [parseInt()](http://www.runoob.com/java/number-parseInt.html)将字符串解析为int类型。 |
| 7    | [abs()](http://www.runoob.com/java/number-abs.html)返回参数的绝对值。 |
| 8    | [ceil()](http://www.runoob.com/java/number-ceil.html)对整形变量向左取整，返回类型为double型。 |
| 9    | [floor()](http://www.runoob.com/java/number-floor.html)对整型变量向右取整。返回类型为double类型。 |
| 10   | [rint()](http://www.runoob.com/java/number-rint.html)返回与参数最接近的整数。返回类型为double。 |
| 11   | [round()](http://www.runoob.com/java/number-round.html)返回一个最接近的int、long型值。 |
| 12   | [min()](http://www.runoob.com/java/number-min.html)返回两个参数中的最小值。 |
| 13   | [max()](http://www.runoob.com/java/number-max.html)返回两个参数中的最大值。 |
| 14   | [exp()](http://www.runoob.com/java/number-exp.html)返回自然数底数e的参数次方。 |
| 15   | [log()](http://www.runoob.com/java/number-log.html)返回参数的自然数底数的对数值。 |
| 16   | [pow()](http://www.runoob.com/java/number-pow.html)返回第一个参数的第二个参数次方。 |
| 17   | [sqrt()](http://www.runoob.com/java/number-sqrt.html)求参数的算术平方根。 |
| 18   | [sin()](http://www.runoob.com/java/number-sin.html)求指定double类型参数的正弦值。 |
| 19   | [cos()](http://www.runoob.com/java/number-cos.html)求指定double类型参数的余弦值。 |
| 20   | [tan()](http://www.runoob.com/java/number-tan.html)求指定double类型参数的正切值。 |
| 21   | [asin()](http://www.runoob.com/java/number-asin.html)求指定double类型参数的反正弦值。 |
| 22   | [acos()](http://www.runoob.com/java/number-acos.html)求指定double类型参数的反余弦值。 |
| 23   | [atan()](http://www.runoob.com/java/number-atan.html)求指定double类型参数的反正切值。 |
| 24   | [atan2()](http://www.runoob.com/java/number-atan2.html)将笛卡尔坐标转换为极坐标，并返回极坐标的角度值。 |
| 25   | [toDegrees()](http://www.runoob.com/java/number-todegrees.html)将参数转化为角度。 |
| 26   | [toRadians()](http://www.runoob.com/java/number-toradians.html)将角度转换为弧度。 |
| 27   | [random()](http://www.runoob.com/java/number-random.html)返回一个随机数。 |

### <A id="xxxValue">xxxValue() 方法</A>

xxxValue() 方法用于将 Number 对象转换为 **xxx ** 数据类型的值并返回。

相关的方法有：

| 类型              | 方法及描述                                  |
| --------------- | -------------------------------------- |
| byte            | **byteValue() :**以 byte 形式返回指定的数值。     |
| abstract double | **doubleValue() :**以 double 形式返回指定的数值。 |
| abstract float  | **floatValue() :**以 float 形式返回指定的数值。   |
| abstract int    | **intValue() :**以 int 形式返回指定的数值。       |
| abstract long   | **longValue() :**以 long 形式返回指定的数值。     |
| short           | **shortValue() :**以 short 形式返回指定的数值。   |

### 参数

以上各函数不接受任何的参数。

### 返回值

转换为 **xxx** 类型后该对象表示的数值。

