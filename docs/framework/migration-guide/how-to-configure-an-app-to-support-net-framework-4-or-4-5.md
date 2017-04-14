---
title: "如何：配置应用程序以支持 .NET Framework 4 或 4.5 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 63c6b9a8-0088-4077-9aa3-521ab7290f79
caps.latest.revision: 14
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 14
---
# 如何：配置应用程序以支持 .NET Framework 4 或 4.5
承载公共语言运行时 \(CLR\) 的所有应用程序均需启动（或称“激活”）CLR 以运行托管代码。  通常，.NET Framework 应用程序在生成它的 CLR 版本上运行，但您可以使用应用程序配置文件（有时称为 app.config 文件）来更改桌面应用程序的此行为。  但是，您不能使用应用程序配置文件来更改 Windows 应用商店应用或 Windows Phone 应用程序的默认激活行为。  本文说明如何使桌面应用程序能够在 .NET Framework 的其他版本上运行，并提供了如何定位版本 4 或 4.5 的示例。  
  
 按下列顺序确定在其上运行应用程序的 .NET Framework 的版本：  
  
-   配置文件。  
  
     如果应用程序配置文件包括指定了一个或多个 .NET Framework 版本的 [\<supportedRuntime\>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 项，并且这些版本之一存在于用户的计算机上，则应用程序将在此版本上运行。  配置文件按 [\<supportedRuntime\>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 项的列出顺序读取这些项，并使用存在于用户计算机上的所列的第一个 .NET Framework 版本。  \(对于 1.0 版，使用 [\<requiredRuntime\> 元素](../../../docs/framework/configure-apps/file-schema/startup/requiredruntime-element.md)。）  
  
-   编译的版本。  
  
     如果不存在任何配置文件，但用户计算机上存在基于其构建应用程序的 .NET Framework 版本，则此应用程序将在此版本上运行。  
  
-   已安装的最新版本。  
  
     如果应用程序基于其生成的 .NET Framework 版本不存在，并且配置文件未在 [\<supportedRuntime\> 元素](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md)中指定版本，则应用程序将尝试在用户计算机上存在的 .NET Framework 的最新版本上运行。  
  
     但是，.NET Framework 1.0、1.1、2.0、3.0 和 3.5 应用程序不会自动在 .NET Framework 4 或更高版本上运行，在某些情况下，用户可能会收到错误，且系统可能会提示用户安装 .NET Framework 3.5。  由于不同版本的 Windows 系统包含的 .NET Framework 版本不同，因此激活行为还取决于用户的操作系统。  如果应用程序支持 .NET Framework 3.5 和 4 或更高版本，建议您在配置文件中使用多个条目来指明这一点，以避免 .NET Framework 初始化错误。  有关详细信息，请参见 [版本和依赖关系](../../../docs/framework/migration-guide/versions-and-dependencies.md)。  
  
 为了利用版本 4 和 4.5 中的性能改进，您可能还需要将您的 .NET Framework 3.5 应用程序配置为在 .NET Framework 版本 4 或 4.5 上运行，甚至在安装了 .NET Framework 3.5 的计算机上也是如此。  
  
> [!IMPORTANT]
>  建议您始终在您支持的每个 .NET Framework 版本上测试应用程序。  有关升级应用程序以支持更高版本的 .NET Framework 的信息，请参阅 [版本兼容性](../../../docs/framework/migration-guide/version-compatibility.md)。  
  
 有关修改 .NET Framework 1.0 和 1.1 应用以支持 Windows 7 和 Windows 8 的信息，请参阅[从 .NET Framework 1.1 迁移](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)。  
  
### 将应用程序配置为在 .NET Framework 4 或 4.5 上运行  
  
1.  添加或查找 .NET Framework 项目的配置文件。  应用程序的配置文件与该应用程序位于相同的目录中，并且具有相同的名称，只不过它具有扩展名 .config。  例如，对于名为 MyExecutable.exe 的应用程序，应用程序配置文件的名称为 MyExecutable.exe.config。  
  
     若要添加配置文件，请在 Visual Studio 的菜单栏中，依次选择**“项目”**和**“添加新项”**。  从左侧窗格中选择**“常规”**，然后选择**“配置文件”**。  将配置文件命名为 *appName*.exe.config。  这些菜单选项对于 Windows 应用商店应用或 Windows Phone 应用程序项目不可用，因为您无法在这些平台上更改激活策略。  
  
2.  将如下 [\<supportedRuntime\>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 元素添加到应用程序配置文件中：  
  
    ```  
    <configuration>  
      <startup>  
        <supportedRuntime version="<version>"/>  
      </startup>  
    </configuration>  
  
    ```  
  
     其中，*\<version\>* 指定与应用支持的 .NET Framework 版本匹配的 CLR 版本。  使用以下字符串：  
  
    -   .NET Framework 1.0：“v1.0.3705”  
  
    -   .NET Framework 1.1：“v1.1.4322”  
  
    -   .NET Framework 2.0、3.0 和 3.5：“v2.0.50727”  
  
    -   .NET Framework 4 和 4.5（包括 4.5.1 等单点发行版）：“v4.0”  
  
     可以添加多个 [\<supportedRuntime\>](../../../docs/framework/configure-apps/file-schema/startup/supportedruntime-element.md) 元素（按优先顺序列出）以指定对 .NET Framework 的多个版本的支持。  
  
 下表演示安装在计算机上的应用程序配置文件设置和 .NET Framework 版本如何确定在计算机上运行的 .NET Framework 3.5 应用程序的版本。  这些示例特定于 .NET Framework 3.5 应用程序，但您可以将类似逻辑用于使用早期版本的 .NET Framework 生成的目标应用程序。  请注意，.NET Framework 2.0 版本号 \(v2.0.50727\) 用于在应用程序配置文件中指定 .NET Framework 3.5。  
  
|||||  
|-|-|-|-|  
|App.config 文件设置|在安装了 3.5 版的计算机上|在安装了版本 3.5 和 4 或 4.5 的计算机上|在安装了版本 4 或 4.5 的计算机上|  
|无|在 3.5 上运行|在 3.5 上运行|显示提示用户安装正确版本的错误消息\*|  
|`<supportedRuntime version="v2.0.50727"/>`|在 3.5 上运行|在 3.5 上运行|显示提示用户安装正确版本的错误消息\*|  
|`<supportedRuntime version="v2.0.50727"/>`  <br />  `<supportedRuntime version="v4.0"/>`|在 3.5 上运行|在 3.5 上运行|在 4 或 4.5 上运行|  
|`<supportedRuntime version="v4.0"/>`  <br />  `<supportedRuntime version="v2.0.50727"/>`|在 3.5 上运行|在 4 或 4.5 上运行|在 4 或 4.5 上运行|  
|`<supportedRuntime version="v4.0"/>`|显示提示用户安装正确版本的错误消息\*|在 4 或 4.5 上运行|在 4 或 4.5 上运行|  
  
 \* 有关此错误消息以及避免它出现的方法的详细信息，请参阅[.NET Framework 初始化错误：管理用户体验](../../../docs/framework/deployment/initialization-errors-managing-the-user-experience.md)。  
  
## 请参阅  
 [从 .NET Framework 1.1 迁移](../../../docs/framework/migration-guide/migrating-from-the-net-framework-1-1.md)   
 [迁移指南](../Topic/Migration%20Guide%20to%20the%20.NET%20Framework%204.6%20and%204.5%20.md)