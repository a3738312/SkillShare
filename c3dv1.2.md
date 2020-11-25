# 《Cocos Creator 3D v1.2 一探究竟》 刘雅琼 Cocos引擎开发工程师兼任布道师

## UI系统

### 支持3D&2D混合排布

* 3D节点和2D节点不再需要分别放在不同的节点下

### 渲染到RenderTexture

### 自定义材质

## 物理系统

### 当前物理系统架构

![&#x7269;&#x7406;&#x7CFB;&#x7EDF;&#x67B6;&#x6784;](.gitbook/assets/01%20%285%29.webp)

### 增加简单形状碰撞

![&#x7B80;&#x5355;&#x5F62;&#x72B6;&#x78B0;&#x649E;](.gitbook/assets/02%20%284%29.webp)

* 增加了对点、线、平面的物理碰撞

### 增加凸边形碰撞

![&#x51F8;&#x8FB9;&#x5F62;&#x78B0;&#x649E;](.gitbook/assets/03%20%284%29.webp)

### 增加静态碰撞

![&#x9759;&#x6001;&#x78B0;&#x649E;](.gitbook/assets/04%20%284%29.webp)

* 图中小球不会被大球挤出外部

### 增加地形碰撞

![&#x5730;&#x5F62;&#x78B0;&#x649E;](.gitbook/assets/05%20%284%29.webp)

### 新增物理约束

![&#x70B9;&#x7EA6;&#x675F;](.gitbook/assets/06%20%284%29.webp)

* 点约束

![&#x94F0;&#x94FE;&#x7EA6;&#x675F;](.gitbook/assets/07%20%284%29.webp)

* 铰链约束，单方向

### 可视化宏定义

![&#x53EF;&#x89C6;&#x5316;&#x5B8F;&#x5B9A;&#x4E49;](.gitbook/assets/08%20%284%29.webp)

* 部分全局变量可以在项目设置中直接设置

### 动画系统

![&#x52A8;&#x753B;&#x7CFB;&#x7EDF;](.gitbook/assets/09%20%284%29.webp) ![morph](.gitbook/assets/10%20%284%29.webp)

* morph需要在组件设置中勾选

![GPU Instanced](.gitbook/assets/11%20%284%29.webp)

* GPU Instanced 优化

![&#x7F16;&#x8F91;&#x5668;&#x62F7;&#x8D1D;](.gitbook/assets/12%20%283%29.webp)

* 动画编辑器批量带曲线拷贝关键帧，还可以跨节点拷贝

### 光影效果

![&#x5149;&#x5F71;&#x6548;&#x679C;](.gitbook/assets/13%20%283%29.webp) ![&#x9634;&#x5F71;&#x67D4;&#x5316;](.gitbook/assets/14%20%284%29.webp)

* 阴影柔化

![&#x7269;&#x4F53;&#x5149;&#x5F71;](.gitbook/assets/15%20%283%29.webp)

* 影子也可以投射到物体上

### 全局雾效

![&#x5168;&#x5C40;&#x96FE;&#x6548;](.gitbook/assets/16%20%284%29.webp) ![&#x5168;&#x5C40;&#x96FE;&#x6548;](.gitbook/assets/17%20%281%29.webp) ![&#x5168;&#x5C40;&#x96FE;&#x6548;](.gitbook/assets/18%20%282%29.webp)

* 通过和摄像机距离计算的雾效

![&#x5168;&#x5C40;&#x96FE;&#x6548;](.gitbook/assets/19%20%282%29.webp)

* 通过地面高度计算的雾效

### 天空盒导入贴图升级

![&#x5929;&#x7A7A;&#x76D2;&#x5BFC;&#x5165;&#x8D34;&#x56FE;&#x5347;&#x7EA7;](.gitbook/assets/20%20%282%29.webp)

* 增加天空盒贴图格式

### 改良插件系统

![&#x63D2;&#x4EF6;&#x7CFB;&#x7EDF;](.gitbook/assets/21%20%282%29.webp) ![&#x63D2;&#x4EF6;&#x7CFB;&#x7EDF;](.gitbook/assets/22%20%282%29.webp)

### 新增GameView预览

![GameView&#x9884;&#x89C8;](.gitbook/assets/23%20%282%29.webp)

* 使用GameView进行预览，可以查看实时节点信息，还可以在编辑器的场景中看游戏的运行，修改场景内物体也会作用到游戏中

### 素材设置可以保存读取

![&#x7D20;&#x6750;&#x8BBE;&#x7F6E;&#x53EF;&#x4EE5;&#x4FDD;&#x5B58;&#x8BFB;&#x53D6;](.gitbook/assets/24%20%282%29.webp)

### 自定义构建流程

![&#x81EA;&#x5B9A;&#x4E49;&#x6784;&#x5EFA;&#x6D41;&#x7A0B;](.gitbook/assets/25%20%282%29.webp) ![&#x81EA;&#x5B9A;&#x4E49;&#x6784;&#x5EFA;&#x6D41;&#x7A0B;](.gitbook/assets/26%20%282%29.webp) ![&#x81EA;&#x5B9A;&#x4E49;&#x6784;&#x5EFA;&#x6D41;&#x7A0B;](.gitbook/assets/27%20%282%29.webp)

* 构建过程中添加了若干钩子，可以根据自己需求添加自定义操作

### 增加AppClip发布

![&#x589E;&#x52A0;AppClip&#x53D1;&#x5E03;](.gitbook/assets/28%20%282%29.webp)

### 渲染设计

![&#x6E32;&#x67D3;&#x8BBE;&#x8BA1;](.gitbook/assets/29%20%282%29.webp) ![&#x6E32;&#x67D3;&#x8BBE;&#x8BA1;](.gitbook/assets/30%20%282%29.webp) ![&#x6E32;&#x67D3;&#x8BBE;&#x8BA1;](.gitbook/assets/31%20%282%29.webp)

* 渲染改为使用原生API，且之后会开放可编程渲染管线  

![&#x6E32;&#x67D3;&#x8BBE;&#x8BA1;](.gitbook/assets/32.jpg)

* Cocos Creator 3.0 Beta版发布时间及所作修改

![&#x6E32;&#x67D3;&#x8BBE;&#x8BA1;](.gitbook/assets/33.jpg)

* Cocos Creator 3.X 正式版发布时间及所作修改

