# V8与JS引擎浅析
### 从JS层进行优化

# JS Engine
![JS Engine](../Image/V8JS/01.webp)

## V8 JIT编译
![V8 JIT编译](../Image/V8JS/02.webp)
![V8 JIT编译](../Image/V8JS/03.webp)
* JIT编译过程

![V8 JIT编译](../Image/V8JS/04.webp)
![V8 JIT编译](../Image/V8JS/05.webp)
![V8 JIT编译](../Image/V8JS/06.webp)
* 进行TurboFan优化的条件

![V8 JIT编译](../Image/V8JS/07.webp)
* 优化回滚

![V8 JIT编译](../Image/V8JS/08.webp)
* 需要尽量避免的情况

![V8 JIT编译](../Image/V8JS/09.webp)
* 如何进行优化

## JSC JIT编译
![JSC JIT编译](../Image/V8JS/10.webp)
* JSC JIT编译流程

![JSC JIT编译](../Image/V8JS/11.webp)
* JSC JIT编译不同阶段性能

![JSC JIT编译](../Image/V8JS/12.webp)
* JSC JIT编译的风险

## 隐藏类
![隐藏类](../Image/V8JS/13.webp)
![隐藏类](../Image/V8JS/14.webp)
![隐藏类](../Image/V8JS/15.webp)
* JS中类的属性会添加到键值对中，若动态添加属性则会创建新的Class键值对，导致后续读取属性数据时性能下降

![隐藏类](../Image/V8JS/16.webp)

## 内联缓存
![内联缓存](../Image/V8JS/17.webp)
![内联缓存](../Image/V8JS/18.webp)
![内联缓存](../Image/V8JS/19.webp)
* 读取对象属性时会增加一层访问，在频繁调用的计算中，使用局部变量记录对象的属性可以提升读取性能

![内联缓存](../Image/V8JS/20.webp)
![内联缓存](../Image/V8JS/21.webp)
![内联缓存](../Image/V8JS/22.webp)

## 垃圾回收
![垃圾回收](../Image/V8JS/23.webp)
![垃圾回收](../Image/V8JS/24.webp)
![垃圾回收](../Image/V8JS/25.webp)
![垃圾回收](../Image/V8JS/26.webp)
* 触发GC后会在Eden区寻找依然被引用的对象占用的内存，并将其复制到Suvivor1区，下次触发GC时如果依然被引用，则会复制到Survivor2区，并在1区和2区反复，在其存在时间太长，则会被复制到Old区

![垃圾回收](../Image/V8JS/27.webp)
* 减少一直存在对象的数量

## 代码优化
### 类型
![类型](../Image/V8JS/28.webp)
![类型](../Image/V8JS/29.webp)
### 数组
![数组](../Image/V8JS/30.webp)
![数组](../Image/V8JS/31.webp)
* 数组在JS中也是用和隐藏类一样的方式

![数组](../Image/V8JS/32.webp)
![数组](../Image/V8JS/33.webp)
![数组](../Image/V8JS/34.webp)
* 给数组添加数据时，若当前数组类型无法存储新添加的类型的数据，数组则会进行类型转换，如 `array = [1, 2, 3]` 类型为 `PACKED_SMI_ELEMENTS` 小整数类型，若添加了一个数据 `4.56` 数组类型则会转变为 `PACKED_DOUBLE_ELEMENTS` 浮点数类型，若再添加一个 `'x'` 数组类型又会进行转变，且转换是不可逆的。

![数组](../Image/V8JS/35.webp)
* 数组中有空位的时候，同样也会转换类型

![数组](../Image/V8JS/36.webp)
![数组](../Image/V8JS/37.webp)
* 上面两组代码中，左边的代码因为使用了 `<=` 让数组下标越界了，会增加许多额外的性能损耗

![数组](../Image/V8JS/38.webp)
* -0也会导致数组类型转变为浮点数类型，所以要特别注意

![数组](../Image/V8JS/39.webp)

### 函数
![函数](../Image/V8JS/40.webp)
![函数](../Image/V8JS/41.webp)
![函数](../Image/V8JS/42.webp)
![函数](../Image/V8JS/43.webp)
![函数](../Image/V8JS/44.webp)
![函数](../Image/V8JS/45.webp)
![函数](../Image/V8JS/46.webp)
![函数](../Image/V8JS/47.webp)
![函数](../Image/V8JS/48.webp)
![函数](../Image/V8JS/49.webp)
![函数](../Image/V8JS/50.webp)
![函数](../Image/V8JS/51.webp)
