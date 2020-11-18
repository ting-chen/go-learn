
**1. 属性的公有私有通过命名来区分：**

 >   常量、变量、类型、函数名、结构字段 以一个大写字母开头，如：Group1，那么使用这种形式的标识符的对象就可以被外部包的代码所使用（客户端程序需要先导入这个包），这被称为导出（像面向对象语言中的 public）；
标识符如果以小写字母开头，则对包外是不可见的，但是他们在整个包的内部是可见并且可用的

**2. 需要注意的是 { 不能单独放在一行，所以以下代码在运行时会产生错误**

**3. 25 个关键字或保留字：**
> break	default	func	interface	select
  case	defer	go	map	struct
  chan	else	goto	package	switch
  const	fallthrough	if	range	type
  continue	for	import	return	var

*除了以上介绍的这些关键字，Go 语言还有 36 个预定义标识符：*

> append	bool	byte	cap	close	complex	complex64	complex128	uint16
copy	false	float32	float64	imag	int	int8	int16	uint32
int32	int64	iota	len	make	new	nil	panic	uint64
print	println	real	recover	string	true	uint	uint8	uintptr

**4. 特殊数据类型:**
```
Channel 类型：
 In the channel, the send and receive operation block until another side is not ready by default.
 It allows goroutine to synchronize with each other without explicit locks or condition variable
 
切片类型：
 初步理解就是长度不固定的数据结构

接口类型：
 待理解

complex64：
 32 位实数和虚数

complex128：
 64 位实数和虚数
 
rune：
 类似 int32
 
uintptr：
 无符号整型，用于存放一个指针
```
**5. 变量声明**
> var identifier type

> var v_name = value

> v_name := value

> iota 可理解为 const 语句块中的行索引
*交换两个变量的值，则可以简单地使用 a, b = b, a，两个变量的类型必须是相同。
空白标识符 _ 也被用于抛弃值，如值 5 在：_, b = 5, 7 中被抛弃。
_ 实际上是一个只写变量，你不能得到它的值。这样做是因为 Go 语言中你必须使用所有被声明的变量*

**6.条件语句**
``` go
select{
  statement(s);      
    case communication clause  :
       statement(s);
    /* 你可以定义任意数量的 case */
    default : /* 可选 */
       statement(s);
}
每个 case 必须是一个通信操作，要么是发送要么是接收。

select 随机执行一个可运行的 case。如果没有 case 可运行，它将阻塞，直到有 case 可运行
```
