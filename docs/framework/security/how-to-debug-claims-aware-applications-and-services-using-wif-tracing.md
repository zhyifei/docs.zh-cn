---
title: "如何：使用 WIF 跟踪调试声明感知应用程序和服务 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3d51ba59-3adb-4ca4-bd33-5027531af687
caps.latest.revision: 7
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 7
---
# 如何：使用 WIF 跟踪调试声明感知应用程序和服务
## 适用于  
  
-   Microsoft® Windows® Identity Foundation \(WIF\)  
  
-   服务跟踪查看器工具 \(SvcTraceViewer.exe\)  
  
-   对 WIF 应用程序进行故障排除和调试  
  
## 摘要  
 本操作说明介绍进行后述操作所需的步骤：配置 WIF 跟踪、收集跟踪日志以及使用“跟踪查看器”工具分析跟踪日志。  它为排除 WIF 相关问题所需的操作提供跟踪项的常规映射。  
  
## 内容  
  
-   目标  
  
-   步骤摘要  
  
-   步骤 1 – 使用 Web.config 配置文件配置 WIF 跟踪  
  
-   步骤 2 – 使用跟踪查看器工具分析 WIF 跟踪文件  
  
-   步骤 3 – 确定解决方案以修复 WIF 相关问题  
  
-   相关项  
  
## 目标  
  
-   配置 WIF 跟踪。  
  
-   在跟踪查看器工具中查看跟踪日志。  
  
-   在跟踪日志中标识 WIF 相关问题。  
  
-   将纠正措施应用于在跟踪日志中发现的 WIF 相关问题。  
  
## 步骤摘要  
  
-   步骤 1 – 使用 Web.config 配置文件配置 WIF 跟踪  
  
-   步骤 2 – 使用跟踪查看器工具分析 WIF 跟踪文件  
  
-   步骤 3 – 确定解决方案以修复 WIF 相关问题  
  
## 步骤 1 – 使用 Web.config 配置文件配置 WIF 跟踪  
 在此步骤中，将向 *Web.config* 文件中的配置节添加更改，该文件使 WIF 能够跟踪其事件并将这些事件存储在跟踪日志中。  
  
#### 使用 Web.config 配置文件配置 WIF 跟踪  
  
1.  在 Visual Studio 编辑器中打开根“Web.config”或“App.config”配置文件，方法是在“解决方案资源管理器”中双击文件。  如果解决方案不具有“Web.config” 或“App.config”配置文件，可在“解决方案资源管理器”中右键单击该解决方案，然后单击“添加”，接着单击“新建项...”，从而添加该文件。  在**“新建项”**对话框上，从列表中为“App.config”选择“应用程序配置文件”或为“Web.config”选择“Web 配置文件”并单击**“确定”**。  
  
2.  在配置文件末尾将与下列项相似的配置项添加到“\<configuration\>”节点内的配置文件中：  
  
    ```xml  
    <system.diagnostics>  
        <sources>  
            <source name="System.IdentityModel" switchValue="Verbose">  
                <listeners>  
                    <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="WIFTrace.e2e"/>  
                </listeners>  
            </source>  
        </sources>  
        <trace autoflush="true"/>  
    </system.diagnostics>  
    ```  
  
3.  以上配置指示 WIF 生成详细的跟踪事件并将它们记录到 *WIFTrace.e2e* 文件中。  有关“switchValue”切换的值的完整列表，请参考以下主题中的“跟踪级别”表：[配置跟踪](http://msdn.microsoft.com/library/ms733025.aspx)。  
  
## 步骤 2 – 使用跟踪查看器工具分析 WIF 跟踪文件  
 在此步骤中，将使用跟踪查看器工具 \(SvcTraceViewer.exe\) 来分析 WIF 跟踪日志。  
  
#### 使用跟踪查看器工具 \(SvcTraceViewer.exe\) 分析 WIF 跟踪日志  
  
1.  跟踪查看器工具 \(SvcTraceViewer.exe\) 作为 Windows SDK 的一部分提供。  如果你尚未安装 Windows SDK，可以在此处下载：[Windows SDK](http://www.microsoft.com/download/en/details.aspx?id=8279)。  
  
2.  运行跟踪查看器工具 \(SvcTraceViewer.exe\)。  通常可以在安装路径的 **Bin** 文件夹中找到。  
  
3.  打开 WIF 跟踪日志文件（如 WIFTrace.e2e），方法是在菜单中选择“文件”、“打开…”选项，或使用“Ctrl\+O”快捷键。  在跟踪查看器工具中打开跟踪日志文件。  
  
4.  查看“活动”选项卡中的项。  每个项均应包含一个活动编号、记录的跟踪数、活动持续时间及其开始和结束时间戳。  
  
5.  单击“活动”选项卡。  应可以在该工具的主区域中看到详细的跟踪项。  使用菜单上的“级别”下拉列表筛选特定跟踪级别，例如：**全部**、**警告**、**错误**、**信息**等。  
  
6.  在工具的下部区域中单击特定跟踪项，查看详细信息。  可通过选择相应的选项卡使用“格式化”和“XML”视图来查看详细信息。  
  
## 步骤 3 – 确定解决方案以修复 WIF 相关问题  
 在此步骤中，可以确定通过 WIF 跟踪日志和跟踪查看器工具标识的 WIF 相关问题的解决方案。  它概述了 WIF 相关异常对用于排除问题的潜在解决方案或所需操作的常规映射。  
  
#### 确定解决方案以修复 WIF 相关问题  
  
1.  查看以下 WIF 异常和解决问题所需操作表。  
  
||||  
|-|-|-|  
|**错误 ID**|**错误消息**|**修复错误所需操作**|  
|ID4175|IssuerNameRegistry 未识别的安全令牌的颁发者。  若要接受来自此颁发者的安全令牌，请将 IssuerNameRegistry 配置为返回此颁发者的有效名称。|产生此错误的原因可能是从 MMC 管理单元复制指纹并将其粘贴到 *Web.config* 文件中。  具体而言，从证书属性窗口中复制时，可以获得文本字符串中额外的非打印字符。  此额外的字符将导致指纹匹配失败。可在此处查看正确复制指纹的过程：[http:\/\/msdn.microsoft.com\/library\/ff359102.aspx](http://msdn.microsoft.com/library/ff359102.aspx)|  
  
## 相关项  
  
-   [使用服务跟踪查看器查看相关跟踪和进行故障诊断](http://msdn.microsoft.com/library/aa751795.aspx)