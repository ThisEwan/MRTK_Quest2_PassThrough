# MRTK_Quest2_PassThrough
使用MRTK框架，并且开启Quest2的Passthrough效果

## quest2 passthrough官方文档
- https://developer.oculus.com/documentation/unity/unity-passthrough/


## 开启步骤

1. 确认MRTK Fundation 导入成功;
2. 切换至Android Platform;
3. Project Settings - Player - Android - Other Settings:
   1. Color space 改为 Linear;
   2. Scripting backend 改为 IL2CPP;
   3. Target Architectures 改为ARM64;
4. Project Settings - XR Plugin-in Management启用，并且勾选Android下的Oculus;
5. Package Manager中安装Oculus Intergration（该Package需要自行去Unity Asset Store中添加到自己的账号内）;
6. MixedReality Toolkit中Camera - DisplaySettings，把Background Color的透明度改为0;
7. 找到MixedReality Toolkit中Input - Input Data Provider - XR SDK Oculus Device Manager的Ovr Camera Rig Prefab:
   1. 勾选该Prefab身上的OVR Manager脚本里的Quest Feature - General - Passthrought Capability Enable;
   2. 勾选Insight Passthrough - Enable Passthrough;
   3. 给该对象加上OVR Passthrough Layer 组件，并且修改Placement为Underlay;
8. 点击Oculus-Tools-Create store-compatible AndroidManifest.xml 来开启passthrough权限;
9. 点击Mxied Reality-Toolkit-Utilities-Oculus-Integrate Oculus Integration Unity Modules;
10. 检查是否有Postprocess组件存在，Unity的Postprocess组件会让passthrough效果失效；（passthrough效果猜测也是基于后处理实现，与Unity的后处理插件有冲突）;