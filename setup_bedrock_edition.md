# 搭建 Minecraft 基岩版服务器

## 环境要求

`Linux` 建议使用较新版本的 Linux 发行版，否则容易出现环境不兼容导致无法启动，建议使用 `Ubuntu 22.04` 及以上版本。

`Windows` 端建议使用 `Windows server 2016`，`Windows 10` 及以上版本。

## Windows 版本

### 获取服务端

最新的官方基岩版服务端可在 [Minecraft 基岩版官网](https://www.minecraft.net/zh-hans/download/server/bedrock) 获取。

若想要获取较老版本的服务端，请到第三方论坛寻找对应版本的服务端。

### 通过面板启动

- 进入面板，进入 `应用实例` 菜单。
- 点击`新建示例`并选择 Minecraft 基岩版版游戏服务器。
- 选择需部署的节点。
- 填写信息，启动命令填写 `bedrock_server.exe`。
- `bedrock_server.exe` 为服务端文件名称。
- 上传你下载的 官方基岩版 Windows 版本服务端压缩包。
- 等待上传并解压完毕，进入控制台。
- 点击控制台右上操作键开启实例即可。

### 出现提示框提示 `未找到 xxx.dll` 或 `启动失败` ？

请从安全的渠道下载 Microsoft VC++ 运行库文件进行安装，补全运行环境。

## Linux 版

### 下载服务端软件

最新的官方基岩版服务端可在 [Minecraft 基岩版官网](https://www.minecraft.net/zh-hans/download/server/bedrock) 获取。

若想要获取较老版本的服务端，请到第三方论坛寻找对应版本的服务端。

### 通过面板启动

- 进入面板，进入 `应用实例` 菜单。
- 选择 Minecraft 基岩版版游戏服务器。
- 选择需部署的节点，选择上传服务端文件压缩包。
- 填写信息，启动命令填写 `./bedrock_server`，`bedrock_server` 为服务端文件名称，具体请视情况而定。
- 上传你下载的官方基岩版 Ubuntu 版本服务端压缩包。
- 等待上传并解压完毕，进入控制台。
- 点击控制台右上操作键开启实例即可。

### 无法成功启动？

```
[错误] 实例启动失败，请检查启动命令，主机环境和配置文件等
```

​ 出现这类问题的原因有很多种，目前已知**三种**情况：

1. 启动命令编写错误。
2. 服务端程序没有运行权限。
3. Ubuntu 系统环境缺少必要的依赖。

​ **第一种**

错误解决方案：填写正确的启动命令

```bash
./bedrock_server
# bedrock_server 为服务端名称，或者你可以选择创建一个 sh 脚本文件，写入启动命令 sh <你的脚本名字>.sh
```

​ **第二种**和**第三种**错误具体表现为：

```
[MCSMANAGER] [ERROR] 检测到实例进程/容器启动失败（PID 为空），其可能的原因是：
1. 实例启动命令编写错误，请前往实例设置界面检查启动命令与参数。
2. 系统主机环境不正确或缺少环境，如 Java 环境等。

原生启动命令：
./bedrock_server

请将此信息报告给管理员，技术人员或自行排查故障。


[错误] 实例启动失败，请检查启动命令，主机环境和配置文件等
```

如果你是**面板服务器管理者**，请检查**服务端**文件是否给予了 755 权限，如未给予则请前往面板文件管理中给予，如果给予了权限，启动依旧报错，请检查服务端文件是否完整正确下载。

如果提示依赖报错，请尝试重装 Ubuntu 系统或升级 Ubuntu 系统版本，重装后还是报同错误，请将错误输出复制到百度，自行搜索解决方案。

### 启动正常，但无法进入游戏服务器？

这种情况多半是**安全组没放行**，请在**服务商安全组面板放行你的服务端端口**，并在**系统防火墙**一并放行。​ 如果还是无法连接，请联系你的服务商检查网络情况。

### 目录

[主页](https://capslock800000.github.io/mcsmanagerdocs)  [java版](https://capslock800000.github.io/mcsmanagerdocs/setup_java_edition)  [基岩版](https://capslock800000.github.io/mcsmanagerdocs/setup_bedrock_edition)  [Docker安装](https://capslock800000.github.io/mcsmanagerdocs/docker-install)  [其他使用场景](https://capslock800000.github.io/mcsmanagerdocs/setup_any_software)  [使用Docker部署服务器](https://capslock800000.github.io/mcsmanagerdocs/setup_docker_image)  [一键部署java版](https://capslock800000.github.io/mcsmanagerdocs/setup_package)  [部署steam游戏服务器](https://capslock800000.github.io/mcsmanagerdocs/setup_steam)
