---
title: "WCF 服务主机 (WcfSvcHost.exe)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8643a63d-a357-4c39-bd6c-cdfdf71e370e
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 39d59e23b407a01e91f68022a1b67e590858235e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="wcf-service-host-wcfsvchostexe"></a>WCF 服务主机 (WcfSvcHost.exe)
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 服务主机 (WcfSvcHost.exe) 允许您启动 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 调试器 (F5) 以自动承载和测试已实现的服务。 然后可以使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端 (WcfTestClient.exe) 或您自己的客户端来测试服务，以查找并解决任何潜在错误。  
  
## <a name="wcf-service-host"></a>WCF 服务主机  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务主机将枚举 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务项目中的服务、加载项目的配置并为它所找到的每项服务对主机进行实例化。 此工具通过 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 服务模板集成到 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 中，在您开始调试项目时将会调用此工具。  
  
 使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务主机可以承载 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务（在 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务库项目中），而无需在开发过程中额外编写代码或提交到特定的主机。  
  
> [!NOTE]
>  [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务主机不支持部分信任。 如果想要在部分信任中使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务，请不要使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 中的 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 服务库项目模板生成服务。 而应通过选择 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 服务网站模板在 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 中创建新的网站。该网站可以在支持 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 部分信任的 WebServer 中承载服务。  
  
## <a name="project-types-hosted-by-wcf-service-host"></a>WCF 服务主机承载的项目类型  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务主机可以承载以下 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务库项目类型：[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务库、顺序工作流服务库、状态机工作流服务库和联合服务库。 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]服务主机也可以承载这些服务可以添加到服务库项目使用**添加项**功能。 这包括 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务、WF 状态机服务、WF 顺序服务、XAML WF 状态机服务和 XAML WF 顺序服务。  
  
 但是，应该注意到该工具将不会帮助您配置主机。 对于此项任务，必须手动编辑 App.config 文件。 另外，此工具也不会验证用户定义的配置文件。  
  
> [!CAUTION]
>  不应该使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务主机在生产环境中承载服务，因为其设计初衷并不是为了执行此操作。  [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务主机无法满足此类环境的可靠性、安全性和可管理性要求。 请改用 IIS，因为它可以提供卓越的可靠性和监视功能，并且是承载服务的首选解决方案。 在服务开发完成后，应该将服务从 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务主机迁移到 IIS。  
  
## <a name="scenarios-for-using-wcf-service-host-inside-visual-studio"></a>在 Visual Studio 中使用 WCF 服务主机的方案  
 下表列出了中的所有参数**命令行自变量**对话框中，可通过右键单击你的项目中找到**解决方案资源管理器**中[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]，选择**属性**，然后选择**调试**选项卡上，单击**启动项目**。 这些参数可用于配置 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务主机。  
  
|参数|含义|  
|---------------|-------------|  
|`/client`|一个可选参数，用于指定要在承载服务后运行的可执行文件的路径。 这将在承载后启动 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端。|  
|`/clientArg`|将字符串指定为传递给自定义客户端应用程序的自变量。|  
|`/?`|显示帮助文本。|  
  
#### <a name="using-wcf-test-client"></a>使用 WCF 测试客户端  
 在创建新的 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务项目并按 F5 启动调试器后，[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务主机将开始承载它在项目中找到的所有服务。 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端将会自动打开，并显示在配置文件中定义的服务终结点列表。 可以从主窗口中测试参数并调用服务。  
  
 若要确保[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]使用测试客户端中，右键单击你的项目中**解决方案资源管理器**中[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]，选择**属性**，然后选择**调试**选项卡。单击**启动项目**并确保中显示以下**命令行自变量**对话框。  
  
 `/client:WcfTestClient.exe`  
  
#### <a name="using-a-custom-client"></a>使用自定义客户端  
 若要使用自定义客户端，右键单击你的项目中**解决方案资源管理器**中[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]，选择**属性**，然后选择**调试**选项卡。单击**启动项目**和编辑`/client`中的参数**命令行自变量**对话框中，以指向自定义客户端，如下面的示例中所示。  
  
 `/client:"path/CustomClient.exe"`  
  
 如果按 F5 再次启动服务，则 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务主机将在您启动调试器时自动启动您的自定义客户端。  
  
 也可以按照以下示例中的指示使用 `/clientArg:` 形参将字符串指定为传递给自定义客户端应用程序的实参。  
  
 `/client:"path/CustomClient.exe" /clientArg:"arguments that are passed to Client"`  
  
 例如，如果使用的是联合服务库模板，则可以使用以下命令行自变量：  
  
 `/client:iexplore.exe /clientArgs:http://localhost:8731/Design_Time_Addresses/Feed1/`  
  
#### <a name="specifying-no-client"></a>指定无客户端  
 若要指定无客户端将使用后[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]服务承载，右键单击你的项目中**解决方案资源管理器**中[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]，选择**属性**，然后选择**调试**选项卡。单击**启动项目**并使**命令行自变量**对话框留空。  
  
#### <a name="using-a-custom-host"></a>使用自定义主机  
 若要使用自定义主机，右键单击你的项目中**解决方案资源管理器**中[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]，选择**属性**，然后选择**调试**选项卡。单击**启动外部程序**并输入自定义宿主的完整路径。 你还可以使用**命令行自变量**对话框中，指定要传递给该主机自变量。  
  
## <a name="wcf-service-host-user-interface"></a>WCF 服务主机用户界面  
 当最初调用[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]服务主机 (由内按 F5 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)])，则**WCF 服务主机**窗口将自动打开。 当正在运行 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务主机时，此程序的图标将出现在通知区域中。 双击该图标可以打开**WCF 服务主机**窗口  
  
 如果在承载服务过程中出错，则将打开“[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务主机”对话框以显示相关信息。  
  
 **WCF 服务主机**主窗口包含以下两个菜单：  
  
-   **文件**： 包含**关闭**和**退出**命令。 当你单击**关闭**、 **WCF 服务主机**对话框关闭，但会继续承载服务。 当你单击**退出**，[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]服务主机也将关闭。 这还将停止所有承载的服务。  
  
-   **帮助**： 包含**有关**包含版本信息的命令。 它还包含**帮助**可以打开的帮助文件的命令。  
  
 主**WCF 服务主机**窗口包含两个区域：  
  
-   第一个领域是**服务**。 该区域包含一个显示所有服务基本信息的列表。 这些信息包括：  
  
    -   **服务**： 列出所有的服务。  
  
    -   **状态**： 列出服务的状态。 有效值为"已启动"、"Stopped"和"错误"。  
  
    -   **元数据地址**： 显示服务的元数据地址。  
  
-   第二个区域是**的其他信息**。 它显示服务状态的详细的说明，在中选择特定的服务行**服务**区域。 如果状态为“错误”，则可以在屏幕上查看完整的错误消息。  
  
## <a name="stopping-wcf-service-host"></a>停止 WCF 服务主机  
 可以通过以下四种方法关闭 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务主机：  
  
-   在 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 中停止调试会话。  
  
-   选择**退出**从**文件**菜单中的**WCF 服务主机**窗口。  
  
-   选择**退出**从上下文菜单[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]系统通知区域中的服务主机任务栏图标。  
  
-   退出正在使用的 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]。  
  
## <a name="using-service-host-without-administrator-privilege"></a>在无管理员权限的情况下使用服务主机  
 为了使没有管理员权限的用户能够开发 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务，在安装 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 的过程中为命名空间“http://+:8731/Design_Time_Addresses”创建了一个 ACL（访问控制列表）。 该 ACL 被设置为“(UI)”，这将包括登录到此计算机的所有交互用户。 管理员可以在此 ACL 中添加或移除用户，或者打开其他端口。此 ACL 使用户可以在无管理员权限的情况下使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务自动主机 (wcfSvcHost.exe)。  
  
 可以使用提升的管理员帐户在 [!INCLUDE[wv](../../../includes/wv-md.md)] 中通过 netsh.exe 工具来修改访问权限。 下面是使用 netsh.exe 的示例。  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 Netsh.exe 的详细信息，请参阅"[如何使用 Netsh.exe 工具和命令行开关](http://go.microsoft.com/fwlink/?LinkId=97877)"。  
  
## <a name="see-also"></a>另请参阅  
 [WCF 测试客户端 (WcfTestClient.exe)](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
