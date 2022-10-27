## 介绍
本项目的初衷是研究frida的检测与保护技术，可能会涉及到具体商业产品，如有侵权，请微信联系lovexyx2020删除。

## apk_all
apk_all目录里面放置了一些常见的检测apk，其中momo和hunter是目前未开源的两款优秀的检测项目

1. [[原创]一个检测手机环境的Demo 珍惜大佬的hunter](https://bbs.pediy.com/thread-274218.htm)
2. [Riru-MomoHider](https://github.com/canyie/Riru-MomoHider)
3. 正在开发的检测apk---detectfridaxp

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

汇总所有的frida反调试
测试环境 android 12 pixel3axl magisk shamiko froda

注意：弱代表使用froda不退出，可以正常hook了。

1. 菠萝包小说 4.8.90 com.sfacg
2. i茅台 1.2.15 com.moutai.mall 
3. 七读免费小说 5.0.1 com.dj.sevenRead
4. 快点阅读 4.19.03 com.skyplatanus.crucio
5. IQIYI Lite 2.8.6 com.qiyi.video.lite
6. 网上国网 2.3.4 com.sgcc.wsgw.cn
7. 得物 5.2.5 com.shizhuang.duapp
8. 小红书 7.59.1 com.xingin.xhs
9. 陌陌 9.5.5 com.immomo.momo
10. 惠头条 4.5.8.9  com.cashtoutiao 
11. taptap 2.36.0 com.taptap 强对抗 
11. taptap 2.34.0 com.taptap 
12. 省省回头车 7.0.1 com.huitouche.android.app
13. 房天下 9.61 com.soufun.app
14. 暗黑破坏神：不朽 1.5.4 com.netease.g67 弱
15. 抖音 22.7.0 com.ss.android.ugc.aweme 弱
16. APKSSR 3.4.3 com.dreamtee.apkfure 弱
17. HiYa语音 4.22.0.1250 com.youyisia.peiwan 
18. 冀云邯郸 1.9.6 com.pdmi.handan.media 弱
19. 中行 7.6.1 com.chinamworld.bocmbci 弱
20. 招行 10.4.0 cmb.pb 弱 
21. 建行 5.5.9 com.chinamworld.main 弱
22. 农行 6.6.1 com.android.bankabc 弱
23. 贵旅优品 3.2.0 com.gzlex.hui.guoziwei.travel 弱 (shamiko模式会卡主界面)
24. V-Appstore 8.98.80.0 com.bbk.appstore 弱
25. 小豆苗 6.19.5 com.threegene.yeemiao 弱
26. 应用宝 8.2.7 com.tencent.android.qqdownloader 弱
27. 闲鱼 7.7.30 com.taobao.idlefish 弱
28. soul 4.50.0 cn.soulapp.android 
29. 捕鱼大咖 38 com.youkushengshi.buyudaka 
30. 汽车之家 11.30.5 com.cubic.autohome
31. bilibili 7.1.2 tv.danmaku.bili
32. 新漂流瓶 3.6.3 com.yilahuo.driftbottle 弱
33. 哈啰 6.25.0 com.jingyao.easybike
34. 国泰君安君弘 9.6.20 com.guotai.dazhihui
35. 知到 4.7.8 com.able.wisdomtree 
36. 恒生 5.7.5 com.hsbc.personalbanking.hacn.dev 弱
37. 联想智选 5.3.9 com.lenovo.club.app 
38. 快手免费小说 1.0.3.5 com.kuaishou.kgx.novel 弱
39. Citic Bank 8.6.1 com.ecitic.bank.mobile 弱
40. 星巴克 9.0.0 com.starbucks.cn 弱
