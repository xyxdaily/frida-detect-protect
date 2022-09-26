## 介绍
本项目的初衷是研究frida的检测与保护技术，可能会涉及到具体商业产品，如有侵权，请微信联系lovexyx2020删除。

## apk_all
apk_all目录里面放置了一些常见的检测apk，其中momo和hunter是目前未开源的两款优秀的检测项目

1. [[原创]一个检测手机环境的Demo 珍惜大佬的hunter](https://bbs.pediy.com/thread-274218.htm)
2. [Riru-MomoHider](https://github.com/canyie/Riru-MomoHider)

## froda（课程相关，暂时未公开）
首先这里感谢hluda的开源定制，因为froda是基于hluda，然后再定制了一些额外的字符串（frida:rpc等），以及线程名，绕过了常见的字符串检测。

## frida检测

### 常规检测参考
1. [AntiFrida](https://github.com/qtfreet00/AntiFrida)
2. [AntiFrida](https://github.com/xxr0ss/AntiFrida)
3. [antifridaAndroid](https://github.com/emanriquez/antifridaAndroid)

### 进阶检测参考
1. [[原创]关于frida检测的一个新思路](https://bbs.pediy.com/thread-268586.htm)
2. [从inlinehook角度检测frida](https://bbs.pediy.com/thread-269862.htm)
3. [anti_Android](https://github.com/TUGOhost/anti_Android)
4. [detectfridalib](https://github.com/kumar-rahul/detectfridalib)
5. [从Frida对SO的解析流程中寻找检测Frida的点](https://mp.weixin.qq.com/s?__biz=MzIxNDcwOTcwOQ==&mid=2247492981&idx=2&sn=1337a0dd0259195efe078be55d1d4a55&chksm=97a1c1d7a0d648c14f09d0fd9a43e150f53ce79c82ab5098b7dca6cffc663ce7d32eb5a27b2e&scene=126&sessionid=1653073641&key=0a9f15bc7a0b11091058c506225c7aacc781814ef557c1c6195dacd423a4d7507afa9035592752f9405e452a884945d59fe8a303e08a2720f63543e053d51f5610aa3b9c39f4022a941e44e6a95a4e7f94a498dbe19a9910e426a2efb448776eb27f191dff8d34dd848894604e6cda8798d3d39de7b44611a7a06cc8fdf43826&ascene=1&uin=MTA3Mzc3OTIzNQ%3D%3D&devicetype=Windows+Server+2016+x64&version=6305002e&lang=zh_CN&session_us=gh_86e8b32f4148&exportkey=AScNPRbXZl0lSD8Me34jl4w%3D&acctmode=0&pass_ticket=CLipu1oc3Xo23kKaFPk9VMmJWr0KzXLDKmtoNd6o2PRzCklLCrUb3XxUITQ9X3B0&wx_header=0&fontgear=2)

## frida保护
1. 检测更多的frida的特征字符串
2. 检测更深的hook特征
3. 尽量使用双进程保护
4. 尽量使用svc去获取数据
5. 保护检测线程不被干掉

## 实例展示（均为最新版）

### taptap
crack: 将froda版的gadget库放在system/lib64下，使用ptrace直接注入即可绕过
改进建议：进行更深层次的inlinehook检测以及其它特征

