# Unity 2021.3.7f1c1 Pico VR 空项目  

- VR空项目, 直接拷贝出来, 改项目名称就可以

## SDK Versions:

   - Pico Unity Integration SDK-2.0.5

## Unity Versions：

   - 2021.3.7flc1

## Description：

简单的搭设模板

##  Note:
- **Preview Tool(类似于 Oculus 的 linked)**
  参考Pico官方文档, 目前连上设备休眠或Unity停止运行后会出问题, 需要设备重启
- **版权提示/权限校验**
  菜单栏→PXR_SDK→平台设置, 将User Entitlement Check关闭, 或**Entitlement Check Simulation**√上, 在**Device SN**里填写VR设备序列表, 用安卓adb.exe可以获取



## Help:

Action-based为新版本方法, Device-based为老版本

**XR Origin(VR)** : VR摄像机+两个射线手柄对象

**XR Interaction Manager** : 交互管理类, **XR Origin(VR)**添加会自动添加

**XR Ray Interactor** : 带有射线的手柄模板对象(添加XR Origin(VR) 会自动添加左右手)
Raycast Configuration
直线类型 : 
=Straight Line 红色的线, Max Raycast Distance 修改距离
=Projectile Curve 抛物线
=Bezier Curve 贝塞尔曲线

**XR Direct Interactor** : 不具有射线的手柄模板对象, 需要添加碰撞盒去拿东西



**XR Grab Interactable** : 组件添加后变为手柄可抓取物(包含上面的射线和非射线)
必须有碰撞盒(Collider)进行检测, 建议带刚体Rigibody抓取投掷
Interaction Layer Mask : 设置和手柄匹配的Layer
Throw On Detach : 抛出
=Throw Smoothing Duration : 抛出平滑持续时间
=Throw Smoothing Curve : 
=Throw Velocity Scale : 抛出速度比例
=Throw Angular Velocity Scale : 抛出角速度比例
Attack Transform : 手柄抓取位置, 可以挂在
Use Dvnamic Attach : Enable to make the effective attachment pointbased on the pose of the lnteractor when theselection is made.在进行选择时，可以根据输入者的姿势制作有效的附件点。
=Match Position :匹配位置,在初始化抓取时，匹配接触器的攻击点的位置。这将超越附加变换的位置。
=Match Rotation : 匹配旋转,在初始化抓取时，匹配交互器攻击点的旋转，这将超过附加变换的旋转。
Attach Point Compatibility Mode : 
=Default (Recommended) : 附加点兼容性模式默认(推荐)可插入事件
=Legacy (Obsolete) : 遗产(过时)
Interactable Events : 抓取事件, 如抓取物体，释放物体，抓取物体后按下Trigger键

**XR-UI Canvas** : 创建Canvas只有在此Canvas下的UI组件才能和手柄射线产生正常的交互 (射线长度为30m)

Tracked Device Graphic Raycaster
Check For 2D Occlusion : 检查射线是否被2D遮挡
Check For 3D Occlusion : 检查射线是否被3D遮挡

Input System Ul Actions
Point Action
Left Click Action
Middle Click Action
Right Click Action
Scroll Wheel Action
Navigate Action
Submit Action
Cancel Action