# 重症大数据行者（Big Data Master of Critical Care，BDMCC）
## 1 关于BDMCC
<p align="center">
  <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/mac_logo.png" width="10%" height="10%" />
</p>

- 重症大数据行者（Big Data Master of Critical Care，BDMCC）为NYL博士开发，计划将逐步支持目前业内所有的公开重症数据库（MIMIC-III、MIMIC-III-Carevue、MIMIC-IV、eICU、HiRID、SICdb、AmsterdamUMCdb、PIC）、麻醉数据库（INSPIRE）等等关系型医学数据集的一键安装。部分数据库将含有独家的增强型BDMCC系列表单（类似于MIMIC数据库的Concepts功能），上述增强型表单已经移除官方Concepts存在的部分Bug并进行优化，配合R包`strong`包可极大提高数据处理效率。
- 软件将覆盖支持Windows、macOS、Linux三平台，实现无论在设备操作系统下，均可以最快、最方便的方式完成对目标数据库的一键安装及后续的一键升级管理。
- 本软件仅提供一键安装功能，不提供任何数据集的下载！安装所需的数据集请自行前往官网进行申请，请遵守数据使用协议，维护良好学术道德风尚。
- 本软件由重症医学、小明学习室、实战医学统计、R语言统计与绘图、重症超声教学资源(以上排名不分先后)联合发布。
- 所有软件均无病毒无后门！请于[本软件唯一官网](https://github.com/ningyile/BDMCC_APP)放心下载安装使用。

## 2 PostgreSQl是否正确安装、配置
- 使用本软件前请确保PostgreSQl已经正确安装并配置相应的环境变量。
### 2.1 PostgreSQl环境变量的查询
- Windows系统下查询：按"Windows徽标键键"+"R"，并在“打开”框中键入“cmd”，然后输入"where psql"。如果cmd终端中出现`C:\Program Files\PostgreSQL\16\bin\psql.exe`等类似结果即表明该PostgreSQl已经安装配置完毕。
<p align="center">
  <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/env_01.png" width="60%" height="60%" />
</p>

- macOS与Linux系统下查询：打开终端，然后输入"which psql"。如果cmd终端中出现`/usr/local/bin/psql`等类似结果即表明该PostgreSQl已经安装配置完毕。
<p align="center">
  <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/env_02.png" width="60%" height="60%" />
</p>

### 2.2 PostgreSQl在三大系统下的安装及配置。
- 若在上述查询中未能返回有效的结果，则证明PostgreSQl未安装或未正确配置。具体解决方案请单击此处观看相应系统下的安装及配置视频教程。
  
## 3 BDMCC下载安装说明
- 请根据操作系统及芯片选择下载安装相应的程序文件。
### 3.1 Windows系统下载安装说明
- Windows系统仅支持Win10 2004及其后续版本（包括Win11）的X64架构，目前仅在Win10 22H2版本进行了测试。Windows系统查看版本的方法：按"Windows徽标键键"+"R"，并在“打开”框中键入“winver”，然后选择"确定"。如符合上述条件请下载安装`BDMCC_1.0.1_x64-setup.exe`。请注意安装路径请使用英文字母。
### 3.2 macOS系统下载安装说明
- macOS Intel与M1/M2系列芯片的设备在安装后首次启动BDMCC软件时均会提示:`无法打开BDMCC.app，因为无法验证开发者`。请单击“取消”并使用如下方法解决：
    - 单击选择菜单：找到"系统偏好设置"。
    - 打开系统偏好设置界面，点击"安全性与隐私"-"通用"。
    <p align="center">
      <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/mac_01.png" width="60%" height="60%" />
    </p>
    
    - 窗口底部允许从以下位置下载的App会看到：已阻止使用“BDMCC”，因为来自身份不明的开发者。点击后面的"仍要打开"按钮。
    <p align="center">
      <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/mac_02.png" width="60%" height="60%" />
    </p>
    <p align="center">
      <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/mac_03.png" width="60%" height="60%" />
    </p>
    
    - 在弹出的确认弹窗中，点击"打开"按钮即可。
    <p align="center">
      <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/mac_04.png" width="60%" height="60%" />
    </p>

- macOS Intel系列芯片请下载安装`BDMCC_1.0.1_x64.dmg`。理论上支持Big Sur以后的版本，目前仅在10代Intel芯片的Big Sur 11.6.1版本上进行了测试。
- macOS M1/M2系列芯片请下载安装`BDMCC_1.0.1_aarch64.dmg`。理论上支持Big Sur以后的版本，目前仅在M2 Max的Sonoma 14.1.1版本上进行了测试，建议将系统更新至最新版使用。
### 3.3 Linux系统下载安装说明
- Linux系统理论上支持所有Debian系列系统，目前仅在Ubuntu LTS 22.04版本进行了测试，如果在Linux上使用，强烈建议使用Ubuntu系统，其他发行版Linux不保证可正常运行。Linux系统请下载`BDMCC_1.0.1_amd64.deb`后，于所在路径开启终端，然后在终端下键入以下命令(xxxxxx修改为相应的BDMCC的版本号)即可完成安装：
```bash
sudo dpkg -i BDMCC_xxxxxx_amd64.deb
```
## 4 各系统运行截图
- Windows下默认主题、中文语言
<p align="center">
  <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/win_run_01.png" width="80%" height="80%" />
</p>

- macOS下默认主题、英文语言
<p align="center">
  <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/mac_run_01.png" width="80%" height="80%" />
</p>

- Linux系统暗黑主题、英文语言
<p align="center">
  <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/linux_run_01.png" width="80%" height="80%" />
</p>

## 5 更新日志
- **V1.0.1** 支持MIMIC-III-Demo V1.4、MIMIC-III V1.4、MIMIC-III-CareVue V1.4、MIMIC-IV V2.0、eICU V2.0数据库安装。其中MIMIC-III V1.4、MIMIC-III-CareVue V1.4、MIMIC-IV V2.0含增强型系列表单BDMCC，可有效减少后期R语言代码。
