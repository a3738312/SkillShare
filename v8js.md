# 《V8与JS引擎浅析》 赵铮雄 Cocos高级咨询顾问

## V8与JS引擎浅析

#### 从JS层进行优化

## JS Engine

![JS Engine](.gitbook/assets/01%20%282%29.webp)

### V8 JIT编译

![V8 JIT&#x7F16;&#x8BD1;](.gitbook/assets/02%20%281%29.webp) ![V8 JIT&#x7F16;&#x8BD1;](.gitbook/assets/03%20%281%29.webp)

* JIT编译过程

![V8 JIT&#x7F16;&#x8BD1;](.gitbook/assets/04%20%281%29.webp) ![V8 JIT&#x7F16;&#x8BD1;](.gitbook/assets/05%20%281%29.webp) ![V8 JIT&#x7F16;&#x8BD1;](.gitbook/assets/06%20%281%29.webp)

* 进行TurboFan优化的条件

![V8 JIT&#x7F16;&#x8BD1;](.gitbook/assets/07%20%281%29.webp)

* 优化回滚

![V8 JIT&#x7F16;&#x8BD1;](.gitbook/assets/08%20%281%29.webp)

* 需要尽量避免的情况

![V8 JIT&#x7F16;&#x8BD1;](.gitbook/assets/09%20%281%29.webp)

* 如何进行优化

### JSC JIT编译

![JSC JIT&#x7F16;&#x8BD1;](.gitbook/assets/10%20%281%29.webp)

* JSC JIT编译流程

![JSC JIT&#x7F16;&#x8BD1;](.gitbook/assets/11%20%281%29.webp)

* JSC JIT编译不同阶段性能

![JSC JIT&#x7F16;&#x8BD1;](.gitbook/assets/12%20%281%29.webp)

* JSC JIT编译的风险

### 隐藏类

![&#x9690;&#x85CF;&#x7C7B;](.gitbook/assets/13%20%281%29.webp) ![&#x9690;&#x85CF;&#x7C7B;](.gitbook/assets/14%20%281%29.webp) ![&#x9690;&#x85CF;&#x7C7B;](.gitbook/assets/15%20%281%29.webp)

* JS中类的属性会添加到键值对中，若动态添加属性则会创建新的Class键值对，导致后续读取属性数据时性能下降

![&#x9690;&#x85CF;&#x7C7B;](.gitbook/assets/16%20%281%29.webp)

### 内联缓存

![&#x5185;&#x8054;&#x7F13;&#x5B58;](.gitbook/assets/17.webp) ![&#x5185;&#x8054;&#x7F13;&#x5B58;](.gitbook/assets/18%20%281%29.webp) ![&#x5185;&#x8054;&#x7F13;&#x5B58;](.gitbook/assets/19%20%281%29.webp)

* 读取对象属性时会增加一层访问，在频繁调用的计算中，使用局部变量记录对象的属性可以提升读取性能

![&#x5185;&#x8054;&#x7F13;&#x5B58;](.gitbook/assets/20%20%281%29.webp) ![&#x5185;&#x8054;&#x7F13;&#x5B58;](.gitbook/assets/21%20%281%29.webp) ![&#x5185;&#x8054;&#x7F13;&#x5B58;](.gitbook/assets/22%20%281%29.webp)

### 垃圾回收

![&#x5783;&#x573E;&#x56DE;&#x6536;](.gitbook/assets/23%20%281%29.webp) ![&#x5783;&#x573E;&#x56DE;&#x6536;](.gitbook/assets/24%20%281%29.webp) ![&#x5783;&#x573E;&#x56DE;&#x6536;](.gitbook/assets/25%20%281%29.webp) ![&#x5783;&#x573E;&#x56DE;&#x6536;](.gitbook/assets/26%20%281%29.webp)

* 触发GC后会在Eden区寻找依然被引用的对象占用的内存，并将其复制到Suvivor1区，下次触发GC时如果依然被引用，则会复制到Survivor2区，并在1区和2区反复，在其存在时间太长，则会被复制到Old区

![&#x5783;&#x573E;&#x56DE;&#x6536;](.gitbook/assets/27%20%281%29.webp)

* 减少一直存在对象的数量

### 代码优化

#### 类型

![&#x7C7B;&#x578B;](.gitbook/assets/28%20%281%29.webp) ![&#x7C7B;&#x578B;](.gitbook/assets/29%20%281%29.webp)

#### 数组

![&#x6570;&#x7EC4;](.gitbook/assets/30%20%281%29.webp) ![&#x6570;&#x7EC4;](.gitbook/assets/31%20%281%29.webp)

* 数组在JS中也是用和隐藏类一样的方式

![&#x6570;&#x7EC4;](.gitbook/assets/32%20%281%29.webp) ![&#x6570;&#x7EC4;](.gitbook/assets/33.webp) ![&#x6570;&#x7EC4;](.gitbook/assets/34.webp)

* 给数组添加数据时，若当前数组类型无法存储新添加的类型的数据，数组则会进行类型转换，如 `array = [1, 2, 3]` 类型为 `PACKED_SMI_ELEMENTS` 小整数类型，若添加了一个数据 `4.56` 数组类型则会转变为 `PACKED_DOUBLE_ELEMENTS` 浮点数类型，若再添加一个 `'x'` 数组类型又会进行转变，且转换是不可逆的。

![&#x6570;&#x7EC4;](.gitbook/assets/35.webp)

* 数组中有空位的时候，同样也会转换类型

![&#x6570;&#x7EC4;](.gitbook/assets/36.webp) ![&#x6570;&#x7EC4;](.gitbook/assets/37.webp)

* 上面两组代码中，左边的代码因为使用了 `<=` 让数组下标越界了，会增加许多额外的性能损耗

![&#x6570;&#x7EC4;](.gitbook/assets/38.webp)

* -0也会导致数组类型转变为浮点数类型，所以要特别注意

![&#x6570;&#x7EC4;](.gitbook/assets/39.webp)

#### 函数

![&#x51FD;&#x6570;](.gitbook/assets/40.webp) ![&#x51FD;&#x6570;](.gitbook/assets/41.webp) ![&#x51FD;&#x6570;](.gitbook/assets/42.webp) ![&#x51FD;&#x6570;](.gitbook/assets/43.webp) ![&#x51FD;&#x6570;](.gitbook/assets/44.webp) ![&#x51FD;&#x6570;](.gitbook/assets/45.webp) ![&#x51FD;&#x6570;](.gitbook/assets/46.webp) ![&#x51FD;&#x6570;](.gitbook/assets/47.webp) ![&#x51FD;&#x6570;](.gitbook/assets/48.webp) ![&#x51FD;&#x6570;](.gitbook/assets/49.webp) ![&#x51FD;&#x6570;](.gitbook/assets/50.webp) ![&#x51FD;&#x6570;](.gitbook/assets/51.webp)

