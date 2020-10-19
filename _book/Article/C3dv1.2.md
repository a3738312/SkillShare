# Cocos Creator 3D v1.2 一探究竟

## UI系统
### 支持3D&2D混合排布
* 3D节点和2D节点不再需要分别放在不同的节点下

### 渲染到RenderTexture
### 自定义材质

## 物理系统
### 当前物理系统架构
![物理系统架构](../Image/v1.2/01.webp)
### 增加简单形状碰撞
![简单形状碰撞](../Image/v1.2/02.webp)
* 增加了对点、线、平面的物理碰撞

### 增加凸边形碰撞
![凸边形碰撞](../Image/v1.2/03.webp)
### 增加静态碰撞
![静态碰撞](../Image/v1.2/04.webp)
* 图中小球不会被大球挤出外部

### 增加地形碰撞
![地形碰撞](../Image/v1.2/05.webp)
### 新增物理约束
![点约束](../Image/v1.2/06.webp)
* 点约束

![铰链约束](../Image/v1.2/07.webp)
* 铰链约束，单方向

### 可视化宏定义
![可视化宏定义](../Image/v1.2/08.webp)
* 部分全局变量可以在项目设置中直接设置

### 动画系统
![动画系统](../Image/v1.2/09.webp)
![morph](../Image/v1.2/10.webp)
* morph需要在组件设置中勾选

![GPU Instanced](../Image/v1.2/11.webp)
* GPU Instanced 优化

![编辑器拷贝](../Image/v1.2/12.webp)
* 动画编辑器批量带曲线拷贝关键帧，还可以跨节点拷贝

### 光影效果
![光影效果](../Image/v1.2/13.webp)
![阴影柔化](../Image/v1.2/14.webp)
* 阴影柔化

![物体光影](../Image/v1.2/15.webp)
* 影子也可以投射到物体上

### 全局雾效
![全局雾效](../Image/v1.2/16.webp)
![全局雾效](../Image/v1.2/17.webp)
![全局雾效](../Image/v1.2/18.webp)
* 通过和摄像机距离计算的雾效

![全局雾效](../Image/v1.2/19.webp)
* 通过地面高度计算的雾效

### 天空盒导入贴图升级
![天空盒导入贴图升级](../Image/v1.2/20.webp)
* 增加天空盒贴图格式

### 改良插件系统
![插件系统](../Image/v1.2/21.webp)
![插件系统](../Image/v1.2/22.webp)
### 新增GameView预览
![GameView预览](../Image/v1.2/23.webp)
* 使用GameView进行预览，可以查看实时节点信息，还可以在编辑器的场景中看游戏的运行，修改场景内物体也会作用到游戏中

### 素材设置可以保存读取
![素材设置可以保存读取](../Image/v1.2/24.webp)
### 自定义构建流程
![自定义构建流程](../Image/v1.2/25.webp)
![自定义构建流程](../Image/v1.2/26.webp)
![自定义构建流程](../Image/v1.2/27.webp)
* 构建过程中添加了若干钩子，可以根据自己需求添加自定义操作

### 增加AppClip发布
![增加AppClip发布](../Image/v1.2/28.webp)
### 渲染设计
![渲染设计](../Image/v1.2/29.webp)
![渲染设计](../Image/v1.2/30.webp)
![渲染设计](../Image/v1.2/31.webp)
* 渲染改为使用原生API，且之后会开放可编程渲染管线  

![渲染设计](../Image/v1.2/32.jpg)
* Cocos Creator 3.0 Beta版发布时间及所作修改

![渲染设计](../Image/v1.2/33.jpg)
* Cocos Creator 3.X 正式版发布时间及所作修改