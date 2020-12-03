# 《Cocos Creator 引擎规划路线前瞻》 Panda Cocos引擎技术总监

## Cocos 3D核心设计和路线图

![&#x5F15;&#x64CE;&#x67B6;&#x6784;](.gitbook/assets/01%20%283%29.webp)

* 引擎100%开源，开发者可以可以针对自己需求自定义引擎

![&#x5F15;&#x64CE;&#x67B6;&#x6784;](.gitbook/assets/02%20%282%29.webp)

* 新的多平台引擎架构

## 基于物理的渲染

![&#x5F15;&#x64CE;&#x67B6;&#x6784;](.gitbook/assets/03%20%282%29.webp)

### 基于物理的光源

![&#x57FA;&#x4E8E;&#x7269;&#x7406;&#x7684;&#x5149;&#x6E90;](.gitbook/assets/04%20%282%29.webp)

* 根据现实中光源的各种属性来制作光源效果

### 基于物理的摄像机

![&#x57FA;&#x4E8E;&#x7269;&#x7406;&#x7684;&#x6444;&#x50CF;&#x673A;](.gitbook/assets/05%20%282%29.webp)

* 按照现实中摄像机的参数来设置相机参数，并且设置可以保存，不会因为改一个摄像机导致其他摄像机渲染偏差

## Cocos Creator的优势

![Cocos Creator&#x7684;&#x4F18;&#x52BF;](.gitbook/assets/06%20%282%29.webp)

## Cocos Creator面向未来的渲染器设计

![Cocos Creator&#x9762;&#x5411;&#x672A;&#x6765;&#x7684;&#x6E32;&#x67D3;&#x5668;&#x8BBE;&#x8BA1;](.gitbook/assets/07%20%282%29.webp) ![Cocos Creator&#x9762;&#x5411;&#x672A;&#x6765;&#x7684;&#x6E32;&#x67D3;&#x5668;&#x8BBE;&#x8BA1;](.gitbook/assets/08%20%282%29.webp)

* 接口尽量贴近Vulkan设计

![Cocos Creator&#x9762;&#x5411;&#x672A;&#x6765;&#x7684;&#x6E32;&#x67D3;&#x5668;&#x8BBE;&#x8BA1;](.gitbook/assets/09%20%282%29.webp) ![Cocos Creator&#x9762;&#x5411;&#x672A;&#x6765;&#x7684;&#x6E32;&#x67D3;&#x5668;&#x8BBE;&#x8BA1;](.gitbook/assets/10%20%282%29.webp)

* 引擎兼容高级特性，Cocos Shader使用GLSL 300 ES规则，开发者只需要写这一种Shader，引擎会针对不同平台编译成各种版本来使用

![Cocos Creator&#x9762;&#x5411;&#x672A;&#x6765;&#x7684;&#x6E32;&#x67D3;&#x5668;&#x8BBE;&#x8BA1;](.gitbook/assets/11%20%282%29.webp)

* 水体效果

## Cocos AR

![Cocos AR](.gitbook/assets/12.jpg) ![Cocos AR](.gitbook/assets/13.jpg) ![Cocos AR](.gitbook/assets/14%20%282%29.webp)

* 使用相机拍到的照片生成游戏地图，并在此之上进行游戏

![&#x6E32;&#x67D3;&#x8BBE;&#x8BA1;](.gitbook/assets/15.jpg)

* 使用可编程渲染管线渲染出的游戏画面

![&#x7ED3;&#x8BED;](.gitbook/assets/16%20%282%29.webp)

