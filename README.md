# 重症大数据行者（Big Data Master of Critical Care，BDMCC）
<p align="center">
  <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/mac_logo.png" width="20%" height="20%" />
</p>

## 1 为什么选择BDMCC

- 重症大数据行者（Big Data Master of Critical Care，BDMCC）为NYL博士开发，计划将逐步支持目前业内所有的开源重症数据集（MIMIC-III、MIMIC-III-CareVue、MIMIC-IV、eICU、HiRID、SICdb、AmsterdamUMCdb、PIC等）的一键安装。部分数据集含有独家BDMCC系列增强表单（类似于MIMIC数据集的Concepts功能），上述表单已经移除官方Concepts存在的部分Bug并进行优化，配合[**strong包**](https://github.com/ningyile/strongInstall_pkg)可极大提高数据处理效率。
- BDMCC开发者为ICU医生，同时具有ICU医疗背景以及ICU数据库的开发经验。发布运营团队（**重症行者翻译组、easyDSM团队**）多名成员具有重症医学、R语言编程、统计学专业相关背景。熟悉重症数据集研究中的数据提取、数据清洗、数据建模等流程。

## 2 关于BDMCC

- 软件覆盖支持Windows、macOS、Linux三种操作系统，实现在任何平台下，以最快、最方便的方式完成对目标数据集的一键安装及后续的一键升级管理。
- **本软件仅提供一键安装功能，不提供任何数据集的下载！安装所需的数据集请自行前往官网进行申请，请遵守数据使用协议，维护良好学术道德风尚。**
- 本软件在**重症医学**、**小明学习室**、**实战医学统计**、**R语言统计与绘图**、**重症超声教学资源**(以上排名不分先后)公众号同步发布。
- 所有软件均无病毒无后门！请于[本软件唯一官网](https://github.com/ningyile/BDMCC_APP/releases)放心下载安装使用。

## 3 PostgreSQL是否正确安装、配置
- 使用本软件前请确保PostgreSQL已经正确安装并配置相应的环境变量。
### 3.1 PostgreSQL环境变量的查询
- Windows系统下查询：按【Windows徽标键】+【R】，并在【打开】框中键入“cmd”，然后输入"where psql"。如果cmd终端中出现`C:\Program Files\PostgreSQL\16\bin\psql.exe`等类似结果即表明该PostgreSQL已经安装配置完毕。
<p align="center">
  <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/env_01.png" width="60%" height="60%" />
</p>

- macOS与Linux系统下查询：打开终端，然后输入"which psql"。如果终端中出现`/usr/local/bin/psql`等类似结果即表明该PostgreSQL已经安装配置完毕。
<p align="center">
  <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/env_02.png" width="60%" height="60%" />
</p>

### 3.2 PostgreSQL在三大系统下的安装及配置。
- 若在上述查询中未能返回有效的结果，则证明PostgreSQL未安装或未正确配置。具体解决方案请看第一部分的视频教程。
  
## 4 BDMCC下载安装说明
- 请根据操作系统及芯片选择下载安装相应的程序文件。
### 4.1 Windows系统下载安装说明
- Windows系统仅支持Win10 2004及其后续版本（包括Win11）的X64架构，目前仅在Win10 22H2版本进行了测试。Windows系统查看版本的方法：按"Windows徽标键键"+"R"，并在“打开”框中键入“winver”，然后选择"确定"。如符合上述条件请下载安装`BDMCC_1.0.1_x64-setup.exe`。**请注意安装路径使用英文字母**。
### 4.2 macOS系统下载安装说明
- macOS Intel与M1/M2系列芯片的设备在安装后首次启动BDMCC软件时均会提示:`无法打开BDMCC.app，因为无法验证开发者`。请单击【取消】并使用如下方法解决：

    - 打开【终端】，在终端中输入下列代码，以开启“任何来源”。
    ```bash
    sudo spctl  --master-disable
    ```
	
    - 单击选择菜单：接着打开【系统偏好设置】，选择【安全性与隐私】，选择【通用】，可以看到【任何来源】已经选定。
    
    <p align="center">
      <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/mac_01.png" width="60%" height="60%" />
    </p>
    
    - 窗口底部允许从以下位置下载的App会看到：已阻止使用“BDMCC”，因为来自身份不明的开发者。点击后面的【仍要打开】按钮。
    
    <p align="center">
      <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/mac_02.png" width="60%" height="60%" />
    </p>
    <p align="center">
      <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/mac_03.png" width="60%" height="60%" />
    </p>
    
    - 在弹出的确认弹窗中，点击【打开】按钮即可。
    <p align="center">
      <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/mac_04.png" width="60%" height="60%" />
    </p>

    - 如果发现还是显示“已损坏，无法打开。您应该将它移到废纸篓”。请单击【取消】。接下来在终端粘贴复制输入命令：
    ```bash
    sudo xattr -r -d com.apple.quarantine /Applications/BDMCC.app
    ```
    <p align="center">
      <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/mac_06.png" width="60%" height="60%" />
    </p>
    
- macOS Intel系列芯片请下载安装`BDMCC_1.0.1_x64.dmg`。理论上支持Big Sur以后的版本，目前仅在10代Intel芯片的Big Sur 11.6.1版本上进行了测试。

- macOS M1/M2系列芯片请下载安装`BDMCC_1.0.1_aarch64.dmg`。理论上支持Big Sur以后的版本，目前仅在M2 Max的Sonoma 14.1.1版本上进行了测试，建议将系统更新至最新版使用。
### 4.3 Linux系统下载安装说明
- Linux系统理论上支持所有Debian系发行版系统，目前仅在Ubuntu LTS 22.04版本进行了测试，如果在Linux上使用，强烈建议使用Ubuntu系统，其他发行版Linux不保证可正常运行。由于各发行版的Debian系统安装后可能缺失必要的依赖库。故需要下载本项目中的二进制程序**bdmcc_dep**，以完成依赖库的自动化校验，如查到缺失依赖库，则该程序会进行自动化安装。假如将二进制程序**bdmcc_dep**下载至桌面，则需在桌面打开终端，并输入以下命令即可完成依赖库的自动化校验及安装（若下列命令无法运行则需要使用`sudo chmod +x ./bdmcc_dep`命令赋予执行权限）：
```bash
./bdmcc_dep
```
<p align="center">
  <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/bdmcc_dep_01.png" width="60%" height="60%" />
</p>
<p align="center">
  <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/bdmcc_dep_02.png" width="60%" height="60%" />
</p>

- 完成依赖库校验后，请下载`BDMCC_1.0.1_amd64.deb`安装包，于所在路径开启终端，然后在终端下键入以下命令(xxxxxx修改为相应的BDMCC的版本号)即可完成安装：
```bash
sudo dpkg -i BDMCC_xxxxxx_amd64.deb
```

## 5 BDMCC使用说明

### 5.1 配置软件账户密码

- 打开软件后填写 PostgreSQL的账户和密码，如填写正确会有相应的提示。

### 5.2 选择数据集文件路径
- 选择数据集文件所在的路径（注意是**上一级路径**，本例中数据集文件路径为桌面的database文件夹，使用上一级目录在安装不同数据集时可以避免频繁切换数据文件夹）。数据集安装文件对应的文件夹对应关系如下表：

  | 数据集            | 版本号 | 对应的子一级（相对于上一级路径database）文件夹 |
  | ----------------- | ------ | ---------------------------------------------- |
  | MIMIC-III-Demo    | V1.4   | mimic-iii-clinical-database-demo-1.4           |
  | MIMIC-III         | V1.4   | mimic-iii-clinical-database-1.4                |
  | MIMIC-III-CareVue | V1.4   | mimic-iii-clinical-database-carevue-subset-1.4 |
  | MIMIC-IV          | V2.0   | mimic-iv-2.0                                   |
  | MIMIC-IV          | V2.2   | mimic-iv-2.2                                   |
  | eICU              | V2.0   | eicu-collaborative-research-database-2.0       |

<p align="center">
  <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/dir_tree_01.png" width="100%" height="100%" />
</p>


### 5.3 数据文件的目录结构
- 各个文件夹的目录树结构严格按照Physionet官网中原始数据文件的目录结构。如下图，以**MIMIC-IV V2.0为例 **，[官网](https://www.physionet.org/content/mimiciv/2.0/#files-panel)和下载的本地数据文件树目录结构需要完全保持一致。此外，在安装前BDMCC软件还会对原始的数据文件进行校验，以确定数据的准确性和唯一性。如文件校验未通过，则安装无法继续进行。
<p align="center">
  <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/dir_tree_02.png" width="80%" height="80%" />
</p>

### 5.4 数据集安装的模块选择
- 各个文上述数据集大多包含三个模块：Base、Concepts和BDMCC（本软件构建的系列增强型表单）模块。其中Base是将数据文件拷贝至相应的数据集；Concepts模块则是官方在Base模块基础上进行进一步计算获取的表单如SOFA、APS评分等表单；BDMCC系列增强型表单则包含文章数据分析时的研究队列人群所需的常用数据，优化了官方Concepts中的部分bug，配合使用可大大减少代码量同时提高数据提取的效率。故上述模块安装顺序依次是Base、Concepts和BDMCC。当所依赖的模块不存在时，后续的模块无法进行安装，故选择模块时应根据设备上数据集模块的安装情况进行选择。

### 5.5 数据集占用磁盘空间情况
- 重症数据集会占用大量的磁盘空间。BDMCC软件在安装对应的数据集之前会校验PostgreSQL的数据路径的剩余空间，当磁盘剩余空间小于目标数据集所需的空间时，安装则难以为继。在不同系统中所占空间大小不一（相差不会很大），故BDMCC软件中设定的空间大小在原来基础上留3GB左右作为冗余空间。BDMCC软件中各数据集以及各模块设定的磁盘空间情况如下表：

  | 数据集             | 版本号  | Base模块 | Concepts模块 | BDMCC模块 |
  | ----------------- | ------ | -------- | ------------ | ------------ |
  | MIMIC-III-Demo    | V1.4   | 200 MB   | 25 MB        |              |
  | MIMIC-III         | V1.4   | 75 GB    | 8 GB         | 5 GB         |
  | MIMIC-III-CareVue | V1.4   | 38 GB    | 3 GB         | 5 GB         |
  | MIMIC-IV          | V2.0   | 99 GB    | 9 GB         | 5 GB         |
  | MIMIC-IV          | V2.2   | 100 GB   | 9 GB         | 5 GB         |
  | eICU              | V2.0   | 55 GB    | 6 GB         |              |


### 5.6 数据集安装时间
- BDMCC软件具有极高的执行效率和性能。以10代intel CPU 10850K、内存64G的macOS为例，各数据集和模块的安装时间如下表：

  | DBeaver中对应数据集名称 | 数据集            | 版本号 | Base模块 | Concepts模块 | BDMCC模块 |
  | ----------------------- | ----------------- | ------ | -------- | ------------ | ------------ |
  | mimic3_demo             | MIMIC-III-Demo    | V1.4   | 10 s     | 19 s         |              |
  | mimic3                  | MIMIC-III         | V1.4   | 53 min   | 40 min       | 10 min       |
  | mimic3_carevue          | MIMIC-III-CareVue | V1.4   | 22 min   | 22 min       | 10 min       |
  | mimic4                  | MIMIC-IV          | V2.0   | 54 min   | 55 min       | 18 min       |
  | mimic4_v22              | MIMIC-IV          | V2.2   | 54 min   | 54 min       | 18 min       |
  | eicu                    | eICU              | V2.0   | 15 min   | 21 min       |              |
  
  
## 6 各系统运行截图

- Windows下默认主题、中文语言
<p align="center">
  <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/win_run_01.png" width="80%" height="80%" />
</p>

- macOS下默认主题、中文语言
<p align="center">
  <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/mac_run_01.png" width="80%" height="80%" />
</p>

- Linux系统暗黑主题、英文语言
<p align="center">
  <img src="https://raw.githubusercontent.com/ningyile/BDMCC_APP/main/img/linux_run_01.png" width="80%" height="80%" />
</p>

## 7 更新日志
- **V1.0.3** 更新MIMIC系列数据集安装代码（主要是Concepts相关代码），与MIT官方保持同步（更新至2024-1-1）；增加对MIMIC-IV V2.2数据集的支持；增加MIMIC-III V1.4、MIMIC-III-CareVue V1.4的BDMCC增强表单；增加网络故障时相关信息的提示；优化云连接获取逻辑（云链接timeout阈值为30s，增加全国/全球动态IP加速）；增加数据集文件校验，以及Base、Concepts、BDMCC模块单独校验功能。
- **V1.0.2** 修复MIMIC-IV V2.0数据集下的BDMCC模块的bdmcc_population表单安装至Concepts模块下（mimic_derived模式下）的bug；优化首次启动时PG用户设置显示标签。
- **V1.0.1** 支持MIMIC-III-Demo V1.4、MIMIC-III V1.4、MIMIC-III-CareVue V1.4、MIMIC-IV V2.0、eICU V2.0数据集安装。其中MIMIC-IV V2.0含增强型系列表单BDMCC（目前MIMIC-IV V2.0只包含bdmcc_population。MIMIC-III V1.4、MIMIC-III-CareVue V1.4暂无BDMCC系列表单，后续会陆续更新），可有效减少后期R语言代码。
