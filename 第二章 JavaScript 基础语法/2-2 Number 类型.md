<h1 align="center">JavaScript Number 类型</h1>


## Number 类型总述

JavaScript Number 类型，用于表示整数或小数。不过 Number 类型存在一定的局限性，可参考 IEEE-754标准；该标准规定了 Number 类型数据的区间大小，即 -2<sup>53</sup> ~ 2<sup>53</sup> 之间的整数，超出该数值区间范围，可选用 BigInt 类型进行存储；否则将出现 Infinity 或 - Infinity 情况。



## 数值进制

常见的进制表示由 2进制，8进制，10进制，16进制，32进制，64进制 ...

进制规定了由哪些整数值(0 ~ N-1)构成。对于任何一种进制来说(N进制)，就表示每一位上的数运算时都是逢 N 进一位，即逢 n 进 1 来表示运算操作。



在 ES6 之后的版本，规定了数值进制的前缀符号：

- [x] 2 进制： 0b
- [x] 8 进制： 0o
- [x] 10 进制：默认写法
- [x] 16 进制：0x





## 数值字面量与分隔符

### 整数字面量

``` javascript
10		   // 十进制表示法,默认写法，不带进制前缀符号
0b0011   // 二进制表示法,由 0,1 构成 
0o0326   // 八进制表示法,由 0,1,2,3,4,5,6,7 构成 
0x2353   // 十六进制表示法,以 0x 开头,由 0,1,2,3,4,5,6,7,8,9,a,b,c,d,e,f 构成 

/** 短线分隔符，是阅读更加客观 */
1_000_000  // 1000000
1_00_00 	 // 10000

0b00_11_11_00  // 60
0b0011_1100    // 60
```



### 浮点数字面量

```javascript
3.14 
.12		// 省略整数 0
1.23423e2 // 科学计数法 1.23423 * 10 的 2 次方，即 1.23423 * 10 * 10
1.23E-2 // 科学计数法 -1.23 * 10 的 2 次方，即 -1.23 * 10 * 10
```



## 数值算术运算

### 简单运算

- [x] 加法：+
- [x] 减法： -
- [x] 乘法： *
- [x] 除法：/
- [x] 取余： %
- [x] 幂次方： **



### 数学运算(Math)

- [x] 圆周率：Math.PI
- [x] 自然对数的底数：Math.E
- [x] 自然对数的底数的立方：Math.exp(number)
- [x] n 的自然底数：Math.log(number)
- [x] 以 2 为自然底数的对数：Math.log2(number)
- [x] 以 10 的自然底数的对数：Math.log10(number)
- [x] 0-1 区间内随机值：Math.random()
- [x] 四舍五入接近整数值：Math.round(number)
- [x] 四舍五入向上取整：Math.ceil(number)
- [x] 四舍五入向下取整：Math.floor(number)
- [x] 数的整数值：Math.trunc(number)
- [x] 数的绝对值：Math.abs(number)
- [x] 数的幂次方：Math.pow(base, time)
- [x] 数的平方根：Math.sqrt(number)
- [x] 数的立方根：Math.pow(base,1/time)
- [x] 区间值的最小值：Math.min(num1,num2,num...)
- [x] 区间值的最大值：Math.max(num1,num2,num...)
- [x] 三角函数-数的正弦值：Math.sin(number)
- [x] 三角函数-数的余弦值：Math.cos(number)
- [x] 三角函数-数的正切值：Math.tan(number)
- [x] 三角函数-数的反正弦值：Math.asin(number)
- [x] 三角函数-数的反余弦值：Math.acos(number)
- [x] 三角函数-数的反正切值：Math.atan(number)
- [x] 双曲线函数-数的正弦值：Math.sinh(number)
- [x] 双曲线函数-数的余弦值：Math.cosh(number)
- [x] 双曲线函数-数的正切值：Math.tanh(number)
- [x] 双曲线函数-数的反正弦值：Math.asinh(number)
- [x] 双曲线函数-数的反余弦值：Math.acosh(number)
- [x] 双曲线函数-数的反正切值：Math.atanh(number)



## 常用方法

- [x] 字符转换为整数数值： Number.parseInt(number)
- [x] 字符转换为小数数值：Number.parseFloat(number)
- [x] 数值转换为进制表示法：(number).toString(radix)
- [x] 检测数是否为 NaN：Number.isNaN(number)
- [x] 检测数是否为有效实数：Number.isFinite(number)
- [x] 检测数是否为整数：Number.isInteger(number)
- [x] 检测数是否为安全整数：Number.isSafeInteger(number)



## 探讨运算错误原因

### 经典案例 0.1 + 0.2  != 0.3

```nginx
0.1 + 0.2 			// 0.30000000000000004

(0.1 + 0.2) === 0.3		// false

# 思考： 0.1 + 0.2  的结果由来(0.30000000000000004)

# 具体原因：
计算机在存储数值的时候，会将数值编译成 二进制位数 来存储。我们会发现小数在转换为 二进制位数 时无法完全表示，所以会取近似数来存储。其小数转二进制位数，可通过 乘2取整法 来实现。

比如：0.2 的二进制位数为 0011001100110011...
第一步：0.2 * 2 = 0.4, 取整数 0
第二步：0.4 * 2 = 0.8, 取整数 0
第三步：0.8 * 2 = 1.6, 取整数 1
第四步：0.6 * 2 = 1.2, 取整数 1
第五步：0.2 * 2 = 0.4, 取整数 0
第六步：0.4 * 2 = 0.4, 取整数 0
由规律得出：它将无限循环 0011 ...

比如 0.25 的二进制位数为 01
第一步：0.25 * 2 = 0.5, 取整数 0
第二步：0.5 * 2 = 1.0, 取整数 1

```



