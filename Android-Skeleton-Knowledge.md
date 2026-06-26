# Android 骨架知识点（200+条）

> 面向全栈开发者的Android知识骨架，适用于跨端开发时快速了解Android生态。**聚焦平台能力、工具链、生态知识**，删除Kotlin/协程等技术细节。

---

## 📑 目录

### 🔧 一、开发基础工具（1-20）
- [1. ADB 调试桥](#📱-1-adb-调试桥) - 设备管理/应用管理/文件传输/日志查看/性能监控
- [2. Android Studio](#🛠️-2-android-studio) - IDE/代码编辑/布局设计/调试/性能分析
- [3. Gradle 构建系统](#📦-3-gradle-构建系统) - 依赖管理/编译打包/多渠道/混淆
- [4. AVD 模拟器](#🖥️-4-avd-模拟器) - 设备模拟/系统测试/功能测试/快照
- [5. AndroidManifest](#📝-5-androidmanifest-清单文件) - 应用声明/组件注册/权限声明
- [6. 项目结构](#🗂️-6-项目结构) - 代码组织/资源管理/构建配置
- [7. 签名与证书](#🔐-7-签名与证书) - 应用标识/权限升级/组件共享
- [8. ProGuard/R8 混淆](#🔨-8-proguardr8-混淆) - 代码混淆/代码压缩/优化
- [9. AAB vs APK](#📦-9-aab-vs-apk) - 发布格式/动态分发/体积优化
- [10. Git 版本控制](#🌐-10-git-版本控制) - 版本管理/分支管理/协作
- [11. Kotlin 语言](#🤖-11-kotlin-语言) - 现代语言/空安全/协程/互操作
- [12. Java 语言](#⚡-12-java-语言) - 传统语言/库支持/性能
- [13. JUnit 测试](#🧪-13-junit-测试框架) - 单元测试/断言/生命周期
- [14. Mockito](#🎭-14-mockito-mock框架) - Mock框架/对象模拟
- [15. Espresso](#🌊-15-espresso-ui测试) - UI测试/交互测试
- [16. 屏幕适配](#📏-16-屏幕适配与密度) - 密度适配/dp单位/资源限定符
- [17. dp/sp/px 单位](#📐-17-dpsppx-单位) - 长度单位/使用场景
- [18. Context 上下文](#📱-18-context-上下文) - 类型/生命周期/使用场景
- [19. 状态栏与导航栏](#📊-19-状态栏与导航栏) - 高度获取/隐藏/颜色修改
- [20. 深色模式](#🌙-20-深色模式) - 系统深色/主题适配/资源适配

### 📱 二、Android平台特性与组件（21-50）
- [21. Activity 组件](#📱-21-activity-组件) - UI容器/生命周期/启动模式/数据传递
- [22. Fragment 组件](#🧩-22-fragment-组件) - UI模块化/生命周期/事务/回栈
- [23. Service 组件](#🎭-23-service-组件) - 后台任务/音乐播放/下载/前台服务
- [24. BroadcastReceiver](#📡-24-broadcastreceiver-组件) - 系统广播/应用广播/有序广播
- [25. ContentProvider](#🗄️-25-contentprovider-组件) - 数据共享/抽象/权限/URI
- [26. Intent](#📨-26-intent-消息机制) - 启动组件/传递数据/隐式/显式
- [27. Intent Filter](#🎢-27-intent-filter) - 隐式Intent/组件声明/DeepLink
- [28. 广播类型](#📡-28-广播类型) - 普通/有序/本地/系统
- [29. IPC 进程间通信](#🔗-29-ipc-进程间通信) - 跨进程/多进程/AIDL/Messenger
- [30. 进程与线程](#📊-30-进程与线程) - 多进程/进程优先级/主线程/子线程
- [31. 应用生命周期](#🎯-31-应用生命周期) - 前台/后台/热启动/冷启动/进程回收
- [32. 应用沙箱](#💾-32-应用沙箱) - 进程隔离/权限隔离/文件隔离/代码隔离
- [33. 应用权限](#🔐-33-应用权限) - 权限声明/运行时权限/权限组/回调
- [34. 常用权限列表](#📋-34-常用权限列表) - 网络/存储/相机/位置/录音等
- [35. 特殊权限](#🔐-35-特殊权限) - 悬浮窗/修改系统/访问所有文件/安装应用
- [36. 定位服务](#📍-36-定位服务) - GPS/网络定位/FusedLocation/地理围栏
- [37. 地图SDK](#🗺️-37-地图sdk) - 高德/百度/Google Maps/定位导航
- [38. 相机能力](#📷-38-相机能力) - Camera1/Camera2/CameraX/拍照录像
- [39. 录音能力](#🎤-39-录音能力) - MediaRecorder/AudioRecord/录音权限
- [40. 电话能力](#📞-40-电话能力) - 拨打电话/读取通话记录/电话状态
- [41. 短信能力](#💬-41-短信能力) - 发送短信/接收短信/短信权限
- [42. 蓝牙能力](#📶-42-蓝牙能力) - 经典蓝牙/低功耗蓝牙/扫描连接
- [43. WiFi能力](#📡-43-wifi能力) - 扫描/连接/热点/WiFi Direct
- [44. 蜂窝网络](#📶-44-蜂窝网络) - 网络类型/SIM卡/信号强度/双卡
- [45. NFC能力](#📡-45-nfc能力) - 标签读写/卡模拟/P2P/支付
- [46. 电池与电源](#🔋-46-电池与电源) - 电池信息/WakeLock/Doze模式
- [47. 通知系统](#🔔-47-通知系统) - 状态栏通知/通知渠道/通知权限
- [48. 音频系统](#🔊-48-音频系统) - 音频管理/播放录制/焦点/音量
- [49. 多媒体能力](#🎬-49-多媒体能力) - 视频/音频/媒体库/控制/画中画
- [50. 网络能力](#🌐-50-网络能力) - 网络类型/网络状态/权限/VPN

### 🎨 三、UI组件与布局（51-80）
- [51. View 基础组件](#🎨-51-view-基础组件) - UI组件/布局管理/事件处理/自定义View
- [52. ViewGroup](#🧩-52-viewgroup-容器) - 容器功能/布局控制/事件分发
- [53. LinearLayout](#📐-53-linearlayout-线性布局) - 线性排列/权重分配/对齐控制
- [54. RelativeLayout](#🎯-54-relativelayout-相对布局) - 相对定位/对齐方式/位置关系
- [55. ConstraintLayout](#🔗-55-constraintlayout-约束布局) - 约束关系/性能优化/可视化编辑
- [56. FrameLayout](#🃏-56-framelayout-帧布局) - 叠加显示/简单布局/Fragment容器
- [57. RecyclerView](#📊-57-recyclerview-列表) - 高效列表/布局管理/列表动画
- [58. ScrollView](#📜-58-scrollview-滚动容器) - 垂直滚动/嵌套滚动/平滑滚动
- [59. ViewPager/ViewPager2](#🧭-59-viewpagerviewpager2-滑动页面) - 页面滑动/页面预加载/指示器
- [60. ImageView](#🖼️-60-imageview-图片组件) - 图片显示/缩放类型/圆角图片
- [61. TextView](#📝-61-textview-文本组件) - 文本显示/样式设置/富文本/省略
- [62. Button](#🔘-62-button-按钮) - 点击事件/样式定制/状态变化
- [63. EditText](#📂-63-edittext-输入框) - 文本输入/输入类型/输入限制/焦点
- [64. ProgressBar](#🎛️-64-progressbar-进度条) - 进度显示/样式选择/不确定状态
- [65. SeekBar](#🎚️-65-seekbar-滑动条) - 拖动调节/进度监听/样式定制
- [66. CheckBox](#💾-66-checkbox-复选框) - 多选功能/状态监听/样式定制
- [67. RadioButton & RadioGroup](#📻-67-radiobutton--radiogroup) - 单选功能/分组管理/状态监听
- [68. Switch](#🔃-68-switch-开关) - 开关功能/状态监听/文本显示
- [69. Toolbar](#🏔️-69-toolbar-工具栏) - 应用标题/导航按钮/菜单项/自定义视图
- [70. TabLayout](#🗂️-70-tablayout-标签页) - 标签页/指示器/图标文字/ViewPager联动
- [71. Material Design 组件](#🎨-71-material-design-组件) - MaterialButton/TextInputLayout/BottomAppBar
- [72. WebView](#🎭-72-webview-网页容器) - 加载网页/JavaScript/Cookie/调试
- [73. 图表库](#📊-73-图表库) - MPAndroidChart/图表类型/动画
- [74. 地图组件](#🗺️-74-地图组件) - 地图显示/标记/折线/定位
- [75. 图片选择器](#📸-75-图片选择器) - 相册选择/相机拍照/裁剪
- [76. GIF播放](#🎬-76-gif播放) - Glide播放/GifImageView/控制
- [77. 视频播放](#🎞️-77-视频播放) - VideoView/MediaPlayer/ExoPlayer
- [78. 音频播放](#🎵-78-音频播放) - MediaPlayer/SoundPool/后台播放
- [79. 广告组件](#🎪-79-广告组件) - AdMob/穿山甲/优量汇
- [80. 自定义View](#🎨-80-自定义view) - 自定义绘制/自定义属性/测量布局

### 📦 四、数据存储（81-100）
- [81. SQLite 数据库](#🗄️-81-sqlite-数据库) - 关系型数据库/SQL支持/事务
- [82. Room 数据库](#🏛️-82-room-数据库) - SQLite抽象/编译验证/LiveData/Flow
- [83. ContentProvider](#🔍-83-contentprovider-数据共享) - 跨应用共享/数据抽象/权限/URI
- [84. 文件存储](#📁-84-文件存储) - 内部存储/外部存储/缓存文件
- [85. MediaStore](#🖼️-85-mediastore-媒体库) - 媒体文件管理/查询/插入/删除
- [86. 加密存储](#🔐-86-加密存储) - Keystore/AES/RSA/加密文件
- [87. 数据同步](#🔄-87-数据同步) - SyncAdapter/WorkManager/云端同步
- [88. 数据迁移](#🔄-88-数据迁移) - Room迁移/增量迁移/备份回滚
- [89. 云端存储](#📱-89-云端存储) - Firestore/Realtime Database/AWS
- [90. 数据压缩](#🗜️-90-数据压缩) - GZIP/ZIP/图片压缩

### 🌐 五、网络通信（101-120）
- [101. 网络基础](#📡-101-网络基础) - 网络类型/网络状态/网络配置
- [102. HTTP协议](#🌐-102-http协议) - GET/POST/HTTPS/缓存/Cookie
- [103. OkHttp](#📦-103-okhttp-客户端) - HTTP请求/连接池/缓存/拦截器
- [104. Retrofit](#🌐-104-retrofit-网络库) - REST API/类型安全/协程/转换器
- [105. 网络请求拦截](#📨-105-网络请求拦截) - 添加Header/日志/重试/缓存
- [106. 文件上传下载](#📦-106-文件上传下载) - Multipart上传/进度/断点续传
- [107. 网络安全](#🔐-107-网络安全) - HTTPS/证书校验/证书固定/配置
- [108. 网络认证](#🔑-108-网络认证) - Basic/Bearer/API Key/签名
- [109. GraphQL](#📊-109-graphql) - 精确查询/强类型/单个端点
- [110. WebSocket](#🔌-110-websocket) - 实时通信/长连接/双向通信
- [111. DownloadManager](#📦-111-downloadmanager-下载) - 后台下载/大文件/通知栏
- [112. 数据同步](#🔄-112-数据同步) - SyncAdapter/WorkManager/轮询/推送
- [113. 网络状态监听](#🌐-113-网络状态监听) - 网络变化/网络类型/离线处理
- [114. 推送服务](#📡-114-推送服务) - FCM/极光/个推/华为/小米/OPPO/vivo
- [115. 消息队列](#📨-115-消息队列) - 消息发送/接收/异步处理

### 🚀 六、跨平台开发（121-140）
- [121. React Native](#📱-121-react-native) - 跨平台/热更新/原生组件
- [122. Flutter](#🐦-122-flutter) - 跨平台/性能/UI一致性/热重载
- [123. Kotlin Multiplatform](#🔧-123-kotlin-multiplatform) - 跨平台/代码共享/原生性能
- [124. 小程序开发](#📐-124-小程序开发) - 微信/支付宝/百度/字节/QQ/快应用
- [125. PWA](#🌐-125-pwa-渐进式web应用) - Web应用/安装/离线/推送
- [126. Unity](#🎮-126-unity-3d游戏) - 3D游戏/C#脚本/性能
- [127. Cocos2d-x](#🎮-127-cocos2d-x-游戏引擎) - 2D游戏/跨平台/性能
- [128. 跨平台方案对比](#🖥️-128-跨平台方案对比) - 性能/开发效率/UI一致性/热更新
- [129. 混合开发](#🎯-129-混合开发) - WebView/JSBridge/Cordova/小程序
- [130. 原生与H5交互](#🔗-130-原生与h5交互) - JSBridge/addJavascriptInterface/evaluateJavascript

### 🔐 七、安全与权限（141-160）
- [141. 应用签名](#🔐-141-应用签名) - 应用标识/权限升级/组件共享/更新
- [142. 代码混淆](#🔨-142-代码混淆) - ProGuard/R8/资源压缩/优化
- [143. 应用加固](#🛡️-143-应用加固) - 代码保护/资源保护/防篡改
- [144. 防调试](#🔍-144-防调试) - 调试检测/模拟器检测/Root检测
- [145. 证书校验](#🔐-145-证书校验) - HTTPS证书/自定义校验/双向认证
- [146. 密钥存储](#🔑-146-密钥存储) - Keystore/密钥生成/生物识别
- [147. 数据加密](#🔒-147-数据加密) - AES/RSA/Hash/HMAC/加密文件
- [148. WebView安全](#🛡️-148-webview安全) - 禁止file:///限制JS/XSS防护
- [149. ProGuard混淆规则](#🔐-149-proguard混淆规则) - keep类/keep成员/移除日志
- [150. 安全检测工具](#🔍-150-安全检测工具) - MobSF/QARK/Drozer/Frida
- [151. 存储权限适配](#🔐-151-存储权限适配) - 分区存储/MediaStore/SAF
- [152. 位置权限适配](#📍-152-位置权限适配) - 精确定位/粗略定位/后台定位
- [153. 相机权限适配](#📷-153-相机权限适配) - CAMERA权限/uses-feature/权限请求
- [154. 生物识别](#🔐-154-生物识别) - BiometricPrompt/指纹/面容/密钥绑定
- [155. 设备认证](#🔐-155-设备认证) - 设备标识/Device Policy/Work Profile
- [156. 应用沙箱隔离](#🛡️-156-应用沙箱隔离) - 进程隔离/权限隔离/签名隔离
- [157. 应用权限检查](#🔐-157-应用权限检查) - checkPermission/requestPermissions/回调
- [158. 权限组](#📋-158-权限组) - LOCATION/CONTACTS/PHONE/STORAGE/CALENDAR
- [159. 网络安全配置](#🔐-159-网络安全配置) - HTTPS/证书固定/域名配置
- [160. 应用签名验证](#🔐-160-应用签名验证) - 签名校验/签名比对/完整性检查

### 📊 八、性能优化（161-180）
- [161. 启动优化](#⚡-161-启动优化) - 冷启动/热启动/优化方向/工具
- [162. 卡顿优化](#🐢-162-卡顿优化) - 主线程/布局优化/过度绘制/刷新率
- [163. 内存优化](#💾-163-内存优化) - 内存泄漏/内存抖动/OOM/分析工具
- [164. 耗电优化](#🔋-164-耗电优化) - WakeLock/后台任务/定位/网络
- [165. 网络优化](#📡-165-网络优化) - 连接复用/缓存/批量请求/压缩
- [166. 数据库优化](#🗄️-166-数据库优化) - 索引/查询优化/批量操作/异步
- [167. APK优化](#📦-167-apk优化) - 资源压缩/代码混淆/图片优化/So优化
- [168. 图片优化](#🖼️-168-图片优化) - 压缩/格式/尺寸/缓存/图片库
- [169. 线程优化](#🔄-169-线程优化) - 线程复用/协程/主线程/线程数
- [170. 布局优化](#📊-170-布局优化) - 减少层级/ConstraintLayout/include/ViewStub
- [171. 渲染优化](#🎨-171-渲染优化) - 硬件加速/过渡绘制/离屏缓冲
- [172. 性能分析工具](#🔍-172-性能分析工具) - Profiler/Memory/Systrace/Perfetto
- [173. 内存分析](#🧪-173-内存分析) - Profiler/Heap Dump/MAT/LeakCanary
- [174. ANR分析](#🐛-174-anr分析) - 主线程阻塞/traces.txt/StrictMode
- [175. 耗时分析](#⚡-175-耗时分析) - CPU Profiler/Systrace/Simpleperf
- [176. 流畅度分析](#📉-176-流畅度分析) - FPS/丢帧/Choreographer/GPU
- [177. 构建优化](#🔧-177-构建优化) - 增量构建/构建缓存/配置内存
- [178. Benchmark](#🧪-178-benchmark-基准测试) - 宏基准/微基准/预热/编译优化
- [179. 电量优化](#📱-179-电量优化) - WakeLock/JobScheduler/Doze/Battery Historian
- [180. 网络优化](#📊-180-网络优化) - 连接复用/缓存/批量/压缩/DNS

### 🛠️ 九、工具与库（181-200）
- [181. Glide](#🖼️-181-glide-图片加载) - 图片加载/内存缓存/磁盘缓存/GIF
- [182. Coil](#🎨-182-coil-图片加载) - Kotlin优先/轻量级/协程/SVG
- [183. Gson](#🌐-183-gson-json解析) - JSON解析/泛型/注解/流式
- [184. Moshi](#📄-184-moshi-json解析) - Kotlin友好/代码生成/注解
- [185. Hilt](#💉-185-hilt-依赖注入) - 官方DI/编译时/Android集成/ViewModel
- [186. Koin](#🧪-186-koin-依赖注入) - 轻量级/无代码生成/DSL
- [187. Material Components](#🎨-187-material-components) - 官方组件/MaterialButton/主题
- [188. Room](#🗄️-188-room-数据库) - 类型安全/编译验证/LiveData/Flow
- [189. Retrofit](#🔗-189-retrofit-网络库) - REST API/类型安全/协程/拦截器
- [190. OkHttp](#⚙️-190-okhttp-客户端) - 连接池/缓存/拦截器/WebSocket
- [191. EventBus](#🎯-191-eventbus-事件总线) - 组件通信/解耦合/线程模式
- [192. 高德地图](#🗺️-192-高德地图sdk) - 地图/定位/导航/搜索/周边
- [193. 百度地图](#🗺️-193-百度地图sdk) - 地图/定位/导航/搜索/鹰眼
- [194. 友盟统计](#📊-194-友盟统计) - 用户统计/页面统计/事件统计
- [195. 神策分析](#📊-195-神策分析) - 用户行为/漏斗/分群/埋点
- [196. 腾讯Bugly](#📱-196-腾讯bugly) - 崩溃/错误/热修复/升级
- [197. 极光推送](#🔔-197-极光推送) - 推送/自定义消息/富媒体/标签
- [198. Gson vs Jackson vs Moshi](#🎨-198-gson-vs-jackson-vs-moshi) - JSON库对比/性能/选择
- [199. 支付集成](#💳-199-支付集成) - 支付宝/微信/银联/Apple Pay/Google Pay
- [200. 社交登录](#📲-200-社交登录) - Google/Facebook/微信/QQ/新浪/Apple

### 📚 学习资源
- [官方资源](#📖-官方资源) - Android Developers/Android Studio/Jetpack/Material
- [学习建议](#🎯-学习建议) - 学习路径/重点关注
- [调试技巧](#🔍-调试技巧) - ADB/Logcat/Profiler/抓包
- [中文资源](#🌐-中文资源) - 中文站/掘金/CSDN/知乎
- [最佳实践](#💡-最佳实践) - 架构/性能/安全/测试/文档

---

## 🔧 一、开发基础工具（1-20）

### 📱 1. ADB 调试桥

**是什么**: Android Debug Bridge，Android SDK中的命令行工具  
**能干什么**:
- **设备管理** - 查看连接设备、重启设备、重启到recovery/fastboot/bootloader模式
- **应用管理** - 安装APK、卸载应用、启动应用、清除应用数据、强制停止应用、备份应用
- **文件传输** - 电脑与设备间双向传输文件、推送到设备、从设备拉取、查看设备文件系统
- **日志查看** - 实时查看应用日志、按TAG/进程过滤、保存日志到文件、清空日志
- **性能监控** - 查看CPU使用率、查看内存占用、查看GPU渲染情况、查看进程信息
- **系统信息** - 查看设备分辨率、查看DPI、查看屏幕密度、查看Android版本、查看设备型号、查看CPU架构
- **调试功能** - 端口转发、调试应用、查看运行中进程、查看应用组件
- **截图录屏** - 截取屏幕截图、录制屏幕视频、屏幕截图后导出
- **Shell命令** - 在设备上执行shell命令、查看系统属性、修改系统设置
- **无线调试** - 通过WiFi连接设备进行调试、TCP/IP连接、无需USB线
- **应用备份** - 备份应用和数据、恢复应用和数据
- **设备信息** - 查看设备ID、查看Mac地址、查看IP地址、查看电池状态
- **输入模拟** - 模拟输入文本、模拟按键、模拟触摸、模拟滑动
- **端口转发** - 端口映射、电脑端口映射到设备端口
- **文件安装** - 安装APK到指定设备、覆盖安装、多设备安装

**常用命令**:
```bash
# 设备管理
adb devices                                    # 查看连接的设备
adb devices -l                                 # 查看设备详细信息
adb reboot                                     # 重启设备
adb reboot recovery                            # 重启到recovery模式
adb reboot bootloader                          # 重启到bootloader模式
adb reboot edl                                 # 重启到EDL模式（小米）
adb shell reboot -p                            # 重启到bootloader

# 应用管理
adb install app.apk                            # 安装应用
adb install -r app.apk                         # 覆盖安装
adb install -g app.apk                         # 安装并授予所有运行时权限
adb uninstall com.example.app                  # 卸载应用
adb uninstall -k com.example.app               # 卸载但保留数据
adb shell pm list packages                     # 列出所有应用
adb shell pm list packages -3                   # 列出第三方应用
adb shell pm list packages | grep xxx          # 过滤应用
adb shell pm path com.example.app              # 查看应用路径
adb shell pm clear com.example.app             # 清除应用数据
adb shell am force-stop com.example.app        # 强制停止应用
adb shell am start -n com.example.app/.MainActivity  # 启动应用
adb shell am start -W -n com.example.app/.MainActivity  # 启动并等待启动完成

# 文件传输
adb push local.txt /sdcard/                    # 电脑→设备
adb pull /sdcard/remote.txt ./                 # 设备→电脑
adb pull /sdcard/                              # 拉取整个目录
adb shell ls -l /sdcard/                       # 查看文件列表
adb shell ls -R /sdcard/                       # 递归查看文件

# 日志查看
adb logcat                                     # 查看所有日志
adb logcat | grep "MyApp"                      # 过滤日志
adb logcat *:W                                 # 只看Warning及以上级别
adb logcat -c                                  # 清除日志
adb logcat -f log.txt                          # 保存日志到文件
adb logcat -t 100                              # 只看最近100条
adb logcat --pid=12345                         # 只看指定进程日志
adb logcat -s TAG:I                            # 只看指定TAG

# 性能监控
adb shell top                                  # 查看进程CPU占用
adb shell top -n 1 | grep com.example          # 查看指定应用CPU
adb shell dumpsys cpuinfo                      # CPU详细信息
adb shell dumpsys meminfo com.example.app      # 应用内存占用
adb shell dumpsys gfxinfo com.example.app      # GPU渲染信息
adb shell ps                                   # 查看运行中的进程
adb shell kill 12345                           # 杀死进程

# 系统信息
adb shell wm size                              # 查看设备分辨率
adb shell wm density                           # 查看DPI
adb shell wm density 320                      # 修改DPI（慎用）
adb shell getprop ro.build.version.release     # 查看Android版本
adb shell getprop ro.product.model             # 查看设备型号
adb shell getprop ro.product.cpu.abi           # 查看CPU架构
adb shell cat /proc/cpuinfo                     # 查看CPU详细信息
adb shell cat /proc/meminfo                     # 查看内存信息
adb shell wm density                           # 查看屏幕密度
adb shell service list                          # 查看系统服务

# 截图录屏
adb shell screencap -p /sdcard/screen.png      # 截图
adb pull /sdcard/screen.png ./                 # 导出截图
adb shell screenrecord /sdcard/demo.mp4        # 录屏（Ctrl+C停止）
adb shell screenrecord --time-limit 30 /sdcard/demo.mp4  # 录屏30秒
adb pull /sdcard/demo.mp4 ./                   # 导出录屏

# 输入模拟
adb shell input text "Hello"                    # 输入文本
adb shell input keyevent 4                     # 模拟返回键
adb shell input tap 500 500                     # 模拟点击
adb shell input swipe 100 500 500 500           # 模拟滑动

# 端口转发
adb forward tcp:8080 tcp:8080                  # 端口转发
adb reverse tcp:8080 tcp:8080                  # 反向端口转发

# 无线调试
adb tcpip 5555                                 # 启用TCP模式
adb connect 192.168.1.100:5555                # WiFi连接设备
adb disconnect 192.168.1.100:5555              # 断开WiFi连接

# 应用组件
adb shell am start -a android.intent.action.VIEW  # 启动隐式Intent
adb shell am broadcast -a com.example.ACTION   # 发送广播
adb shell am startservice -n com.example/.MyService  # 启动Service

# 其他
adb shell df -h                                # 查看存储
adb shell getprop                              # 查看所有系统属性
adb shell settings list global                 # 查看系统设置
adb bugreport                                  # 生成完整bug报告
```

### 🛠️ 2. Android Studio

**是什么**: Google官方Android集成开发环境（IDE），基于IntelliJ IDEA  
**能干什么**:
- **代码编辑** - 智能代码补全、语法高亮、代码重构、多光标编辑、代码格式化、实时模板
- **布局设计** - 可视化布局编辑器、拖拽组件、实时预览、蓝图视图、约束布局编辑
- **项目管理** - Gradle同步、依赖管理、模块管理、版本控制集成、构建变体
- **调试功能** - 断点调试、变量查看、表达式求值、条件断点、日志断点、线程调试
- **性能分析** - CPU Profiler、内存分析、网络分析、能耗分析、布局检查
- **日志查看** - Logcat集成、日志过滤、日志搜索、按进程/级别过滤
- **模拟器管理** - AVD管理、模拟器启动、设备配置、快照管理
- **APK分析** - APK Analyzer查看APK内容、资源分析、代码分析、大小分析
- **版本控制** - Git集成、代码提交、分支管理、冲突解决、变更历史
- **插件生态** - 丰富的插件支持、主题定制、快捷键自定义、代码生成
- **AI助手** - Gemini AI代码生成、代码解释、bug修复建议
- **布局检查** - Layout Inspector查看运行时布局、View属性、布局层级
- **数据库检查** - Database Inspector查看数据库、执行SQL、修改数据

### 📦 3. Gradle 构建系统

**是什么**: Android项目的自动化构建工具  
**能干什么**:
- **依赖管理** - 自动下载和管理第三方库、版本控制、依赖冲突解决、传递依赖
- **编译打包** - 编译Kotlin/Java代码、打包APK/AAB、签名APK、多版本打包
- **多渠道打包** - productFlavors配置多版本、动态替换配置、批量生成渠道包、manifestPlaceholders
- **构建变体** - debug/release版本、buildTypes配置、自动生成多版本、versionNameSuffix
- **代码混淆** - ProGuard/R8混淆、资源压缩、优化代码、keep规则
- **资源处理** - 资源合并、资源压缩、自动生成R类、资源去重
- **Manifest处理** - 自动合并Manifest、权限合并、占位符替换
- **Native编译** - NDK/JNI代码编译、CMake支持、ndk-build支持、外部Native构建
- **增量构建** - 增量编译、构建缓存、加速构建、构建缓存清理
- **自定义任务** - 自定义Gradle任务、Transform API、字节码操作、Gradle插件开发
- **Build Config** - 自动生成BuildConfig类、编译时常量、DEBUG标志

**常用配置**:
```gradle
// 依赖管理
dependencies {
    implementation 'androidx.core:core-ktx:1.12.0'  // 实现，不对外暴露
    api 'androidx.appcompat:appcompat:1.6.1'         // API，会传递给依赖者
    testImplementation 'junit:junit:4.13.2'        // 测试依赖
    androidTestImplementation 'androidx.test:runner:1.5.2'
    debugImplementation 'com.squareup.leakcanary:leakcanary-android:2.12'  // 仅debug
}

// 多渠道打包
android {
    flavorDimensions "default"
    productFlavors {
        free { 
            applicationId "com.example.app.free"
            versionNameSuffix "-free"
        }
        pro { 
            applicationId "com.example.app.pro"
            versionNameSuffix "-pro"
        }
    }
}

// 构建变体
buildTypes {
    debug {
        applicationIdSuffix ".debug"
        debuggable true
        minifyEnabled false
    }
    release {
        minifyEnabled true           // 混淆
        shrinkResources true         // 资源压缩
        proguardFiles 'proguard-rules.pro'
        signingConfig signingConfigs.release
    }
}

// 签名配置
signingConfigs {
    release {
        storeFile file("keystore.jks")
        storePassword "password"
        keyAlias "key0"
        keyPassword "password"
    }
}
```

### 🖥️ 4. AVD 模拟器

**是什么**: Android Virtual Device，Android虚拟设备  
**能干什么**:
- **设备模拟** - 模拟各种Android设备、不同屏幕尺寸、不同API级别、不同CPU架构
- **系统测试** - 测试不同Android版本、测试不同屏幕配置、测试不同语言
- **功能测试** - GPS模拟、电话模拟、短信模拟、网络模拟、传感器模拟
- **性能测试** - 模拟不同CPU性能、模拟不同内存大小、模拟不同存储
- **快照功能** - 保存模拟器状态、快速启动、多快照切换、快照管理
- **Google服务** - 模拟Google Play服务、测试Google登录、Play Store测试
- **传感器模拟** - 加速度计、陀螺仪、光线传感器、距离传感器、温度传感器
- **相机模拟** - 摄像头模拟、前后摄像头、照片/视频模拟、Webcam
- **文件传输** - 直接拖拽文件到模拟器、简化文件传输
- **adb连接** - 支持adb调试、端口转发、无线调试
- **电话功能** - 模拟电话呼叫、模拟短信、模拟电话状态
- **电池模拟** - 模拟电池电量、模拟充电状态、模拟电池温度
- **网络模拟** - 模拟网络类型、模拟网络延迟、模拟网络速度

### 📝 5. AndroidManifest 清单文件

**是什么**: Android应用配置文件，位于项目根目录  
**能干什么**:
- **应用声明** - 声明应用名称、声明应用图标、声明应用主题、声明版本信息、声明应用ID
- **组件注册** - 注册Activity、注册Service、注册BroadcastReceiver、注册ContentProvider、注册Application
- **权限声明** - 声明应用所需权限、声明系统权限、声明自定义权限、声明权限组
- **应用配置** - 声明支持的屏幕尺寸、声明支持的API级别、声明硬件特性要求、声明软件特性
- **Intent过滤** - 声明组件可响应的Intent、声明隐式Intent配置、声明Action/Category/Data
- **元数据** - 存储应用配置信息、存储第三方SDK配置、存储key-value配置
- **备份配置** - 云备份配置、自动备份规则、exclude备份规则
- **安全配置** - 网络安全配置、信任锚点配置、证书固定
- **应用链接** - App Links配置、Deep Link配置、autoVerify验证
- **安装位置** - 安装到内部存储、安装到SD卡、installLocation
- **任务亲和性** - taskAffinity配置、launchMode配置、allowBackup配置

### 🗂️ 6. 项目结构

**是什么**: Android项目的目录组织和文件结构  
**能干什么**:
- **代码组织** - 分离业务代码、分离测试代码、分离AndroidManifest
- **资源管理** - 按类型组织资源文件（layout/drawable/values等）、按分辨率组织、按语言组织
- **多版本管理** - 支持多版本代码、支持多版本资源、支持不同屏幕
- **构建配置** - 模块级构建配置、项目级构建配置、settings配置
- **测试分离** - 单元测试代码、UI测试代码、androidTest分离
- **Gradle Scripts** - 构建脚本配置、依赖管理、签名配置

**核心目录说明**:
```
app/
├── src/
│   ├── main/
│   │   ├── java/              # Kotlin/Java源代码
│   │   ├── res/               # 资源文件
│   │   │   ├── layout/        # 布局文件
│   │   │   ├── drawable/      # 图片资源
│   │   │   ├── values/        # 字符串、颜色、样式
│   │   │   ├── mipmap/        # 应用图标
│   │   │   ├── raw/           # 原始文件
│   │   │   ├── anim/          # 动画资源
│   │   │   ├── color/         # 颜色状态列表
│   │   │   └── xml/           # XML配置
│   │   └── AndroidManifest.xml
│   ├── test/                  # 单元测试（JVM运行）
│   └── androidTest/           # UI测试（设备运行）
├── build.gradle               # 模块级构建配置
└── proguard-rules.pro         # 混淆规则
build.gradle                   # 项目级构建配置
settings.gradle                # 项目设置、模块声明
gradle.properties             # Gradle配置
local.properties               # 本地配置（SDK路径等，不提交）
```

### 🔐 7. 签名与证书

**是什么**: Android应用签名机制  
**能干什么**:
- **应用标识** - 确保应用来源可信、防止应用被替换、应用唯一标识
- **权限升级** - 签名相同可升级系统签名权限、signature权限
- **组件共享** - 相同签名的应用可共享组件、共享数据、sharedUserId
- **应用更新** - 相同签名才能覆盖安装更新应用、防止第三方覆盖
- **系统应用** - 系统签名可安装到/system分区、系统级应用
- **Google Play** - 上架Google Play需要签名、签名一致性验证
- **密钥库** - keystore文件管理、密钥别名管理、密钥密码管理
- **签名工具** - apksigner签名、jarsigner签名、验证签名

### 🔨 8. ProGuard/R8 混淆

**是什么**: Android代码混淆工具，R8是ProGuard的后继者  
**能干什么**:
- **代码混淆** - 将类名、方法名替换为无意义字符、保护代码逻辑、防止逆向
- **代码压缩** - 移除未使用的代码、减小APK体积、shrink阶段
- **资源压缩** - 移除未使用的资源文件、减小APK体积、shrinkResources
- **代码优化** - 优化字节码、提升运行性能、内联方法
- **优化控制** - keep规则、不混淆特定代码、keep规则配置
- **日志优化** - 移除Log.d/Log.v等调试日志、assumenosideeffects
- **生成映射** - mapping.txt文件、还原混淆后的堆栈
- **字典优化** - 自定义混淆字典、增加混淆强度

**混淆规则**:
```proguard
# 保持某个类不混淆
-keep public class com.example.MyClass

# 保持所有继承自Activity的类
-keep public class * extends android.app.Activity

# 保持所有native方法
-keepclasseswithmembernames class * {
    native <methods>;
}

# 移除日志
-assumenosideeffects class android.util.Log {
    public static *** d(...);
    public static *** v(...);
}

# 保持Bean类
-keep class com.example.bean.** { *; }
```

### 📦 9. AAB vs APK

**是什么**: Android App Bundle和Android Package的对比  
**能干什么**:
- **APK** - 传统安装格式、可直接安装、包含所有资源和代码、可独立分发
- **AAB** - 新发布格式、Google Play动态分发、按需加载功能模块
- **动态分发** - AAB支持根据设备配置自动生成优化APK、语言/屏幕/DPI
- **模块化** - AAB支持动态功能模块、用户需要时才下载、减少初始下载
- **体积优化** - AAB能减小下载体积、用户只下载需要的资源、节省空间
- **Play Asset** - Play Asset Delivery、大型资源包、游戏资源
- **Google Play要求** - 2021年8月起Google Play要求使用AAB、必须格式

### 🌐 10. Git 版本控制

**是什么**: 分布式版本控制系统  
**能干什么**:
- **代码版本管理** - 跟踪代码变更、查看历史版本、版本回退、查看diff
- **分支管理** - 创建分支、切换分支、合并分支、解决冲突
- **协作开发** - 多人协作、代码合并、冲突解决、代码审查
- **远程仓库** - GitHub/GitLab远程同步、代码共享、代码备份
- **代码审查** - Pull Request/Merge Request、代码审查、讨论代码
- **标签管理** - 版本标签、发布版本管理、v1.0.0等标签
- **暂存管理** - 暂存文件、取消暂存、丢弃修改
- **提交历史** - 查看提交历史、查看提交详情、统计提交

### 🤖 11. Kotlin 语言

**是什么**: Android官方推荐的现代编程语言  
**能干什么**:
- **简洁语法** - 减少样板代码、提高开发效率、data class自动生成方法
- **空安全** - 编译时空指针检查、减少运行时崩溃、?/!!操作符
- **协程支持** - 简化异步编程、替代回调和RxJava、结构化并发
- **扩展函数** - 为现有类添加新方法、无需继承、String.toMD5()
- **数据类** - 自动生成equals/hashCode/toString、copy方法、componentN
- **高阶函数** - 函数式编程支持、lambda表达式、函数作为参数
- **智能转换** - 类型自动转换、安全类型转换、无需强制转换
- **互操作性** - 与Java 100%互操作、可调用Java库、@JvmStatic等注解

### ⚡ 12. Java 语言

**是什么**: Android的传统编程语言  
**能干什么**:
- **Android开发** - 支持完整的Android API、历史悠久、生态成熟
- **库支持** - 大量成熟的Java库、Apache Commons、Guava
- **性能** - 优秀的性能表现、JVM优化、即时编译
- **稳定性** - 久经考验的稳定性、广泛使用
- **生态** - 庞大的生态系统、学习资源丰富

### 🧪 13. JUnit 测试框架

**是什么**: Java/Android单元测试框架  
**能干什么**:
- **单元测试** - 测试单个方法、测试业务逻辑、隔离测试
- **断言验证** - 验证预期结果、验证异常情况、assertEquals
- **测试套件** - 组织多个测试、批量运行、@Suite
- **生命周期** - @Before/@After、测试准备和清理、@BeforeAll/@AfterAll
- **参数化测试** - 多组参数测试、减少重复代码、@ParameterizedTest
- **超时测试** - 测试超时控制、timeout属性
- **异常测试** - 验证异常抛出、assertThrows

### 🎭 14. Mockito Mock框架

**是什么**: Java Mock框架，用于模拟依赖对象  
**能干什么**:
- **对象模拟** - 模拟依赖对象、隔离测试单元、mock()
- **行为验证** - 验证方法调用、验证调用次数、verify()
- **返回值模拟** - 模拟方法返回值、模拟异常抛出、when().thenReturn()
- **减少依赖** - 不依赖真实对象、测试更快速、无副作用
- **复杂场景** - 模拟复杂依赖、模拟异常情况、spy()部分模拟

### 🌊 15. Espresso UI测试

**是什么**: Android官方UI测试框架  
**能干什么**:
- **UI交互测试** - 模拟用户点击、输入、滑动等操作、onView().perform()
- **UI状态验证** - 验证UI元素显示、验证文本内容、check(matches())
- **Activity测试** - 验证Activity启动、验证Intent、IntentMatcher
- **RecyclerView测试** - 验证列表项、滚动到指定位置、scrollTo()
- **匹配器** - 丰富的视图匹配器、文本匹配器、Id匹配器、withId()/withText()
- **异步处理** - 自动处理异步、IdlingResource
- **WebView测试** - WebView断言、webAssignableFrom()

### 📏 16. 屏幕适配与密度

**是什么**: Android屏幕适配机制和像素密度概念  
**能干什么**:
- **密度适配** - 不同屏幕密度自动适配、mdpi/hdpi/xhdpi/xxhdpi/xxxhdpi
- **dp单位** - 与密度无关的像素、保证不同设备显示一致、1dp = 设备无关像素
- **sp单位** - 可缩放像素、用于字体、随用户字体设置缩放
- **px转换** - px = dp * (dpi / 160)、dp = px / (dpi / 160)
- **资源限定符** - res/layout-hdpi、res drawable-xhdpi、系统自动选择
- **屏幕尺寸** - small/normal/large/xlarge屏幕、layout-sw600dp
- **方向适配** - layout-land横屏、layout-port竖屏
- **宽高比** - 16:9/18:9/21:9等不同屏幕比例适配
- **刘海屏** - 刘海屏适配、displayCutout
- **挖孔屏** - 挖孔屏适配、不同厂商刘海

**密度比例**:
- mdpi (基准): 1dp = 1px (160dpi)
- hdpi: 1dp = 1.5px (240dpi)
- xhdpi: 1dp = 2px (320dpi)
- xxhdpi: 1dp = 3px (480dpi)
- xxxhdpi: 1dp = 4px (640dpi)

### 📐 17. dp/sp/px 单位

**是什么**: Android中的长度单位  
**能干什么**:
- **dp** - 密度无关像素、用于UI尺寸、适配不同密度
- **sp** - 可缩放像素、用于字体、随用户设置缩放、推荐字体单位
- **px** - 物理像素、实际屏幕像素、避免使用
- **pt** - 磅、1/72英寸、很少使用
- **mm** - 毫米、物理单位、很少使用
- **in** - 英寸、物理单位、很少使用

**使用建议**:
- UI尺寸用dp - 宽高/边距/间距
- 字体大小用sp - 适配用户字体设置
- 避免使用px - 适配不同屏幕

### 📱 18. Context 上下文

**是什么**: Android上下文接口，提供应用环境信息  
**能干什么**:
- **访问资源** - 访问res资源、getString/getColor
- **启动组件** - startActivity/startService/sendBroadcast
- **获取系统服务** - getSystemService、WindowManager/LayoutInflater等
- **访问应用信息** - getPackageName/getApplicationInfo
- **文件操作** - openFileInput/openOutput、getDir
- **数据库操作** - openOrCreateDatabase、getDatabasePath
- **SharedPreferences** - getSharedPreferences
- **ClassLoader** - getClassLoader
- **Theme** - setTheme/getTheme

**Context类型**:
- **Application Context** - 应用级别、生命周期与应用一致、单例、全局
- **Activity Context** - Activity级别、生命周期与Activity一致、UI相关
- **Service Context** - Service级别、生命周期与Service一致
- **BaseContext** - 基础Context、其他Context的底层

**使用场景**:
- 需要生命周期长于Activity→Application Context
- UI相关操作→Activity Context
- 单例/工具类→Application Context避免内存泄漏

### 📊 19. 状态栏与导航栏

**是什么**: 系统UI状态栏和导航栏  
**能干什么**:
- **状态栏高度** - 获取状态栏高度、适配刘海屏
- **隐藏状态栏** - 沉浸式体验、全屏视频
- **修改状态栏颜色** - API 21+、变色状态栏
- **浅色状态栏** - 浅色背景、深色图标
- **导航栏高度** - 获取导航栏高度、适配手势导航
- **隐藏导航栏** - 沉浸式体验、游戏
- **手势导航** - Android 10+、虚拟导航键
- **沉浸模式** - 全屏体验、sticky沉浸

### 🌙 20. 深色模式

**是什么**: Android 10+深色模式/夜间模式  
**能干什么**:
- **自动切换** - 跟随系统、电池 saver、日落时
- **强制深色** - 强制启用深色模式
- **主题适配** - Theme.Material3.DayNight、Force Dark
- **资源适配** - values-night、深色模式资源
- **WebView深色** - WebView适配深色、forceDark
- **自动图片** - 深色模式图片、drawble-night

---

## 📱 二、Android平台特性与组件（21-50）

### 📱 21. Activity 组件

**是什么**: 界面容器组件，Android四大组件之一  
**能干什么**:
- **UI容器** - 承载UI界面、显示内容、用户交互
- **用户交互** - 处理用户点击、处理用户输入、触摸事件
- **生命周期** - onCreate→onStart→onResume→onPause→onStop→onDestroy
- **任务栈** - Activity栈、返回键管理、taskAffinity
- **启动模式** - standard/singleTop/singleTask/singleInstance
- **数据传递** - Intent传递数据、startActivityForResult/ActivityResultLauncher
- **启动动画** - overridePendingTransition、转场动画
- **返回结果** - setResult、setResult(RESULT_OK, data)

**启动模式**:
- **standard** - 标准模式、每次创建新实例
- **singleTop** - 栈顶复用、不重复创建
- **singleTask** - 栈内单例、清除上方实例
- **singleInstance** - 单独栈、全局单例

### 🧩 22. Fragment 组件

**是什么**: 可重用的UI组件，现代Android开发核心  
**能干什么**:
- **UI模块化** - UI模块化、可复用、组合式UI
- **组合UI** - 组合多个Fragment、灵活布局、ViewPager
- **生命周期** - onAttach→onCreate→onCreateView→onViewCreated→onStart→onResume→onPause→onStop→onDestroyView→onDestroy→onDetach
- **Fragment事务** - Fragment切换、添加/移除/替换、addToBackStack
- **数据传递** - Fragment间通信、ViewModel共享、setFragmentResult
- **回栈** - addToBackStack、返回键恢复、popBackStack
- **DialogFragment** - 对话框Fragment、生命周期管理
- **选项菜单** - onCreateOptionsMenu、onOptionsItemSelected

### 🎭 23. Service 组件

**是什么**: 后台服务组件，Android四大组件之一  
**能干什么**:
- **后台任务** - 后台长时间运行、不依赖UI、播放音乐/下载
- **音乐播放** - 后台播放音乐、服务常驻、前台服务
- **下载任务** - 后台下载、不阻塞UI、进度通知
- **定时任务** - 定时执行任务、AlarmManager配合
- **IntentService** - 串行执行任务、自动停止（已废弃，用WorkManager）
- **前台服务** - 通知栏显示、不易被杀、startForeground
- **后台服务** - 后台运行、Android 8.0+限制
- **生命周期** - onCreate→onStartCommand→onDestroy

### 📡 24. BroadcastReceiver 组件

**是什么**: 广播接收器，Android四大组件之一  
**能干什么**:
- **系统广播** - 接收系统广播、开机关机/网络变化/屏幕亮灭
- **应用广播** - 应用内广播、组件通信、自定义广播
- **有序广播** - 有序传递、可中断、abortBroadcast
- **本地广播** - LocalBroadcastManager、应用内广播、更安全
- **动态注册** - 代码动态注册、生命周期可控、registerReceiver
- **静态注册** - Manifest注册、应用启动即可接收
- **权限控制** - sendBroadcast带权限、permission参数
- **常用系统广播** - BOOT_COMPLETED/CONNECTIVITY_CHANGE/BATTERY_CHANGED

### 🗄️ 25. ContentProvider 组件

**是什么**: 数据共享组件，Android四大组件之一  
**能干什么**:
- **跨应用数据共享** - 应用间共享数据、统一访问接口
- **数据抽象** - 隐藏数据源、统一访问方式、URI访问
- **系统ContentProvider** - 访问系统数据（联系人/媒体/设置/通话记录/日历）
- **权限控制** - 通过权限控制访问、READ_CONTACTS等权限
- **数据监听** - ContentObserver监听数据变化、registerContentObserver
- **URI匹配** - UriMatcher匹配URI、支持通配符、content://
- **增删改查** - insert/delete/update/query操作、getType
- **批量操作** - bulkInsert、applyBatch

### 📨 26. Intent 消息机制

**是什么**: 组件间通信的信使  
**能干什么**:
- **启动组件** - 启动Activity/Service/BroadcastReceiver
- **传递数据** - 携带数据、putExtra传递键值对
- **隐式Intent** - 声明Action/Category、系统匹配组件、应用间跳转
- **显式Intent** - 指定类名、直接启动、Intent(this, MainActivity::class.java)
- **返回结果** - startActivityForResult/Activity Result API、onActivityResult
- **Flag控制** - Flag控制启动模式、FLAG_ACTIVITY_NEW_TASK、FLAG_ACTIVITY_CLEAR_TOP
- **Action常量** - ACTION_VIEW/ACTION_SEND/ACTION_PICK等系统Action
- **数据传递** - putExtra、putExtras、getXXXExtra

### 🎢 27. Intent Filter

**是什么**: Intent过滤器，声明组件可响应的Intent  
**能干什么**:
- **隐式Intent** - 过滤隐式Intent、匹配Action/Category/Data
- **组件声明** - 在Manifest声明、组件可响应的Intent
- **Action匹配** - 自定义Action、系统Action、android.intent.action.VIEW
- **Category匹配** - DEFAULT/BROWSER等Category、android.intent.category.DEFAULT
- **Data匹配** - URI/scheme/mimeType匹配、content://、http://
- **DeepLink** - 网页链接启动App、应用间跳转、autoVerify验证
- **优先级** - android:priority、优先级高的优先响应

### 📡 28. 广播类型

**是什么**: Android广播的分类  
**能干什么**:
- **普通广播** - 异步发送、所有接收者同时接收、无序
- **有序广播** - 同步发送、按优先级依次接收、可中断
- **本地广播** - 应用内广播、不跨应用、更安全高效
- **系统广播** - 系统发送的广播、应用可接收、BOOT_COMPLETED等
- **应用广播** - 应用自定义广播、应用内通信
- **粘性广播** - 已废弃、sendStickyBroadcast

### 🔗 29. IPC 进程间通信

**是什么**: 跨进程通信机制  
**能干什么**:
- **跨进程通信** - 不同进程间数据交换、进程隔离
- **多进程App** - 同一App多进程、:remote、android:process
- **AIDL** - Android接口定义语言、简化IPC、自动生成代码
- **Messenger** - 基于Message的IPC、串行处理、轻量级
- **Binder** - Android底层IPC、高效安全、一次拷贝
- **ContentProvider** - 跨进程数据共享、统一接口
- **共享文件** - 文件共享、多进程读写需同步
- **Socket** - 网络IPC、TCP/UDP

### 📊 30. 进程与线程

**是什么**: Android进程和线程模型  
**能干什么**:
- **多进程** - 四大组件可运行在不同进程、android:process、多进程App
- **进程优先级** - 前台/可见/服务/后台/空进程、影响进程回收
- **进程生命周期** - 创建→运行→销毁、LRU回收、内存不足时
- **主线程** - UI线程、更新UI必须在主线程、ANR检测
- **子线程** - 耗时操作、网络/数据库/计算
- **线程创建** - Thread/ExecutorService/协程
- **线程池** - 复用线程、避免频繁创建

### 🎯 31. 应用生命周期

**是什么**: 应用的生命周期状态  
**能干什么**:
- **应用状态** - 前台/后台、热启动/冷启动、切换应用
- **进程生命周期** - 进程创建/销毁、低内存杀手
- **ActivityManager** - getRunningAppProcesses、getRunningTasks
- **Application onCreate** - 应用启动时、最早初始化
- **Activity栈** - 任务栈管理、返回栈
- **应用切换** - onTrimMemory、onLowMemory、内存警告
- **后台限制** - 后台服务限制、后台定位限制、省电优化

### 💾 32. 应用沙箱

**是什么**: Android应用隔离机制  
**能干什么**:
- **进程隔离** - 每个应用独立进程、进程ID、UID隔离
- **权限隔离** - 每个应用独立权限、权限声明
- **文件隔离** - 应用私有目录、/data/data/包名、其他应用无法访问
- **数据隔离** - SharedPreferences/Database私有、需权限共享
- **代码隔离** - 独立ClassLoader、类隔离
- **安全沙箱** - 限制系统访问、需权限才能访问敏感资源

### 🔐 33. 应用权限

**是什么**: Android权限系统  
**能干什么**:
- **权限声明** - Manifest声明权限、uses-permission
- **运行时权限** - Android 6.0+动态请求、checkSelfPermission/requestPermissions
- **权限组** - 同组权限任一授权、全组生效、LOCATION_GROUP
- **特殊权限** - 系统级特殊权限、需特殊处理、SYSTEM_ALERT_WINDOW
- **权限解释** - shouldShowRequestPermissionRationale、解释为什么需要
- **权限回调** - onRequestPermissionsResult回调结果
- **权限检查** - ContextCompat.checkSelfPermission
- **批量请求** - 一次请求多个权限

### 📋 34. 常用权限列表

**是什么**: Android常用权限汇总  
**能干什么**:
- **网络权限** - INTERNET网络访问、ACCESS_NETWORK_STATE网络状态
- **存储权限** - READ/WRITE_EXTERNAL_STORAGE外部存储（分区存储后废弃）
- **相机权限** - CAMERA相机、拍照录像
- **位置权限** - ACCESS_FINE_LOCATION精确定位、ACCESS_COARSE_LOCATION粗略定位
- **录音权限** - RECORD_AUDIO录音
- **联系人权限** - READ_CONTACTS读联系人、WRITE_CONTACTS写联系人
- **短信权限** - SEND_SMS发送短信、READ_SMS读短信
- **电话权限** - READ_PHONE_STATE电话状态、CALL_PHONE拨打电话
- **蓝牙权限** - BLUETOOTH蓝牙、BLUETOOTH_ADMIN蓝牙管理
- **通知权限** - POST_NOTIFICATIONS通知（Android 13+）

### 🔐 35. 特殊权限

**是什么**: 系统级特殊权限  
**能干什么**:
- **SYSTEM_ALERT_WINDOW** - 悬浮窗权限、draw over other apps
- **WRITE_SETTINGS** - 修改系统设置、write system settings
- **MANAGE_EXTERNAL_STORAGE** - 访问所有文件、Android 11+
- **REQUEST_INSTALL_PACKAGES** - 安装应用权限、安装APK
- **ACCESS_BACKGROUND_LOCATION** - 后台定位、Android 10+
- **MANAGE_MEDIA** - 修改媒体文件、Android 11+
- **PHONE_CALL** - 直接拨打电话、无需拨号界面

### 📍 36. 定位服务

**是什么**: Android定位相关能力  
**能干什么**:
- **GPS定位** - LocationManager.GPS_PROVIDER、高精度、室内无信号
- **网络定位** - LocationManager.NETWORK_PROVIDER、基站/WiFi、精度低
- **被动定位** - LocationManager.PASSIVE_PROVIDER、被动接收位置
- **FusedLocationProvider** - Google位置服务、融合定位、更好的精度和省电
- **地理围栏** - Geofencing、进出围栏触发、位置提醒
- **后台定位** - ACCESS_BACKGROUND_LOCATION、Android 10+限制
- **定位权限** - ACCESS_FINE_LOCATION、ACCESS_COARSE_LOCATION
- **位置监听** - requestLocationUpdates、定位变化监听

### 🗺️ 37. 地图SDK

**是什么**: 第三方地图服务  
**能干什么**:
- **高德地图** - 高德地图SDK、国内常用、定位/地图/导航/路径规划
- **百度地图** - 百度地图SDK、定位/地图/导航/周边检索
- **Google Maps** - Google地图SDK、国外常用、地图/定位/导航
- **地图显示** - 显示地图、缩放/旋转/移动、标记/折线/多边形
- **定位功能** - 定位SDK、连续定位、地理编码
- **路径规划** - 驾车/步行/公交路线、距离计算、时间估算
- **POI搜索** - 周边检索、关键词搜索、 autocomplete
- **离线地图** - 离线下载、离线导航

### 📷 38. 相机能力

**是什么**: Android相机相关能力  
**能干什么**:
- **Camera1** - 旧相机API、android.hardware.Camera、已废弃
- **Camera2** - 新相机API、android.hardware.camera2、更强大复杂
- **CameraX** - Jetpack相机库、简化相机开发、推荐使用
- **拍照** - 拍照片、设置参数、对焦/闪光灯/曝光
- **录像** - 录视频、MediaRecorder、CameraX Video
- **前后摄像头** - 前置/后置、多摄像头同时打开
- **相机权限** - CAMERA权限、运行时权限
- **相机特性** - 自动对焦、人脸检测、HDR、夜景

### 🎤 39. 录音能力

**是什么**: Android录音相关能力  
**能干什么**:
- **MediaRecorder** - 录音类、MediaRecorder.AudioSource.MIC
- **AudioRecord** - 更底层的录音、实时音频数据
- **录音权限** - RECORD_AUDIO、运行时权限
- **音频格式** - AAC/AMR/3GP、采样率、比特率
- **实时处理** - 实时音频处理、音频可视化
- **录音文件** - 保存到文件、File/OutputStream

### 📞 40. 电话能力

**是什么**: Android电话相关能力  
**能干什么**:
- **拨打电话** - Intent.ACTION_CALL、CALL_PHONE权限
- **拨号器** - Intent.ACTION_DIAL、跳转拨号界面
- **读取通话记录** - READ_CALL_LOG、读取历史通话
- **监听电话状态** - TelephonyManager、通话状态监听
- **电话状态** - IDLE/RINGING/OFFHOOK、空闲/响铃/通话
- **SIM卡信息** - TelephonyManager、SIM卡运营商/号码
- **电话权限** - READ_PHONE_STATE、敏感权限

### 💬 41. 短信能力

**是什么**: Android短信相关能力  
**能干什么**:
- **发送短信** - SmsManager、发送文本短信、分段发送
- **接收短信** - BroadcastReceiver接收、ACTION_SMS_RECEIVED
- **短信权限** - SEND_SMS/RECEIVE_SMS/READ_SMS
- **MMS** - 彩信、发送多媒体消息
- **WAP PUSH** - 接收WAP推送消息
- **读取短信** - content://sms/、读取短信内容

### 📶 42. 蓝牙能力

**是什么**: Android蓝牙相关能力  
**能干什么**:
- **经典蓝牙** - BluetoothAdapter、蓝牙配对、SPP通信
- **BLE低功耗蓝牙** - BluetoothLeScanner、低功耗、扫描/连接/通信
- **蓝牙权限** - BLUETOOTH/BLUETOOTH_ADMIN、Android 12+新权限
- **蓝牙扫描** - scanLeDevices、扫描周围设备
- **蓝牙连接** - BluetoothDevice、connectGatt、连接GATT服务
- **GATT服务** - Service/Characteristic、读写数据
- **BLE beacon** - iBeacon/Eddystone、 proximity sensing

### 📡 43. WiFi能力

**是什么**: Android WiFi相关能力  
**能干什么**:
- **WiFi扫描** - WifiManager、扫描WiFi、getScanResults
- **WiFi连接** - 连接指定WiFi、addNetwork、enableNetwork
- **WiFi信息** - 获取连接信息、getConnectionInfo、IP地址
- **WiFi P2P** - WiFi Direct、点对点连接、无需热点
- **WiFi热点** - 创建热点、setWifiApEnabled
- **WiFi锁定** - WifiLock、保持WiFi、屏幕关闭不断网
- **WiFi权限** - ACCESS_WIFI_STATE、CHANGE_WIFI_STATE

### 📶 44. 蜂窝网络

**是什么**: Android蜂窝网络相关能力  
**能干什么**:
- **TelephonyManager** - 蜂窝网络管理、运营商信息
- **网络类型** - 2G/3G/4G/5G、getNetworkType
- **SIM卡** - SIM卡状态、getSimSerialNumber、getSimOperator
- **信号强度** - 信号强度、listen信号变化
- **漫游** - 漫游状态、isNetworkRoaming
- **双卡** - 双卡双待、SubscriptionManager
- **运营商** - MCC/MNC、PLMN码

### 📡 45. NFC能力

**是什么**: Android近场通信能力  
**能干什么**:
- **NFC标签** - 读写NFC标签、NDEF格式
- **卡模拟** - HCE、卡片模拟、手机当卡用
- **P2P模式** - Android Beam、点对点传输
- **支付** - NFC支付、Huawei Pay/小米Pay
- **NFC权限** - NFC、运行时权限
- **NdefMessage** - NDEF消息、解析/编写

### 🔋 46. 电池与电源

**是什么**: Android电池相关能力  
**能干什么**:
- **电池信息** - BatteryManager、电池状态/电量/温度
- **充电状态** - 充电中/充满/未充电、USB/AC充电
- **WakeLock** - 保持唤醒/屏幕常亮、PARTIAL_WAKE_LOCK
- **Doze模式** - 低电量模式、系统休眠、限制网络
- **App Standby** - 应用待机、长期不活跃应用限制
- **电池优化** - 加入电池优化白名单、请求忽略电池优化
- **电量统计** - BatteryStats、耗电量分析

### 🔔 47. 通知系统

**是什么**: Android通知机制  
**能干什么**:
- **状态栏通知** - NotificationManager、状态栏图标
- **通知渠道** - NotificationChannel、Android 8.0+必需
- **通知样式** - 大文本/大图片/收件箱样式、NotificationCompat.Style
- **通知行为** - 点击跳转/PendingIntent、按钮动作
- **通知组** - 组合通知、setGroup
- **通知badge** - 角标、应用图标数字
- **通知权限** - POST_NOTIFICATIONS、Android 13+必需
- **通知监听** - NotificationListenerService、监听通知

### 🔊 48. 音频系统

**是什么**: Android音频系统  
**能干什么**:
- **AudioManager** - 音频管理、音量/模式/焦点
- **音频播放** - MediaPlayer/SoundPool/ExoPlayer
- **音频录制** - MediaRecorder/AudioRecord
- **音频焦点** - 音频焦点管理、requestAudioFocus
- **音频会话** - 音频会话ID、setAudioSessionId
- **静音模式** - 静音/振动/响铃、getRingerMode
- **音量控制** - 调节音量、adjustStreamVolume
- **音频路由** - 音频输出、扬声器/耳机/蓝牙

### 🎬 49. 多媒体能力

**是什么**: Android多媒体相关能力  
**能干什么**:
- **视频播放** - MediaPlayer/ExoPlayer、本地/网络视频
- **音频播放** - MediaPlayer、音频播放、后台播放
- **视频录制** - MediaRecorder/CameraX、视频录制
- **媒体库** - MediaStore、访问媒体文件、query/insert/update/delete
- **媒体扫描** - MediaScannerConnection、扫描文件
- **媒体元数据** - MediaMetadataRetriever、提取元数据
- **媒体控制** - MediaSession/ MediaController、媒体控制
- **画中画** - Picture-in-Picture、视频小窗

### 🌐 50. 网络能力

**是什么**: Android网络相关能力  
**能干什么**:
- **网络类型** - WiFi/Mobile/Ethernet、getNetworkType
- **网络状态** - 网络连接/断开、CONNECTIVITY_ACTION
- **网络变化** - NetworkCallback、网络变化监听
- **HTTP请求** - HttpURLConnection/OkHttp/Retrofit
- **WebSocket** - 长连接/实时通信
- **网络权限** - INTERNET、必需权限
- **VPN** - VPN服务、VpnService
- **网络安全** - HTTPS、网络安全配置、证书固定

---

## 🎨 三、UI组件与布局（51-80）

### 🎨 51. View 基础组件

**是什么**: Android UI的基础组件系统  
**能干什么**:
- **UI组件** - 提供丰富的UI组件（TextView、Button、ImageView、EditText等）
- **布局管理** - 组织UI布局、定位子组件、ViewGroup容器
- **事件处理** - 处理点击/触摸/按键等事件、OnClickListener/OnTouchListener
- **自定义View** - 创建自定义组件、自定义绘制逻辑、onDraw
- **动画效果** - 属性动画/补间动画/转场动画、Animator
- **触摸反馈** - Ripple效果/点击反馈/状态变化、selector
- **属性** - 宽高/边距/padding/背景/可见性
- **测量布局** - measure/layout/draw、测量/布局/绘制流程

### 🧩 52. ViewGroup 容器

**是什么**: 可包含其他View的容器组件  
**能干什么**:
- **容器功能** - 包含多个子View、管理子View布局
- **布局控制** - 决定子View位置、控制子View大小、onLayout
- **事件分发** - 分发触摸事件到子View、onInterceptTouchEvent拦截
- **自定义布局** - 创建自定义布局容器、自定义测量逻辑
- **性能优化** - 减少布局层级、优化绘制性能

### 📐 53. LinearLayout 线性布局

**是什么**: 线性布局容器，子View按水平或垂直排列  
**能干什么**:
- **线性排列** - 子View按顺序排列、horizontal/vertical方向
- **权重分配** - layout_weight按比例分配空间、动态计算
- **对齐控制** - gravity控制对齐方式、layout_gravity控制自身对齐
- **分隔线** - divider属性添加分隔线、showDividers控制显示
- **嵌套** - 可多层嵌套、但影响性能

### 🎯 54. RelativeLayout 相对布局

**是什么**: 相对布局容器，子View相对定位  
**能干什么**:
- **相对定位** - 相对父容器定位、相对其他子View定位
- **对齐方式** - 对齐父容器边、对齐其他View边、layout_align
- **位置关系** - 在某个View上方/下方/左侧/右侧、layout_to
- **居中显示** - 水平居中/垂直居中/完全居中、centerInParent

### 🔗 55. ConstraintLayout 约束布局

**是什么**: 约束布局，现代推荐的布局方式  
**能干什么**:
- **约束关系** - 通过约束定位子View、相对其他View或父容器
- **性能优化** - 减少布局层级、提升布局性能、扁平化
- **可视化编辑** - Android Studio可视化编辑、拖拽设计
- **宽高比** - layout_constraintDimensionRatio设置宽高比、16:9
- **链条** - 创建链条模式、CHAIN_SPREAD/权重分配
- **辅助线** - Guideline辅助线/Barrier屏障/Reference引用
- **百分比布局** - percent布局、适配不同屏幕

### 🃏 56. FrameLayout 帧布局

**是什么**: 帧布局容器，子View叠加显示  
**能干什么**:
- **叠加显示** - 子View叠加在一起、后添加的在上层
- **简单布局** - 适合简单叠加场景、单个子View填充
- **进度加载** - 常用于进度框、加载框叠加
- **Fragment容器** - 常用作Fragment容器、Fragment切换

### 📊 57. RecyclerView 列表

**是什么**: 高性能列表组件，替代ListView  
**能干什么**:
- **高效列表** - 复用Viewholder、减少内存占用、流畅滚动
- **布局管理** - LinearLayoutManager线性、GridLayoutManager网格、StaggeredGridLayoutManager瀑布流
- **列表动画** - Item添加删除动画、Item移动动画、DefaultItemAnimator
- **多样式** - 多种Item类型、getItemViewType、MultiTypeAdapter
- **分隔线** - ItemDecoration添加分隔线、分组、DividerItemDecoration
- **点击事件** - Item点击、长按、滑动删除、OnItemTouchListener
- **分页加载** - 配合Paging库实现分页、loadMore

```kotlin
// 基本使用
val recyclerView = findViewById<RecyclerView>(R.id.recycler)
recyclerView.layoutManager = LinearLayoutManager(this)
recyclerView.adapter = MyAdapter(dataList)
```

### 📜 58. ScrollView 滚动容器

**是什么**: 可滚动的容器  
**能干什么**:
- **垂直滚动** - 内容超出屏幕时可滚动查看
- **嵌套滚动** - 嵌套ScrollView、NestedScrollView支持嵌套
- **滚动监听** - setOnScrollChangeListener、监听滚动位置
- **平滑滚动** - smoothScrollTo平滑滚动到指定位置、scrollTo

### 🧭 59. ViewPager/ViewPager2 滑动页面

**是什么**: 可滑动的页面容器  
**能干什么**:
- **页面滑动** - 左右滑动切换页面、手势支持
- **页面预加载** - 预加载相邻页面、setOffscreenPageLimit
- **页面指示器** - TabLayout指示器、小圆点指示器、TabLayoutMediator
- **页面切换** - setCurrentItem程序控制切换、监听页面切换
- **Fragment适配** - FragmentPagerAdapter、FragmentStatePagerAdapter

### 🖼️ 60. ImageView 图片组件

**是什么**: 图片显示组件  
**能干什么**:
- **图片显示** - 显示本地图片、显示网络图片（需库支持）
- **缩放类型** - centerCrop/centerInside/fitCenter/fitXY、scaleType
- **圆角图片** - 通过Shape实现、通过CardView实现
- **圆形图片** - CircleImageView、自定义View实现
- **图片着色** - tint属性、setColorTint
- **点击效果** - selector状态变化、Ripple效果
- **矩阵变换** - Matrix、旋转/缩放/平移

### 📝 61. TextView 文本组件

**是什么**: 文本显示组件  
**能干什么**:
- **文本显示** - 显示单行文本、显示多行文本
- **样式设置** - 字体大小、字体颜色、字体样式、字体
- **富文本** - SpannableString富文本、ClickableSpan可点击文本
- **文本省略** - ellipsize省略号、maxLines最大行数
- **文本阴影** - shadowColor阴影颜色、shadowDx阴影偏移
- **文本选择** - setTextIsSelectable可复制、textIsSelectable
- **自动换行** - singleLine单行、自动换行
- **行高** - lineHeight行高、lineSpacingExtra
- **字母间距** - letterSpacing、letterSpacing

### 🔘 62. Button 按钮

**是什么**: 按钮组件，继承自TextView  
**能干什么**:
- **点击事件** - onClick监听、处理用户点击
- **样式定制** - 背景色、文字颜色、圆角边框
- **状态变化** - pressed状态、selector状态切换
- **图标按钮** - 图标+文字、纯图标按钮、drawableLeft
- **点击效果** - Ripple水波纹效果、foreground
- **禁用状态** - enabled状态、改变禁用样式
- **MaterialButton** - Material Design按钮、支持图标/圆角/边框

### 📂 63. EditText 输入框

**是什么**: 可编辑文本框，继承自TextView  
**能干什么**:
- **文本输入** - 单行输入、多行输入、密码输入
- **输入类型** - number数字、email邮箱、phone电话、date日期、textPassword
- **输入限制** - maxLength最大长度、digits允许字符、inputFilters
- **提示文本** - hint提示、hintTextColor提示颜色
- **监听变化** - TextWatcher监听文本变化、beforeTextChanged
- **自动完成** - AutoCompleteTextView自动完成、建议列表
- **焦点管理** - requestFocus请求焦点、clearFocus清除焦点
- **光标** - selectionStart/selectionEnd、setSelection
- **TextInputLayout** - Material Design输入框、浮动标签/错误提示

### 🎛️ 64. ProgressBar 进度条

**是什么**: 进度条组件  
**能干什么**:
- **进度显示** - 显示加载进度、显示百分比
- **样式选择** - 圆形进度条、水平进度条、style
- **不确定状态** - 不确定进度动画、indeterminate
- **自定义颜色** - tint属性设置颜色、progressTint
- **水平进度条** - setProgress设置进度、getMax最大值
- **Material进度** - CircularProgressIndicator、ProgressIndicator

### 🎚️ 65. SeekBar 滑动条

**是什么**: 可拖动的进度条  
**能干什么**:
- **拖动调节** - 用户拖动调节进度、音量亮度调节
- **进度监听** - onProgressChanged监听进度变化、SeekBar.OnSeekBarChangeListener
- **样式定制** - 颜色、滑块样式、进度条高度、thumb
- **初始值** - progress初始进度、max最大值
- **禁用状态** - enabled是否可拖动

### 💾 66. CheckBox 复选框

**是什么**: 复选框组件  
**能干什么**:
- **多选功能** - 支持多个选项、独立状态、CheckedChangeListener
- **状态监听** - setOnCheckedChangeListener监听状态变化
- **初始状态** - checked初始选中状态
- **文本显示** - 可显示文本在复选框旁、text属性
- **样式定制** - 自定义选中图标、自定义颜色、buttonTint

### 📻 67. RadioButton & RadioGroup

**是什么**: 单选框和单选框组  
**能干什么**:
- **单选功能** - 同组内只能选中一个、互斥选择、RadioGroup
- **分组管理** - RadioGroup管理多个RadioButton
- **状态监听** - setOnCheckedChangeListener监听选中变化
- **横向/纵向** - RadioGroup的orientation属性、horizontal/vertical
- **默认选中** - check方法设置默认选中

### 🔃 68. Switch 开关

**是什么**: 开关组件，替代ToggleButton  
**能干什么**:
- **开关功能** - 打开/关闭状态、iOS风格开关、Material Design
- **状态监听** - setOnCheckedChangeListener监听开关变化
- **文本显示** - showText属性、textOn/textOff文字
- **样式定制** - track颜色、thumb颜色、SwitchCompat
- **初始状态** - checked初始选中状态

### 🏔️ 69. Toolbar 工具栏

**是什么**: 应用栏组件，替代ActionBar  
**能干什么**:
- **应用标题** - 显示应用名、显示页面标题、setTitle
- **导航按钮** - 返回按钮、汉堡菜单按钮、setNavigationIcon
- **菜单项** - 显示选项菜单、处理菜单点击、inflateMenu
- **自定义视图** - 添加自定义View、搜索框等、addView
- **样式定制** - 颜色、高度、背景、popupTheme
- **滚动隐藏** - 滚动时隐藏/显示、app:layout_scrollFlags
- **CoordinatorLayout** - 配合使用、滚动联动

### 🗂️ 70. TabLayout 标签页

**是什么**: 标签页组件  
**能干什么**:
- **标签页** - 显示多个标签、支持滑动、TabLayout
- **指示器** - 选中指示器、指示器样式、tabIndicator
- **图标文字** - 图标+文字、纯文字、纯图标、setIcon/setText
- **ViewPager联动** - 与ViewPager2联动、自动切换页面、TabLayoutMediator
- **模式选择** - fixed固定宽度、scrollable可滚动、tabMode
- **选中监听** - addOnTabSelectedListener监听选中

### 🎨 71. Material Design 组件

**是什么**: Material Design设计组件库  
**能干什么**:
- **MaterialButton** - Material按钮、支持图标/圆角/边框/波纹
- **MaterialCardView** - Material卡片、圆角/阴影/ elevation
- **TextInputLayout** - 输入框容器、浮动标签/错误提示/字符计数
- **BottomNavigationView** - 底部导航、菜单项/选中监听
- **AppBarLayout** - 应用栏、滚动联动/折叠效果
- **CoordinatorLayout** - 协调布局、子View联动/behavior
- **CollapsingToolbarLayout** - 可折叠工具栏、滚动折叠效果
- **BottomSheet** - 底部抽屉、BottomSheetDialog/BottomSheetFragment
- **Snackbar** - 简易通知、可操作通知、类似Toast
- **FAB** - FloatingActionButton、悬浮按钮
- **Material主题** - Theme.Material3、Material You

### 🎭 72. WebView 网页容器

**是什么**: 内嵌浏览器组件  
**能干什么**:
- **加载网页** - loadUrl加载网页、loadData加载HTML
- **WebViewClient** - 页面加载监听、shouldOverrideUrlLoading拦截
- **WebChromeClient** - 浏览器交互、进度/标题/图标
- **JavaScript** - 启用JS、addJavascriptInterface交互
- **Cookie** - CookieManager管理cookie
- **缓存** - 缓存控制、清除缓存
- **缩放** - 支持缩放、setSupportZoom
- **文件下载** - setDownloadListener、下载监听
- **文件上传** - 文件选择、WebChromeClient.FileChooser
- **调试** - setWebContentsDebuggingEnabled、Chrome调试
- **User-Agent** - 自定义UA、setUserAgentString
- **深色模式** - forceDark、自动适配深色
- **安全** - 禁用file://、HTTPS only

### 📊 73. 图表库

**是什么**: Android图表显示库  
**能干什么**:
- **MPAndroidChart** - 强大的图表库、支持多种图表类型
- **图表类型** - 折线图/柱状图/饼图/雷达图/气泡图
- **动画** - 图表动画、数据显示动画
- **交互** - 点击/高亮/缩放/手势交互
- **自定义** - 自定义样式/自定义渲染
- **AnyChart** - 商业图表库、更多图表类型
- **Vico** - Compose图表库、Jetpack Compose

### 🗺️ 74. 地图组件

**是什么**: 地图显示组件  
**能干什么**:
- **地图显示** - 显示地图、缩放/旋转/移动
- **标记** - Marker标记、自定义图标、InfoWindow
- **折线** - Polyline折线、路径规划
- **多边形** - Polygon多边形、区域显示
- **定位** - 我的位置、定位按钮、MyLocation
- ** heatmap** - 热力图、密度显示
- **聚类** - Marker聚类、聚合显示

### 📸 75. 图片选择器

**是什么**: 图片/视频选择组件  
**能干什么**:
- **相册选择** - 打开系统相册、ACTION_PICK
- **相机拍照** - 打开相机、ACTION_IMAGE_CAPTURE
- **多选** - 多选图片、Intent.EXTRA_ALLOW_MULTIPLE
- **裁剪** - 图片裁剪、uCrop
- **压缩** - 图片压缩、Luban
- **第三方库** - PictureSelector、Matisse、知乎组件库

### 🎬 76. GIF播放

**是什么**: GIF动画播放  
**能干什么**:
- **Glide** - 支持GIF播放、自动播放
- **GifImageView** - 专门播放GIF的控件
- **帧动画** - AnimationDrawable、逐帧播放
- **控制** - 暂停/播放/跳帧
- **Lottie** - 支持导出GIF、After Effects

### 🎞️ 77. 视频播放

**是什么**: 视频播放能力  
**能干什么**:
- **VideoView** - 简单视频播放、setVideoPath
- **MediaPlayer** - 底层播放器、SurfaceView播放
- **ExoPlayer** - Google推荐、功能强大、支持多种格式
- **播放控制** - 播放/暂停/seek、进度条、音量
- **全屏播放** - 全屏切换、横竖屏
- **列表播放** - RecyclerView视频、列表自动播放
- **缓存** - 视频缓存、预加载

### 🎵 78. 音频播放

**是什么**: 音频播放能力  
**能干什么**:
- **MediaPlayer** - 播放音频、start/pause/stop/seek
- **SoundPool** - 短音效、适合游戏音效
- **ExoPlayer** - 流媒体、支持在线音频
- **后台播放** - Service后台播放、前台服务
- **播放控制** - 播放/暂停/上一曲/下一曲
- **播放列表** - 播放列表、循环模式
- **歌词** - 歌词同步、LRC解析
- **均衡器** - 均衡器、音效

### 🎪 79. 广告组件

**是什么**: 移动广告SDK  
**能干什么**:
- **AdMob** - Google广告、横幅/插屏/激励视频/原生广告
- **穿山甲** - 字节广告、国内主流
- **优量汇** - 腾讯广告、流量变现
- **广告类型** - Banner广告、插屏广告、开屏广告、激励视频、原生广告
- **广告加载** - 加载广告、显示广告、监听回调
- **广告过滤** - 流量过滤、广告过滤
- **收益** - 广告收益、eCPM

### 🎨 80. 自定义View

**是什么**: 自定义UI组件  
**能干什么**:
- **自定义绘制** - onDraw绘制、Canvas/Paint
- **自定义属性** - attrs.xml、declare-styleable、obtainStyledAttributes
- **测量** - onMeasure测量、MeasureSpec
- **布局** - onLayout布局、子View位置
- **触摸事件** - onTouchEvent、onInterceptTouchEvent
- **动画** - 属性动画、ValueAnimator
- **保存状态** - onSaveInstanceState、恢复状态
- **可访问性** - 无障碍支持

---

## 📦 四、数据存储（81-100）

### 🗄️ 81. SQLite 数据库

**是什么**: Android内置的关系型数据库  
**能干什么**:
- **关系型数据库** - 完整的SQL支持、事务支持、SQL语法
- **本地存储** - 持久化存储大量数据、结构化数据
- **复杂查询** - 支持复杂SQL查询、joins、聚合函数
- **索引优化** - 索引支持、查询性能优化、CREATE INDEX
- **事务** - 事务支持、begin transaction/commit/rollback
- **直接使用** - 通过SQLiteDatabase直接操作、execSQL/rawQuery
- **数据库文件** - /data/data/包名/databases/、.db文件

### 🏛️ 82. Room 数据库

**是什么**: Android官方SQLite ORM框架  
**能干什么**:
- **SQLite抽象** - 简化SQLite操作、无需写SQL、编译时生成SQL
- **编译时验证** - SQL语法检查、减少运行时错误、@Query注解
- **类型安全** - 类型安全的API、自动转换、@Entity/@Dao/@Database
- **LiveData支持** - 与LiveData集成、自动更新UI、@Query返回LiveData
- **Flow支持** - 与Kotlin Flow集成、响应式查询
- **数据库迁移** - Migration机制、版本升级、Database.Migration
- **多表查询** - @Relation关联查询、@Embedded嵌入
- **数据库查看** - Database Inspector、Android Studio查看

```kotlin
@Entity
data class User(@PrimaryKey val id: Int, val name: String)

@Dao
interface UserDao {
    @Query("SELECT * FROM user")
    fun getAll(): Flow<List<User>>
    
    @Insert
    suspend fun insert(user: User)
}

@Database(entities = [User::class], version = 1)
abstract class AppDatabase : RoomDatabase() {
    abstract fun userDao(): UserDao
}
```

### 🔍 83. ContentProvider 数据共享

**是什么**: 数据共享组件  
**能干什么**:
- **跨应用数据共享** - 应用间共享数据、统一访问接口、content://
- **数据抽象** - 隐藏数据源、统一访问方式
- **系统ContentProvider** - 访问系统数据（联系人/媒体/设置等）
- **权限控制** - 通过权限控制访问、READ_CONTACTS等权限
- **URI匹配** - UriMatcher匹配URI、支持通配符、*
- **数据监听** - ContentObserver监听数据变化、registerContentObserver
- **增删改查** - insert/delete/update/query操作、getType
- **批量操作** - bulkInsert批量插入、applyBatch批量事务

### 📁 84. 文件存储

**是什么**: Android文件系统存储  
**能干什么**:
- **内部存储** - 应用私有空间、/data/data/包名/、其他应用无法访问
- **外部存储** - 公共存储空间、/sdcard/、可访问其他应用文件
- **缓存文件** - 临时文件、getCacheDir、系统可能清理
- **文件操作** - 创建/读取/写入/删除文件、File API
- **目录结构** - 自动创建应用目录、filesDir/cacheDir等
- **分区存储** - Android 10+、Scoped Storage、应用私有

### 🖼️ 85. MediaStore 媒体库

**是什么**: Android媒体文件数据库  
**能干什么**:
- **媒体文件管理** - 访问图片/视频/音频文件、content://media/external/
- **查询媒体** - 查询媒体文件信息、缩略图、query
- **插入媒体** - 保存媒体文件到MediaStore、insert
- **删除媒体** - 删除媒体文件、delete、删除缩略图
- **更新媒体** - 更新文件信息、update、修改属性
- **分区存储** - Android 10+分区存储适配、IS_PENDING
- **MediaScanner** - 扫描文件、MediaScannerConnection

### 🔐 86. 加密存储

**是什么**: 数据加密存储  
**能干什么**:
- **Android Keystore** - 密钥存储、系统级保护、KeyStore
- **加密算法** - AES加密、RSA加密、Cipher
- **EncryptedSharedPreferences** - 加密的键值对、Jetpack Security
- **SQLCipher** - 数据库加密、SQLiteDatabase加密
- **文件加密** - 文件加密存储、CipherOutputStream
- **BiometricPrompt** - 生物识别解锁、指纹/面容

### 📊 87. 数据同步

**是什么**: 数据同步机制  
**能干什么**:
- **SyncAdapter** - 系统同步框架、自动同步
- **WorkManager** - 后台任务调度、定期同步
- **JobScheduler** - 系统任务调度、Android 5.0+
- **Firebase Sync** - 实时同步、Firebase Realtime Database
- **云端同步** - 云端备份、Google Drive/小米云同步
- **数据版本** - 数据版本控制、版本冲突处理

### 🔄 88. 数据迁移

**是什么**: 数据库版本迁移  
**能干什么**:
- **Room迁移** - Migration类、数据库版本升级
- **增量迁移** - 逐步迁移、version X → Y
- **数据备份** - 迁移前备份数据
- **数据回滚** - 迁移失败回滚、fallback
- **复杂迁移** - Schema变化、表结构变化
- **数据验证** - 迁移后验证数据

### 📱 89. 云端存储

**是什么**: 云端数据存储  
**能干什么**:
- **Firebase Firestore** - NoSQL数据库、实时同步、离线支持
- **Firebase Realtime Database** - 实时数据库、JSON存储
- **AWS Amplify** - AWS云服务、AppSync
- **Azure Mobile** - Azure移动服务、Easy Tables
- **自建API** - REST API、GraphQL

### 🗜️ 90. 数据压缩

**是什么**: 数据压缩存储  
**能干什么**:
- **GZIP压缩** - GZIPInputStream/GZIPOutputStream、压缩文本数据
- **ZIP压缩** - ZipInputStream/ZipOutputStream、压缩文件
- **图片压缩** - 质量压缩/尺寸压缩、Bitmap.compress
- **数据库压缩** - 数据库压缩、VACUUM
- **文件压缩** - 减少存储空间、加快传输

---

## 🌐 五、网络通信（101-120）

### 📡 101. 网络基础

**是什么**: Android网络相关基础能力  
**能干什么**:
- **网络类型** - WiFi/Mobile/Ethernet/VPN、getNetworkType
- **网络状态** - 网络连接/断开/切换、CONNECTIVITY_ACTION
- **网络变化** - NetworkCallback监听、registerNetworkCallback
- **网络权限** - INTERNET、必需权限、Manifest声明
- **网络配置** - 网络安全配置、network_security_config.xml
- **网络安全** - HTTPS强制、证书固定、防止中间人攻击

### 🌐 102. HTTP协议

**是什么**: HTTP网络协议  
**能干什么**:
- **GET/POST** - HTTP请求方法、GET获取数据/POST提交数据
- **HTTPS** - 加密HTTP、TLS/SSL、证书验证
- **HTTP/2** - HTTP/2协议、多路复用、头部压缩
- **HTTP缓存** - HTTP缓存机制、Cache-Control、ETag
- **Cookie** - Cookie管理、CookieManager、Session
- **UA** - User-Agent、浏览器标识、自定义UA

### 📦 103. OkHttp 客户端

**是什么**: Square高效HTTP客户端  
**能干什么**:
- **HTTP请求** - GET/POST/PUT/DELETE等请求、Request
- **连接池** - 连接复用、减少延迟、ConnectionPool
- **缓存** - 自动缓存、Cache、减少网络请求
- **拦截器** - 请求/响应拦截、Interceptor、添加token/日志/重试
- **HTTPS** - 自动TLS、证书校验、证书固定
- **WebSocket** - WebSocket支持、长连接、实时通信
- **异步请求** - enqueue异步、不阻塞主线程
- **超时控制** - 连接超时/读取超时/写入超时

```gradle
implementation 'com.squareup.okhttp3:okhttp:4.12.0'
```

### 🌐 104. Retrofit 网络库

**是什么**: Square类型安全的HTTP客户端  
**能干什么**:
- **REST API** - 定义REST接口、自动实现、@GET/@POST等注解
- **类型安全** - 编译时检查、类型转换、自动Gson解析
- **转换器** - Gson/Moshi/Protobuf等、Converter
- **协程支持** - suspend函数、协程请求
- **RxJava支持** - Observable/Flowable、RxJava适配器
- **拦截器** - 添加token/日志/重试、OkHttp拦截器
- **多baseUrl** - @Url动态指定url
- **文件上传** - @Multipart、@Part上传文件

```gradle
implementation 'com.squareup.retrofit2:retrofit:2.9.0'
implementation 'com.squareup.retrofit2:converter-gson:2.9.0'
```

### 📨 105. 网络请求拦截

**是什么**: 网络请求拦截器  
**能干什么**:
- **添加Header** - 添加通用Header、token/设备信息
- **日志拦截** - 打印请求/响应日志、HttpLoggingInterceptor
- **重试** - 失败重试、指数退避
- **缓存** - 网络缓存、CacheInterceptor
- **认证** - token认证、OAuth
- **签名** - 请求签名、防篡改

### 📦 106. 文件上传下载

**是什么**: 文件传输能力  
**能干什么**:
- **文件上传** - Multipart上传、@Multipart/@Part
- **进度监听** - 上传进度、RequestBody
- **断点续传** - 断点续传、Range请求
- **文件下载** - 下载文件、OkHttp下载
- **下载进度** - 下载进度监听
- **后台下载** - 后台下载、WorkManager/DownloadManager

### 🔐 107. 网络安全

**是什么**: Android网络安全机制  
**能干什么**:
- **HTTPS强制** - 默认HTTPS、HTTP需配置、cleartextTrafficPermitted
- **证书校验** - HTTPS证书校验、防止中间人攻击
- **证书固定** - 证书锁定、Certificate Pinner、防伪造
- **网络安全配置** - network_security_config.xml、自定义信任
- **域名配置** - 配置允许的域名、拒绝其他域名
- **调试配置** - debug版本允许HTTP、允许自签名证书

```xml
<!-- res/xml/network_security_config.xml -->
<network-security-config>
    <domain-config cleartextTrafficPermitted="true">
        <domain includeSubdomains="true">example.com</domain>
    </domain-config>
    <base-config cleartextTrafficPermitted="false">
        <trust-anchors>
            <certificates src="system" />
            <certificates src="user" />
        </trust-anchors>
    </base-config>
</network-security-config>
```

### 🔑 108. 网络认证

**是什么**: 网络请求认证机制  
**能干什么**:
- **Basic认证** - 用户名密码认证、Authorization: Basic
- **Bearer Token** - OAuth2 Token、Authorization: Bearer
- **API Key** - API密钥认证、Header/Query参数
- **签名认证** - 请求签名、MD5/HMAC-SHA256
- **OAuth2** - OAuth2认证、授权码模式
- **双向认证** - 客户端证书认证

### 📊 109. GraphQL

**是什么**: 数据查询语言  
**能干什么**:
- **精确查询** - 按需查询、避免过度获取、指定字段
- **强类型** - 类型系统、编译时检查、Schema
- **单个端点** - 单个URL、减少网络请求
- **实时订阅** - Subscription、实时更新
- **Apollo** - Apollo Android客户端、apollo-android

### 🔌 110. WebSocket

**是什么**: 双向通信协议  
**能干什么**:
- **实时通信** - 服务端主动推送、实时更新、聊天室
- **长连接** - 保持连接、减少握手开销
- **双向通信** - 客户端/服务端互发消息
- **OkHttp支持** - OkHttp原生支持、newWebSocket
- **心跳** - 心跳包、保持连接
- **应用场景** - 聊天/即时通讯/游戏/协同编辑

### 📦 111. DownloadManager 下载

**是什么**: 系统下载管理器  
**能干什么**:
- **后台下载** - 系统级后台下载、应用关闭继续下载
- **大文件** - 适合下载大文件、自动断点续传
- **通知栏** - 下载进度显示、下载完成通知
- **网络切换** - 自动处理网络切换、WiFi/Mobile
- **队列管理** - 多任务队列、优先级控制
- **查询下载** - 查询下载状态、Query

### 🔄 112. 数据同步

**是什么**: 网络数据同步  
**能干什么**:
- **SyncAdapter** - 系统同步框架、自动同步、省电
- **WorkManager** - 后台任务调度、定期同步
- **Firebase Sync** - 实时同步、Firestore/Realtime Database
- **轮询** - 定期轮询、JobScheduler/AlarmManager
- **推送** - 服务端推送、FCM/极光推送
- **增量同步** - 增量更新、timestamp/version

### 🌐 113. 网络状态监听

**是什么**: 网络状态变化监听  
**能干什么**:
- **网络变化** - 网络连接/断开监听、ConnectivityManager
- **WiFi切换** - WiFi切换监听、网络切换
- **网络类型** - 识别网络类型、WiFi/Mobile
- **网络质量** - 网络质量评估、带宽/延迟
- **离线处理** - 离线模式、缓存数据

### 📡 114. 推送服务

**是什么**: 消息推送服务  
**能干什么**:
- **FCM** - Firebase Cloud Messaging、Google官方推送
- **极光推送** - 国内推送、JPush、多渠道
- **个推** - 个推推送、Getui
- **华为推送** - 华为推送服务、HMS
- **小米推送** - 小米推送、MiPush
- **OPPO推送** - OPPO推送
- **vivo推送** - vivo推送
- **通知权限** - POST_NOTIFICATIONS、Android 13+

### 📨 115. 消息队列

**是什么**: 消息队列服务  
**能干什么**:
- **消息发送** - 发送消息到队列、生产者
- **消息接收** - 从队列接收消息、消费者
- **异步处理** - 异步消费、解耦合
- **可靠性** - 消息持久化、不丢失
- **重试机制** - 失败重试、死信队列
- **应用场景** - 延迟任务/批量处理/异步通知

---

## 🚀 六、跨平台开发（121-140）

### 📱 121. React Native

**是什么**: Facebook跨平台框架  
**能干什么**:
- **跨平台** - iOS/Android、代码复用、JavaScript开发
- **热更新** - CodePush、无需审核更新
- **原生组件** - Native Modules、原生组件桥接
- **性能** - 接近原生、JIT编译
- **生态** - 丰富第三方库、npm生态
- **学习成本** - JavaScript+React、Web开发者友好

### 🐦 122. Flutter

**是什么**: Google跨平台框架  
**能干什么**:
- **跨平台** - iOS/Android/Web/Desktop、一套代码
- **性能** - 接近原生、AOT编译、Dart语言
- **UI一致性** - UI完全一致、绘制引擎
- **热重载** - Hot Reload、快速开发
- **Widget** - 丰富的Widget、Material/Cupertino
- **性能优化** - 60fps、流畅度

### 🔧 123. Kotlin Multiplatform

**是什么**: Kotlin跨平台方案  
**能干什么**:
- **跨平台** - Android/iOS/Web/JVM、Kotlin语言
- **代码共享** - 业务逻辑共享、平台特定实现
- **原生性能** - 完全原生、编译为原生代码
- **互操作** - 与Swift/ObjC/Java互操作
- **KMP** - Kotlin Multiplatform Mobile、移动端
- **Compose Multiplatform** - 跨平台UI、Compose for Desktop/Web

### 📐 124. 小程序开发

**是什么**: 平台小程序生态  
**能干什么**:
- **微信小程序** - 微信生态、无需安装
- **支付宝小程序** - 支付宝生态
- **百度小程序** - 百度生态
- **字节跳动小程序** - 字节生态
- **QQ小程序** - QQ小程序
- **快应用** - 九大厂商联盟、免安装

### 🌐 125. PWA 渐进式Web应用

**是什么**: Progressive Web App  
**能干什么**:
- **Web应用** - 网页技术栈、HTML/CSS/JS
- **安装** - 可添加到主屏幕、类似原生应用
- **离线** - Service Worker、离线访问
- **推送** - Web Push、消息推送
- **更新** - 自动更新、无需审核
- **Android支持** - Chrome支持、添加到主屏幕

### 🎮 126. Unity 3D游戏

**是什么**: Unity游戏引擎  
**能干什么**:
- **3D游戏** - 3D游戏开发、C#脚本
- **2D游戏** - 2D游戏开发
- **Android发布** - 发布到Android、.apk/.aab
- **性能** - 优秀性能、OpenGL ES/Vulkan
- **资源** - 丰富资源、Asset Store
- **学习成本** - Unity+C#、学习曲线

### 🎮 127. Cocos2d-x 游戏引擎

**是什么**: 开源游戏引擎  
**能干什么**:
- **2D游戏** - 2D游戏开发、Lua/JS绑定
- **跨平台** - iOS/Android/Web、跨平台
- **性能** - 优秀性能、OpenGL ES
- **学习成本** - C++/Lua/JS、学习曲线
- **国产** - 国内流行、中文文档

### 🖥️ 128. 跨平台方案对比

**是什么**: 跨平台方案选型  
**能干什么**:
- **性能对比** - 原生 > Flutter > RN > 小程序 > PWA
- **开发效率** - 小程序 > RN > Flutter > 原生
- **UI一致性** - Flutter > RN > 小程序
- **热更新** - RN > 小程序 > Flutter > 原生
- **生态** - RN > Flutter > KMP
- **学习成本** - PWA（Web）> RN（JS）> Flutter（Dart）> 原生

**选型建议**:
- **性能优先** → 原生
- **快速开发** → 小程序
- **代码复用** → RN/Flutter
- **Android技术栈** → KMP
- **游戏** → Unity/Cocos2d-x

### 🎯 129. 混合开发

**是什么**: 原生+Web混合  
**能干什么**:
- **WebView** - 原生嵌入WebView、加载H5页面
- **JSBridge** - JavaScript桥接、Native与JS通信
- **Cordova** - 混合开发框架、插件生态
- **Ionic** - 基于Angular的混合开发
- **小程序容器** - 原生嵌入小程序、微信小程序SDK
- **Flutter模块** - 原生集成Flutter模块、Add-to-App

### 🔗 130. 原生与H5交互

**是什么**: 原生与WebView交互  
**能干什么**:
- **JSBridge** - Native与JS双向通信、接口封装
- **addJavascriptInterface** - Android原生JS桥接
- **evaluateJavascript** - Native调用JS
- **WebViewClient** - 拦截URL、自定义协议
- **消息通道** - postMessage、message事件监听
- **注入对象** - 注入Native对象到JS

---

## 🔐 七、安全与权限（141-160）

### 🔐 141. 应用签名

**是什么**: Android应用签名机制  
**能干什么**:
- **应用标识** - 确保应用来源可信、防止应用被替换
- **权限升级** - 签名相同可升级系统签名权限、signature权限
- **组件共享** - 相同签名的应用可共享组件、sharedUserId
- **应用更新** - 相同签名才能覆盖安装更新应用
- **系统应用** - 系统签名可安装到/system分区
- **Google Play** - 上架Google Play需要签名
- **签名文件** - keystore文件、密钥别名、密钥密码

### 🔨 142. 代码混淆

**是什么**: 代码保护技术  
**能干什么**:
- **ProGuard/R8** - 代码混淆、类名方法名替换
- **资源压缩** - shrinkResources、移除未使用资源
- **代码优化** - 优化字节码、提升性能
- **保持规则** - keep规则、不混淆特定代码
- **字符串加密** - 字符串加密、提高破解难度
- **mapping文件** - mapping.txt、还原混淆后的堆栈

### 🛡️ 143. 应用加固

**是什么**: APK安全加固  
**能干什么**:
- **代码保护** - DEX加固、防止反编译
- **资源保护** - 资源加密、防止资源窃取
- **防篡改** - 完整性校验、防止二次打包
- **环境检测** - 模拟器检测、Root检测
- **第三方加固** - 360加固/腾讯御安全/爱加密/梆梆加固

### 🔒 144. 防调试

**是什么**: 防止应用被调试  
**能干什么**:
- **调试检测** - 检测是否被调试、Debug.isDebuggerConnected()
- **模拟器检测** - 检测模拟器、Build.FINGERPRINT
- **Root检测** - 检测Root、su命令、Superuser.apk
- **Xposed检测** - 检测Xposed框架、XposedBridge
- **Frida检测** - 检测Frida Hook、端口检测
- **反调试** - 获取ptrace、attach拒绝

### 🔐 145. 证书校验

**是什么**: HTTPS证书校验  
**能干什么**:
- **证书绑定** - 证书固定、防止中间人攻击
- **自定义校验** - 自定义证书校验逻辑、X509TrustManager
- **信任锚点** - 配置信任证书、网络安全配置
- **双向认证** - 客户端证书认证
- **证书过期** - 检测证书过期、有效期验证

### 🔑 146. 密钥存储

**是什么**: Android密钥存储系统  
**能干什么**:
- **Android Keystore** - 系统级密钥存储、密钥永不离开设备
- **密钥生成** - 生成密钥对、KeyGenerator
- **密钥使用** - 签名/加密/解密、Cipher
- **生物识别** - 绑定生物识别、用户认证后使用
- **密钥导入** - 导入密钥、importKey
- **Hardware Backed** - 硬件支持、TEE

### 🔒 147. 数据加密

**是什么**: 数据加密保护  
**能干什么**:
- **AES加密** - 对称加密、AES/GCB/NoPadding
- **RSA加密** - 非对称加密、加密小数据
- **Hash** - 消息摘要、MD5/SHA-256
- **HMAC** - 消息认证码、防篡改
- **加密文件** - EncryptedFile、加密文件存储
- **加密SharedPreferences** - EncryptedSharedPreferences

### 🛡️ 148. WebView安全

**是什么**: WebView安全机制  
**能干什么**:
- **禁止file://** - 禁止访问本地文件、setAllowFileAccessFromFileURLs
- **限制JS** - 限制JS能力、removeJavascriptInterface
- **HTTPS only** - 强制HTTPS、mixedContent
- **白名单** - URL白名单、shouldOverrideUrlLoading
- **SameOrigin** - 同源策略、WebSecurityConfig
- **XSS防护** - XSS防护、转义HTML

### 🔐 149. ProGuard混淆规则

**是什么**: ProGuard混淆配置  
**能干什么**:
- **keep类** - 保持类不混淆、-keep class
- **keep成员** - 保持成员不混淆、keepclassmembers
- **keep注解** - 保持特定注解的类、@keep
- **移除日志** - 移除Log调用、assumenosideeffects
- **优化** - 优化代码、优化字节码

### 🔍 150. 安全检测工具

**是什么**: 安全检测工具  
**能干什么**:
- **MobSF** - 移动安全框架、静态/动态分析
- **QARK** - Quick Android Review Kit、漏洞扫描
- **Drozer** - Android安全测试框架
- **Frida** - 动态Hook、Hook Native/Java
- **Xposed** - Hook框架、模块开发
- **Burp Suite** - 抓包分析、修改请求

### 🔐 151. 存储权限适配

**是什么**: 存储权限演进适配  
**能干什么**:
- **分区存储** - Android 10+强制分区存储、应用私有目录
- **MediaStore** - 通过MediaStore访问公共媒体文件、query/insert/update/delete
- **SAF** - Storage Access Framework、文件选择器、ACTION_OPEN_DOCUMENT
- **MANAGE_EXTERNAL_STORAGE** - 访问所有文件、特殊权限、Manage External Storage
- **兼容性** - 不同版本适配、requestLegacyExternalStorage
- **文件选择器** - 系统文件选择器、ACTION_OPEN_DOCUMENT_TREE

### 📍 152. 位置权限适配

**是什么**: 位置权限使用适配  
**能干什么**:
- **精确定位** - ACCESS_FINE_LOCATION、GPS定位
- **粗略定位** - ACCESS_COARSE_LOCATION、基站定位
- **后台定位** - ACCESS_BACKGROUND_LOCATION、Android 10+
- **地理围栏** - Geofencing、地理围栏权限
- **位置说明** - 位置使用说明、为什么要位置权限
- **隐私政策** - 隐私政策、位置数据使用说明

### 📷 153. 相机权限适配

**是什么**: 相机权限使用适配  
**能干什么**:
- **CAMERA权限** - 拍照录像权限、运行时权限
- **Manifest声明** - uses-feature声明相机特性、uses-feature android:name="android.hardware.camera"
- **兼容性** - 检测相机是否存在、hasSystemFeature(PackageManager.FEATURE_CAMERA)
- **权限请求** - 运行时请求、说明用途、shouldShowRequestPermissionRationale
- **CameraX** - 简化相机使用、权限自动处理
- **相机特性** - 自动对焦/闪光灯、检查相机特性

### 🔐 154. 生物识别

**是什么**: 生物识别认证  
**能干什么**:
- **BiometricPrompt** - Android官方生物识别API、统一接口
- **指纹识别** - 指纹认证、FingerprintManager
- **面容识别** - 面容认证、Face Unlock
- **虹膜识别** - 虹膜认证、Samsung
- **密钥绑定** - 绑定密钥、生物识别解锁密钥
- **认证原因** - 显示认证原因、setNegativeButton
- **应用场景** - 用户登录/支付验证/敏感数据访问

```gradle
implementation 'androidx.biometric:biometric:1.1.0'
```

### 🔐 155. 设备认证

**是什么**: 设备级认证  
**能干什么**:
- **设备标识** - 设备唯一标识、DeviceId/IMEI/UUID
- **Device Policy** - 设备管理、密码策略、加密
- **Work Profile** - 工作资料隔离、工作/个人分离
- **设备管理** - MDM、远程擦除、应用管理
- **Knox** - Samsung Knox、企业级安全
- **SafetyNet** - Google SafetyNet、设备认证

### 🛡️ 156. 应用沙箱隔离

**是什么**: 应用沙箱机制  
**能干什么**:
- **进程隔离** - 每个应用独立进程、UID隔离
- **权限隔离** - 每个应用独立权限、权限声明
- **文件隔离** - 应用私有目录、其他应用无法访问
- **数据隔离** - SharedPreferences/Database私有
- **签名隔离** - 不同签名应用隔离、sharedUserId共享
- **进程通信** - 通过IPC、ContentProvider/AIDL

### 🔒 157. 应用权限检查

**是什么**: 权限检查机制  
**能干什么**:
- **checkPermission** - 检查权限、ContextCompat.checkSelfPermission
- **requestPermissions** - 请求权限、ActivityCompat.requestPermissions
- **shouldShowRequestPermissionRationale** - 是否需要解释、为什么需要
- **权限回调** - onRequestPermissionsResult、处理结果
- **批量请求** - 一次请求多个权限
- **特殊权限** - SYSTEM_ALERT_WINDOW、WRITE_SETTINGS

### 📋 158. 权限组

**是什么**: Android权限分组  
**能干什么**:
- **LOCATION组** - 位置权限组、CONTACTS组、存储组
- **权限组** - 同组权限任一授权、全组生效
- **运行时权限** - Android 6.0+、危险权限组
- **普通权限** - 非危险权限、自动授权
- **特殊权限** - 系统级权限、需特殊处理

**常见权限组**:
- LOCATION - ACCESS_FINE_LOCATION、ACCESS_COARSE_LOCATION
- CONTACTS - READ_CONTACTS、WRITE_CONTACTS
- PHONE - READ_PHONE_STATE、CALL_PHONE
- SMS - SEND_SMS、RECEIVE_SMS
- STORAGE - READ_EXTERNAL_STORAGE、WRITE_EXTERNAL_STORAGE
- CALENDAR - READ_CALENDAR、WRITE_CALENDAR

### 🔐 159. 网络安全配置

**是什么**: Android网络安全配置  
**能干什么**:
- **HTTPS强制** - 强制HTTPS、默认行为
- **证书固定** - pin-set、证书指纹
- **调试配置** - debug overrides、debug-only证书
- **域名配置** - domain-config、指定域名配置
- **信任锚点** - trust-anchors、自定义信任
- **明文通信** - cleartextTrafficPermitted、允许HTTP

### 🔐 160. 应用签名验证

**是什么**: 应用签名验证机制  
**能干什么**:
- **签名校验** - 验证应用签名、防止被篡改
- **签名比对** - 比对签名、防止假冒应用
- **完整性检查** - 检查APK完整性、CRC校验
- **自检机制** - 应用启动自检、被篡改拒绝运行
- **签名信息** - PackageManager.GET_SIGNING_CERTIFICATES

---

## 📊 八、性能优化（161-180）

### ⚡ 161. 启动优化

**是什么**: 应用启动速度优化  
**能干什么**:
- **冷启动** - 首次启动、进程创建→Activity显示、优化Application初始化
- **热启动** - 后台恢复、进程已存在
- **温启动** - 部分初始化、进程存在但Activity被销毁
- **优化方向** - Application初始化、Activity初始化、布局优化
- **工具** - TraceView/Systrace/Perfetto分析
- **最佳实践** - 延迟初始化、线程池、避免主线程操作、异步加载

### 🐢 162. 卡顿优化

**是什么**: UI卡顿问题优化  
**能干什么**:
- **主线程** - 避免主线程耗时操作、16ms/帧、60fps
- **布局优化** - 减少层级、ConstraintLayout、include/merge/ViewStub
- **过度绘制** - 减少过度绘制、去冗余背景、show GPU overdraw
- **刷新率** - 60Hz/90Hz/120Hz、流畅度
- **分析工具** - GPU Profiler、Systrace、Hierarchy Viewer、StrictMode
- **优化技巧** - 异步加载、延迟加载、预加载

### 💾 163. 内存优化

**是什么**: 内存占用优化  
**能干什么**:
- **内存泄漏** - 避免泄漏、LeakCanary检测
- **内存抖动** - 避免频繁创建销毁、对象池
- **内存溢出** - OOM优化、大图片压缩、Bitmap采样
- **内存分析** - Memory Profiler、Heap Dump、MAT分析
- **优化策略** - 及时释放、弱引用WeakReference、LRU缓存
- **监控** - LeakCanary、Memory Profiler、Dump Heap

### 🔋 164. 耗电优化

**是什么**: 应用耗电量优化  
**能干什么**:
- **唤醒锁** - WakeLock慎用、用完释放、partial_wake_lock
- **后台任务** - 减少后台、JobScheduler/WorkManager
- **定位** - 减少定位频率、fused location provider、批量定位
- **网络** - 批量请求、减少轮询、连接复用
- **分析工具** - Battery Historian、Profiler、dumpsys battery
- **优化策略** - Doze模式、App Standby、后台限制

### 📡 165. 网络优化

**是什么**: 网络请求优化  
**能干什么**:
- **连接复用** - HTTP/2、连接池、OkHttp
- **缓存策略** - 缓存减少请求、Cache-Control
- **请求合并** - 批量请求、减少请求次数
- **压缩** - Gzip压缩、减小传输量
- **DNS优化** - HTTPDNS、DNS缓存
- **预加载** - 预加载数据、提升体验
- **图片优化** - WebP格式、图片压缩、采样加载

### 🗄️ 166. 数据库优化

**是什么**: 数据库性能优化  
**能干什么**:
- **索引** - 添加索引、加速查询、CREATE INDEX
- **查询优化** - 避免全表扫描、select *慎用
- **批量操作** - 批量插入/删除、事务、beginTransaction
- **异步操作** - Room支持、suspend函数、协程异步
- **分页** - Paging库、按需加载、LoadState
- **分析工具** - Room数据库生成器、EXPLAIN QUERY PLAN

### 📦 167. APK优化

**是什么**: APK体积优化  
**能干什么**:
- **资源压缩** - shrinkResources、移除未使用资源
- **代码混淆** - ProGuard/R8、减小代码体积
- **资源优化** - WebP格式、矢量图、图片压缩、tinypng
- **So优化** - 只保留必要ABI、arm64-v8a、压缩So
- **动态下发** - 动态特性模块、按需下载、Dynamic Feature
- **分析工具** - APK Analyzer、R8、build-analyzer

### 🖼️ 168. 图片优化

**是什么**: 图片加载和显示优化  
**能干什么**:
- **图片压缩** - 质量压缩、格式转换、Bitmap.compress
- **格式选择** - WebP/PNG/JPEG、选择合适格式
- **尺寸优化** - 按需加载、采样加载、inSampleSize
- **内存缓存** - LruCache、内存缓存、Glide自动
- **磁盘缓存** - DiskLruCache、磁盘缓存、Glide自动
- **图片库** - Glide/Coil自动优化、避免OOM

### 🔄 169. 线程优化

**是什么**: 多线程使用优化  
**能干什么**:
- **线程复用** - 线程池、避免频繁创建、ExecutorService
- **协程** - 轻量级、大量并发、结构化并发
- **主线程** - 主线程不阻塞、保证UI流畅、StrictMode检测
- **线程数** - 合理配置线程数、CPU核心数、Runtime.getRuntime().availableProcessors()
- **避免竞态** - 同步锁、原子操作、Atomic类、synchronized

### 📊 170. 布局优化

**是什么**: 布局性能优化  
**能干什么**:
- **减少层级** - 扁平化、减少嵌套、Hierarchy Viewer查看
- **ConstraintLayout** - 减少层级、性能更好
- **include/merge** - 复用布局、合并根节点、<include/>/<merge/>
- **ViewStub** - 延迟加载、按需加载、<ViewStub/>
- **过度绘制** - 去除冗余背景、减少绘制、show GPU overdraw
- **分析工具** - Layout Inspector、Systrace、Hierarchy Viewer

### 🎨 171. 渲染优化

**是什么**: 渲染性能优化  
**能干什么**:
- **硬件加速** - hardwareAccelerated、GPU渲染、Android 3.0+
- **过渡绘制** - clipPath、避免过度绘制
- **离屏缓冲** - setLayerType、复杂动画、LAYER_TYPE_HARDWARE
- **invalidate** - 局部刷新、避免全屏刷新、invalidate(Rect)
- **GPU分析** - GPU Profiler、渲染管道分析、Profile GPU Rendering

### 🔍 172. 性能分析工具

**是什么**: Android性能分析工具  
**能干什么**:
- **Android Profiler** - CPU/内存/网络/能耗分析、实时监控
- **Memory Profiler** - 内存分析、堆转储、内存泄漏检测
- **CPU Profiler** - CPU分析、方法耗时、Trace
- **Network Profiler** - 网络分析、请求/响应/流量
- **Energy Profiler** - 能耗分析、唤醒锁/CPU/网络
- **Systrace** - 系统性能分析（已停更，被Perfetto取代）
- **Perfetto** - 系统跟踪工具、UI性能/CPU调度/内存
- **Simpleperf** - CPU性能分析、Native代码

### 🧪 173. 内存分析

**是什么**: 内存分析方法  
**能干什么**:
- **Memory Profiler** - 实时内存监控、堆转储
- **Heap Dump** - 堆转储、分析对象
- **MAT** - Memory Analyzer Tool、分析Hprof文件
- **LeakCanary** - 内存泄漏检测、自动检测
- **内存分配** - 追踪内存分配、Allocation Tracker
- **内存计数** - 对象数量统计、Object Count

### 🐛 174. ANR分析

**是什么**: Application Not Responding分析  
**能干什么**:
- **ANR原因** - 主线程阻塞、5秒超时
- **anr日志** - /data/anr/traces.txt、分析ANR
- **StrictMode** - 检测主线程操作、磁盘/网络操作
- **调试** - adb shell kill -3 <PID>、模拟ANR
- **分析工具** - Perfetto、分析traces.txt
- **优化方向** - 避免主线程耗时、子线程处理

### ⚡ 175. 耗时分析

**是什么**: 方法耗时分析  
**能干什么**:
- **TraceView** - 方法耗时分析、已废弃
- **Systrace** - 系统级耗时、已停更
- **CPU Profiler** - Trace Method Recording、方法耗时
- **Simpleperf** - CPU性能、Native代码
- **插桩** - Debug.startMethodTracing
- **耗时统计** - System.currentTimeMillis、时间差

### 📉 176. 流畅度分析

**是什么**: UI流畅度分析  
**能干什么**:
- **FPS** - 帧率统计、60fps流畅
- **丢帧** - 检测丢帧、GPU Profiler
- **Choreographer** - 帧率检测、onFrame
- **Profile GPU Rendering** - GPU渲染分析、4阶段
- **Systrace** - UI线程分析
- **Dumpsys gfxinfo** - dumpsys gfxinfo、帧信息

### 🔧 177. 构建优化

**是什么**: Gradle构建速度优化  
**能干什么**:
- **增量构建** - 增量编译、--no-daemon
- **构建缓存** - 构建缓存、org.gradle.caching=true
- **配置内存** - gradle.properties、org.gradle.jvmargs
- **并行构建** --parallel、并行编译模块
- **依赖版本** - 固定依赖版本、避免动态版本
- **Kapt** - 关闭Kapt、使用KSP

### 🧪 178. Benchmark 基准测试

**是什么**: 性能基准测试  
**能干什么**:
- **Jetpack Benchmark** - 宏基准/微基准
- **Macrobenchmark** - UI性能、启动速度
- **Microbenchmark** - 方法级别、循环预热
- ** warming up** - 预热、避免冷启动影响
- **编译优化** - 测试不同编译配置性能
- **报告** - 生成报告、对比结果

### 📱 179. 电量优化

**是什么**: 应用电量消耗优化  
**能干什么**:
- **WakeLock** - 使用后释放、避免持有
- **JobScheduler** - 批量任务、系统调度
- **Doze** - 适配Doze模式、避免频繁唤醒
- **后台限制** - 适配后台限制、Android 8.0+
- **Battery Historian** - 分析电量消耗
- **Battery Profiler** - 实时电量监控

### 📊 180. 网络优化

**是什么**: 网络请求优化  
**能干什么**:
- **连接复用** - HTTP/2、OkHttp连接池
- **缓存** - HTTP缓存、减少请求
- **批量请求** - 合并请求、减少请求次数
- **压缩** - Gzip、减小数据量
- **DNS优化** - HTTPDNS、DNS缓存
- **预加载** - 提前加载、提升体验

---

## 🛠️ 九、工具与库（181-200）

### 🖼️ 181. Glide 图片加载

**是什么**: Google推荐的图片加载库  
**能干什么**:
- **图片加载** - 网络/本地/资源图片、自动加载
- **内存缓存** - 三级内存缓存、优化内存
- **磁盘缓存** - 磁盘缓存、减少网络请求
- **GIF支持** - 支持GIF动画
- **图片变换** - 圆角/模糊/灰度等变换
- **生命周期** - 生命周期感知、页面停止停止加载
- **视频帧** - 支持视频帧截图

```gradle
implementation 'com.github.bumptech.glide:glide:4.16.0'
kapt 'com.github.bumptech.glide:compiler:4.16.0'
```

### 🎨 182. Coil 图片加载

**是什么**: Kotlin图片加载库  
**能干什么**:
- **Kotlin优先** - Kotlin编写、协程支持
- **轻量级** - 比Glide更轻量、APK体积小
- **协程图片** - ImageRequest协程支持
- **SVG支持** - 支持SVG图片
- **内存优化** - 更好的内存管理、更少OOM
- **API简单** - API简洁、易于使用

```gradle
implementation 'io.coil-kt:coil:2.5.0'
```

### 🌐 183. Gson JSON解析

**是什么**: Google JSON解析库  
**能干什么**:
- **JSON转对象** - JSON→Java/Kotlin对象、fromJson
- **对象转JSON** - 对象→JSON字符串、toJson
- **泛型支持** - 支持泛型类型、TypeToken
- **注解** - @SerializedName等注解、重命名字段
- **流式解析** - JsonReader/JsonWriter流式解析
- **容错** - 容错性好、宽松解析

```gradle
implementation 'com.google.code.gson:gson:2.10.1'
```

### 📄 184. Moshi JSON解析

**是什么**: Square JSON解析库  
**能干什么**:
- **Kotlin友好** - 更好的Kotlin支持、Null安全
- **代码生成** - 编译时生成代码、性能更好
- **注解** - @Json等注解、自定义适配器
- **流式API** - 类似Gson、易于使用
- **容错** - Fail-fast默认、可配置

```gradle
implementation 'com.squareup.moshi:moshi:1.15.0'
kapt 'com.squareup.moshi:moshi-kotlin-codegen:1.15.0'
```

### 💉 185. Hilt 依赖注入

**是什么**: Android官方依赖注入框架  
**能干什么**:
- **编译时DI** - 编译时生成代码、性能优秀
- **Android集成** - 与Android组件深度集成、@HiltAndroidApp
- **ViewModel支持** - 自动注入ViewModel、@ViewModelInject
- **模块化** - @Module模块化组织、@InstallIn
- **作用域** - @Singleton等作用域、组件作用域
- **简单易用** - @Inject注入、构造函数注入

```gradle
implementation 'com.google.dagger:hilt-android:2.48'
kapt 'com.google.dagger:hilt-compiler:2.48'
```

### 🧪 186. Koin 依赖注入

**是什么**: 轻量级Kotlin依赖注入框架  
**能干什么**:
- **无代码生成** - 无需注解处理、编译快、无kapt
- **DSL定义** - DSL定义模块、简单直观
- **ViewModel支持** - 支持ViewModel注入、viewModel()
- **作用域** - 支持作用域管理、scope
- **简单易用** - 学习成本低、API简洁
- **模块化** - module模块、组织依赖

```gradle
implementation 'io.insert-koin:koin-android:3.5.3'
```

### 🎨 187. Material Components

**是什么**: Material Design组件库  
**能干什么**:
- **官方组件** - Material Design组件、Google官方
- **MaterialButton** - Material按钮
- **MaterialCardView** - Material卡片、圆角/阴影
- **TextInputLayout** - 输入框容器、浮动标签
- **BottomNavigationView** - 底部导航
- **CoordinatorLayout** - 协调布局
- **Material主题** - Theme.Material3

```gradle
implementation 'com.google.android.material:material:1.11.0'
```

### 🗄️ 188. Room 数据库

**是什么**: Android官方SQLite ORM  
**能干什么**:
- **类型安全** - 类型安全的数据库访问
- **编译时验证** - SQL编译时检查
- **LiveData支持** - 与LiveData集成
- **Flow支持** - 与Kotlin Flow集成
- **迁移** - 数据库版本迁移
- **多表查询** - 关联查询

### 🔗 189. Retrofit 网络库

**是什么**: Square网络请求库  
**能干什么**:
- **REST API** - 定义REST接口、自动实现
- **类型安全** - 类型安全的API
- **转换器** - 支持多种转换器
- **协程支持** - 支持suspend函数
- **拦截器** - 添加token/日志等

### ⚙️ 190. OkHttp 客户端

**是什么**: 高效HTTP客户端  
**能干什么**:
- **连接池** - HTTP连接复用
- **缓存** - HTTP缓存
- **拦截器** - 请求/响应拦截
- **WebSocket** - WebSocket支持
- **同步/异步** - 支持同步/异步请求

### 🎯 191. EventBus 事件总线

**是什么**: 事件总线框架  
**能干什么**:
- **组件通信** - 组件间事件通信
- **解耦合** - 组件间解耦
- **线程模式** - 指定接收线程
- **优先级** - 事件优先级
- **粘性事件** - 粘性事件、新订阅者收到最新事件

```gradle
implementation 'org.greenrobot:eventbus:3.3.1'
```

### 🗺️ 192. 高德地图SDK

**是什么**: 高德地图服务  
**能干什么**:
- **地图显示** - 显示地图、缩放/旋转
- **定位** - 定位SDK、连续定位
- **导航** - 路线规划、导航SDK
- **搜索** - POI搜索、关键词搜索
- **周边** - 周边检索
- **离线地图** - 离线下载

### 🗺️ 193. 百度地图SDK

**是什么**: 百度地图服务  
**能干什么**:
- **地图显示** - 显示地图、缩放/旋转
- **定位** - 定位SDK
- **导航** - 路线规划、导航SDK
- **搜索** - POI搜索
- **周边** - 周边检索
- **鹰眼** - 轨迹服务

### 📊 194. 友盟统计

**是什么**: 移动应用统计  
**能干什么**:
- **用户统计** - 用户数/活跃用户/新增用户
- **页面统计** - 页面访问、页面停留时间
- **事件统计** - 自定义事件、事件属性
- **渠道统计** - 渠道来源分析
- **崩溃统计** - 崩溃报告
- **错误分析** - 错误统计

### 📊 195. 神策分析

**是什么**: 用户行为分析  
**能干什么**:
- **用户行为** - 用户行为分析、事件追踪
- **漏斗分析** - 转化漏斗、留存分析
- **用户分群** - 用户分群、用户画像
- **埋点** - 代码埋点/全埋点
- **行为路径** - 用户行为路径分析

### 📱 196. 腾讯Bugly

**是什么**: 腾讯崩溃上报平台  
**能干什么**:
- **崩溃上报** - 自动上报崩溃
- **错误统计** - 错误统计、错误趋势
- **崩溃分析** - 崩溃日志、机型/系统版本
- **热修复** - 热修复、Bugly Hotfix
- **升级** - 应用升级

### 🔔 197. 极光推送

**是什么**: JPush推送服务  
**能干什么**:
- **推送通知** - 通知推送、自定义通知
- **自定义消息** - 自定义消息、应用内处理
- **富媒体** - 富媒体推送、大图/视频
- **标签/别名** - 标签推送、别名推送
- **统计** - 推送统计、到达率/点击率
- **多厂商** - 集成厂商推送、小米/华为/OPPO/vivo

### 🎨 198. Gson vs Jackson vs Moshi

**是什么**: JSON库对比  
**能干什么**:
- **Gson** - Google出品、简单易用、容错性好
- **Jackson** - 功能强大、高性能、服务端常用
- **Moshi** - Square出品、Kotlin友好、类型安全
- **选择建议** - Android用Gson/Moshi、服务端用Jackson
- **性能** - Moshi > Jackson > Gson
- **Kotlin支持** - Moshi > Gson > Jackson

### 💳 199. 支付集成

**是什么**: 移动支付  
**能干什么**:
- **支付宝** - 支付宝SDK、支付/授权
- **微信支付** - 微信支付SDK、统一下单
- **银联** - 银联SDK、支付控制
- **Apple Pay** - iOS支付、设备绑定
- **Google Pay** - Google支付、Google Play Billing
- **Stripe** - 国际支付、信用卡支付

### 📲 200. 社交登录

**是什么**: 第三方登录  
**能干什么**:
- **Google登录** - Google Sign-In、一键登录
- **Facebook登录** - Facebook SDK、Graph API
- **微信登录** - 微信开放平台、获取用户信息
- **QQ登录** - QQ互联、腾讯SDK
- **新浪登录** - 微博登录、新浪SDK
- **Apple登录** - Sign in with Apple、iOS必需

---

## 📚 学习资源

### 📖 官方资源
- **Android Developers** - https://developer.android.com 官方文档
- **Android Studio** - 下载最新版Android Studio、最新版
- **Jetpack** - https://developer.android.com/jetpack Jetpack库
- **Material Design** - https://m3.material.io Material设计
- **AOSP** - https://source.android.com Android开源项目

### 🎯 学习建议
1. **先掌握ADB调试** - 能够安装/调试/查看日志/查看设备信息
2. **了解项目结构** - AndroidManifest/Gradle/res目录/源码组织
3. **了解平台能力** - Android能做什么、有什么组件、有什么限制
4. **了解安全权限** - 有什么权限、怎么申请、适配方案
5. **了解性能优化** - 有哪些工具、怎么分析、怎么优化
6. **关注新特性** - Android新版本特性、新能力
7. **了解跨平台** - RN/Flutter/KMP怎么选、各自优缺点

### 🔍 调试技巧
- **ADB调试** - 设备管理/应用管理/日志查看/性能监控
- **Logcat过滤** - 包名过滤/TAG过滤/级别过滤
- **Profiler分析** - CPU/内存/网络/能耗分析
- **布局检查** - Layout Inspector查看布局、View属性
- **网络抓包** - Charles/Fiddler/Wireshark抓包
- **数据库查看** - Stetho/Debug Database查看

### 🌐 中文资源
- **Android中文组** - https://developer.android.google.cn
- **掘金Android** - https://juejin.cn/tag/Android
- **CSDN Android** - https://www.csdn.net/nav/android
- **知乎Android** - https://www.zhihu.com/topic/19559327

### 💡 最佳实践
- **架构选择** - MVVM+Jetpack官方推荐、Clean Architecture
- **性能优先** - 避免主线程操作、减少布局层级、内存优化
- **安全第一** - HTTPS、加密存储、权限最小化、代码混淆
- **测试驱动** - 单元测试、UI测试、测试覆盖
- **文档优先** - 代码注释、API文档、README
- **版本管理** - Git分支、语义化版本、CHANGELOG

---

**总结**: 这个Android骨架知识体系完全面向全栈开发者，删除了协程/Flow等技术实现细节，聚焦**平台能力、工具链、生态知识**。让全栈开发者快速了解Android有什么能力、能做什么、怎么查怎么用，无需深入实现细节。
