# Java Number类

一般地，当需要使用数字的时候，我们通常使用内置数据类型，如：byte、int、long、double等。

然而，在实际开发过程中，我们经常会遇到需要使用对象，而不是内置数据类型的情形。为了解决这个问题，Java语言为每一个内置数据类型提供了对应的包装类。

所有的包装类（Integer、Long、Byte、Double、Float、Short）都是抽象类Number的子类。

这种由编译器特别支持的包装称为装箱，所以当内置数据类型被当作对象使用的时候，编译器会把内置类型装箱为包装类。相似的，编译器也可以把一个对象拆箱为内置类型。Number类属于java.lang包。

### Number 方法

下面的表中列出的是 Number 子类实现的方法：

| 序号   | 方法与描述                                    |
| ---- | ---------------------------------------- |
| 1    | [xxxValue()](#user-content-xxxValue)将number对象转换为xxx数据类型的值并返回。 |
| 2    | [compareTo()](#user-content-compareTo)将number对象与参数比较。 |
| 3    | [equals()](#user-content-equals)判断number对象是否与参数相等。 |
| 4    | [valueOf()](#user-content-valueOf)返回一个 Number 对象指定的内置数据类型 |
| 5    | [toString()](#user-content-toString)以字符串形式返回值。 |
| 6    | [parseInt()](#user-content-parseInt)将字符串解析为int类型。 |
| 7    | [abs()](#user-content-abs)返回参数的绝对值。      |
| 8    | [ceil()](#user-content-ceil)对整形变量向左取整，返回类型为double型。 |
| 9    | [floor()](#user-content-floor)对整型变量向右取整。返回类型为double类型。 |
| 10   | [rint()](#user-content-rint)返回与参数最接近的整数。返回类型为double。 |
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

### <a name="xxxValue">xxxValue()</a>



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

#### 参数

以上各函数不接受任何的参数。

#### 返回值

转换为 **xxx** 类型后该对象表示的数值。

### <a name="compareTo">compareTo()</a>

ompareTo() 方法用于将 Number 对象与方法的参数进行比较。可用于比较 Byte, Long, Integer等。

该方法用于两个相同数据类型的比较，两个不同类型的数据不能用此方法来比较。

#### 语法

```java
public int compareTo( NumberSubClass referenceName )
```

#### 参数

**referenceName** -- 可以是一个 Byte, Double, Integer, Float, Long 或 Short 类型的参数。

#### 返回值

- 如果指定的数与参数相等返回0。
- 如果指定的数小于参数返回 -1。
- 如果指定的数大于参数返回 1。

### <a name="equals">equals()</a>

equals() 方法用于判断 Number 对象与方法的参数进是否相等。

#### 语法

```java
public boolean equals(Object o)
```

#### 参数

**o** -- 任何对象。

#### 返回值

如 Number 对象不为 Null，且与方法的参数类型与数值都相等返回 True，否则返回 False。

Double 和 Float 对象还有一些额外的条件，可以参阅 API 手册：[JDK 1.6](http://www.runoob.com/manual/jdk1.6/)。

### <a name="valueOf">valueOf()</a>

valueOf() 方法用于返回给定参数的原生 Number 对象值，参数可以是原生数据类型, String等。

该方法是静态方法。该方法可以接收两个参数一个是字符串，一个是基数。

#### 语法

该方法有以下几种语法格式：

```java
static Integer valueOf(int i)
static Integer valueOf(String s)
static Integer valueOf(String s, int radix)
```

#### 参数

- **i** -- Integer 对象的整数。
- **s** -- Integer 对象的字符串。
- **radix** --在解析字符串 s 时使用的基数，用于指定使用的进制数。

#### 返回值

- **Integer valueOf(int i)：**返回一个表示指定的 int 值的 Integer 实例。
- **Integer valueOf(String s):**返回保存指定的 String 的值的 Integer 对象。
- **Integer valueOf(String s, int radix):** 返回一个 Integer 对象，该对象中保存了用第二个参数提供的基数进行解析时从指定的 String 中提取的值。

### <a name="toString">toString()</a>

valueOf() 方法用于返回以一个字符串表示的 Number 对象值。

如果方法使用了原生的数据类型作为参数，返回原生数据类型的 String 对象值。

如果方法有两个参数， 返回用第二个参数指定基数表示的第一个参数的字符串表示形式。

#### 语法

以 String 类为例，该方法有以下几种语法格式：

```java
String toString()
static String toString(int i)
```

#### 参数

- **i** -- 要转换的整数。

#### 返回值

- **toString():** 返回表示 Integer 值的 String 对象。
- **toString(int i):** 返回表示指定 int 的 String 对象。

### <a name="parseInt">parseInt()</a>

parseInt() 方法用于将字符串参数作为有符号的十进制整数进行解析。

如果方法有两个参数， 使用第二个参数指定的基数，将字符串参数解析为有符号的整数。

#### 语法

所有 Number 派生类 parseInt 方法格式类似如下：

```java
static int parseInt(String s)

static int parseInt(String s, int radix)
```

#### 参数

- **s** -- 十进制表示的字符串。
- **radix** -- 指定的基数。

#### 返回值

- **parseInt(String s):** 返回用十进制参数表示的整数值。
- **parseInt(int i):** 使用指定基数的字符串参数表示的整数 (基数可以是 10, 2, 8, 或 16 等进制数) 。

### <a name="abs">abs()</a>

abs() 返回参数的绝对值。参数可以是 int, float, long, double, short, byte类型。

#### 语法

各个类型的方法格式类似如下：

```java
double abs(double d)
float abs(float f)
int abs(int i)
long abs(long lng)
```

#### 参数

- 任何原生数据类型。

#### 返回值

返回参数的绝对值。

### <a name="ceil">ceil()</a>

ceil() 方法可对一个数进行上舍入，返回值大于或等于给定的参数。

#### 语法

该方法有以下几种语法格式：

```java
double ceil(double d)

double ceil(float f)
```

#### 参数

- double 或 float 的原生数据类型。

#### 返回值

返回 double 类型，返回值大于或等于给定的参数。

### <a name="floor">floor()</a>

floor() 方法可对一个数进行下舍入，返回给定参数最大的整数，该整数小于或等给定的参数。

#### 语法

该方法有以下几种语法格式：

```java
double floor(double d)

double floor(float f)
```

#### 参数

- double 或 float 的原生数据类型。

#### 返回值

返回 double 类型数组，小于或等于给定的参数。

### <a name="rint">rint()</a>

rint() 方法返回最接近参数的整数值。

#### 语法

该方法有以下几种语法格式：

```java
double rint(double d)
```

#### 参数

- double 原始数据类型。

#### 返回值

返回 double 类型数组，是最接近参数的整数值。