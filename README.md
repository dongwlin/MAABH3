<div align="center">

# MAABH3

基于MAA全新架构的 蹦蹦蹦 小助手

图像技术 + 模拟控制，解放双手！

由 [MaaFramework](https://github.com/MaaAssistantArknights/MaaFramework) 强力驱动！

</div>

## How to use

> 1. [下载](https://github.com/MaaAssistantArknights/MAABH3/releases) 对应平台的压缩包
> 2. 将压缩包解压到没有中文的目录下

### 基本说明

1. 请根据 [模拟器支持情况](https://maa.plus/docs/1.3-模拟器支持.html)，进行对应的操作。
2. 修改模拟器分辨率为 `16:9` 比例，最低 `1280 * 720`，更高不限。

### 直接使用 

> 以 Windows 用户为主，其他系统请照葫芦画瓢。

1. 首次使用，双击打开 `MAABH3_CLI.exe` 或 通过 CMD 执行 `MAABH3_CLI.exe`
2. 等待扫描设备（设备越多等待时间越长）
3. 选择客户端
4. 输入需要执行的任务序号
    - 以空格分隔，例如 `1 2 3 4 5` 和 `2 3 1 4 5`，序号的顺序代表着执行顺序
    - 序号可重复，例如 `5 1 2 3 4 5`

5. 选择需要连接的设备
6. 开始使用吧！

   - 后续使用无需再次选择客户端和输入需要执行的任务
   - 后续使用除非需要连接的设备不存在，否则无需再次选择设备

### 作为MAA结束后脚本使用

> 以 Windows 用户为主，其他系统请照葫芦画瓢。

1. 先按照 [直接使用](#直接使用) 进行操作
2. 在MAA目录下新建一个文本文件，在其中填入以下内容

    ```bat
    @echo off
    cd D:/Software/MAABH3
    MAABH3_CLI.exe
    ```

   - 注意：`D:/Software/MAABH3` 请替换成你自己的 MAABH3 目录

3. 将文本文件重命名为 `finish.bat`

    - 如果重命名后没有弹出修改扩展名的二次确认对话框，且文件图标没有变化，请自行搜索“Windows如何显示文件扩展名”。

4. 在MAA `设置`-`游戏设置`-`结束后脚本` 中填入 `finish.bat`
5. 开始使用吧！

## Task instructions

| 任务 | 说明 |
| ---- | ---- |
| Dorm | 家园；自动收家园金币、体力、打工和远征 |
| MaterialEvent | 材料远征；自动一键减负 |
| Armada | 舰团；自动提交委托回收和领取舰团贡献奖励 |
| Shop | 商店；用金币购买后勤终端的角色碎片和用1星石购买虚境商店的时序通行证 |
| Awards | 奖励；领取每日奖励 |
| UniversalMirage | 万象虚境；自动打第二层 |

   - 目前启动游戏仅支持官服、Bilibili服和Vivo服
   - 其他渠道服虽不支持启动，但可手动启动游戏后正常使用
   - 若需要适配启动其他渠道服，欢迎提 `issues` 或 `pr`
   - 家园远征可能会清空当前体力和家园体力罐内体力,总量受远征派遣体力限制
   - 如果任务列表中同时包含 MaterialEvent 和 Dorm，先完成 MaterialEvent是一个更好的选择。这样做有助于确保有足够的体力来完成所有任务
   - 使用材料减负需要先三星通关一次对应关卡，有多个关卡的模块（如曜日材料）则会自动进行已完成挑战的最高一级关卡
   - 万象虚境需要先选好上场女武神

## How to build

**如果你要编译源码才看这节，否则直接 [下载](https://github.com/MaaAssistantArknights/MAABH3/releases) 即可**

_欢迎大佬们来带带~_

1. 下载 MaaFramework 的 [Release 包](https://github.com/MaaAssistantArknights/MaaFramework/releases)，解压到 `deps` 文件夹中
2. 配置 cmake

    - Windows  

    ```bash
    cmake --preset "MSVC 2022"
    ```

    - Linux / macOS

    ```bash
    cmake --preset "NinjaMulti"
    ```

3. 使用 cmake 构建工程  

    ```bash
    cmake --build build --config Release
    cmake --install build --prefix install
    ```

    生成的二进制及相关资源文件在 `install` 目录下

## 开发相关

- `tools/CropRoi` 可以用来裁剪图片和获取 ROI
- Pipeline 协议请参考 [MaaFramework 的文档](https://github.com/MaaAssistantArknights/MaaFramework/blob/main/docs/zh_cn/3.1-%E4%BB%BB%E5%8A%A1%E6%B5%81%E6%B0%B4%E7%BA%BF%E5%8D%8F%E8%AE%AE.md)

## Join us

QQ 群：566868495

## 其他

* 芝士[MAA1999](https://github.com/MaaAssistantArknights/MAA1999)，基于MAA全新架构的 亿韭韭韭 小助手。

## Todo

* [x] 启动
  * [x] 签到

* [x] 家园
  * [x] 家园金币和体力
  * [x] 家园打工
  * [x] 家园远征

* [x] 材料远征一键减负

* [x] 舰团
  * [x] 委托回收
  * [x] 舰团贡献

* [ ] 商店
  * [x] 后勤终端金币碎片
  * [x] 虚境商店1星石时序通行证
  * [ ] 吼姆秘宝

* [ ] 万象虚境
  * [x] 第二层
  * [ ] 第五层

* [ ] 奖励
  * [x] 每日奖励
  * [ ] 邮件

* [ ] 杂项
  * [ ] 每周分享

* [ ] 肉鸽（乐土）