---
title: "如何：启用 WIF 跟踪 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 271b6889-3454-46ff-96ab-9feb15e742ee
caps.latest.revision: 3
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 3
---
# 如何：启用 WIF 跟踪
## 适用于  
  
-   Microsoft® Windows® 标识基础 \(WIF\)  
  
-   ASP.NET® Web 窗体  
  
## 摘要  
 本帮助主题。中启用 ASP.NET 应用程序的跟踪详细 WIF 提供分步过程。  它还提供指令验证测试应用程序的跟踪侦听器、记录正确工作。  本帮助主题没有创建的附带了标识和访问工具的安全标记服务 \(STS\) 详细说明和开发使用 STS。  出于测试目的 STS 开发不执行实际身份验证和计划。只。  您将需要安装和标识访问工具完成本帮助主题。  可从以下位置下载：[标识和访问工具](http://go.microsoft.com/fwlink/?LinkID=245849)  
  
> [!IMPORTANT]
>  被动启用应用程序，即，使用联合 WS 身份验证协议的应用程序跟踪 WIF，可能会公开应用程序到拒绝服务攻击 \(DoS\) 或到信息泄露给恶意的方。  这包括 RPs 被动和被动 STSes。  为此，我们建议不启用 RPs 的被动 WIF 在生产环境中跟踪或 STSes。  
  
## 内容  
  
-   目标  
  
-   概述  
  
-   步骤摘要  
  
-   步骤 1 \- 创建简单 ASP.NET Web 窗体应用程序和启用跟踪  
  
-   步骤 2 \- 测试解决方案  
  
## 目标  
  
-   WIF 使用创建和开发 STS 从标识的简单 ASP.NET 应用程序进行访问工具  
  
-   启用跟踪并验证它是否  
  
## 概述  
 跟踪使您可以调试和疑难解答问题的许多类型。WIF，包括标记、Cookie、协议消息声明，等等。  WIF 跟踪类似 WCF 跟踪；例如，可以选择任何从跟踪详细显示重要消息到任何消息。  WIF 跟踪可以生成在 **.xml** 文件中是可见的。使用跟踪查看服务工具的 **.svclog** 文件。  例如本工具在 Windows SDK 的 **bin** 目录中安装计算机的路径，例如：**C:\\Program Files\\Microsoft SDKs\\Windows\\v7.1\\Bin\\SvcTraceViewer.exe**。  
  
## 步骤摘要  
  
-   步骤 1 \- 创建简单 ASP.NET Web 窗体应用程序和启用跟踪  
  
-   步骤 2 \- 测试解决方案  
  
## 步骤 1 \- 创建简单 ASP.NET Web 窗体应用程序和启用跟踪  
 在此步骤中，将创建一个新的 ASP.NET Web 窗体应用程序并修改 *Web.config 文件* 启用跟踪。  
  
#### 创建一个简单的 ASP.NET 应用程序  
  
1.  启动 Visual Studio 并单击 **文件**，**新建**和 **项目**。  
  
2.  在 **新建项目** 窗口中，单击 **ASP.NET Web 窗体应用程序**。  
  
3.  在 **名称**中，键入 `TestApp` 并按 **确定**。  
  
4.  右击 **TestApp** 项目下的 **解决方案资源管理器**，然后选择 **身份认证和访问**。  
  
5.  **身份认证和访问** 窗口。  在 **提供程序**下，选择 **测试与本地开发 STS 的应用程序**，然后单击 **应用**。  
  
6.  创建一个名为 **日志** 的 **C:** 文件夹中，如下所示：驱动器的根目录 **C:\\logs**  
  
7.  将以下元素添加到 **\<system.diagnostics\>** 在结束 **\<\/configSections\>** 元素后的 *Web.config 配置文件*，如下所示：  
  
    ```  
    <configuration>  
        <configSections>  
        …  
        </configSections>  
        <system.diagnostics>  
            <sources>  
                <source name="System.IdentityModel" switchValue="Verbose">  
                    <listeners>  
                        <add name="xml" type="System.Diagnostics.XmlWriterTraceListener" initializeData="C:\logs\WIF.xml" />  
                    </listeners>  
                </source>  
            </sources>  
            <trace autoflush="true" />  
        </system.diagnostics>  
    ```  
  
    > [!NOTE]
    >  然后记录才能开始，在 **initializeData** 特性所需指定的目录位置。  如果该位置不存在，则不会创建。  
  
     上面配置的设置将启用跟踪。WIF 的 **详细** 并保存结果日志添加到 **C:\\logs\\WIF.xml** 文件。  
  
## 步骤 2 \- 测试解决方案  
 在本步骤，则测试 WIF 启用 ASP.NET 应用程序验证记录。  
  
#### 负责测试成功的跟踪 WIF 启用 ASP.NET 应用程序  
  
1.  解决方案按 **F5** 键运行。  您应提供与默认 ASP.NET 主页和自动验证使用用户名 *特里*，是默认用户由开发 STS 返回。  
  
2.  关闭浏览器窗口然后再导航到 **C:\\logs** 文件夹。  使用文本编辑器，打开 **C:\\logs\\WIF.xml** 文件。  
  
3.  检查 **WIF.xml** 并验证该文件包含以 **\<E2ETraceEvent\>**开始的输入。  这些跟踪包含阐释的 **\<TraceRecord\>** 元素。跟踪的活动，如 **验证 SecurityToken**。