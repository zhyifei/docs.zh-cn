---
title: 如何：创建 Windows Communication Foundation 客户端
ms.date: 03/30/2017
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: d2932293536f875d8986d8d49842cddc196ced0f
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33806268"
---
# <a name="how-to-create-a-windows-communication-foundation-client"></a>如何：创建 Windows Communication Foundation 客户端
这是创建 Windows Communication Foundation (WCF) 应用程序所需的六项任务的第四个。 有关全部六项任务的概述，请参阅[入门教程](../../../docs/framework/wcf/getting-started-tutorial.md)主题。  
  
 本主题介绍如何从 WCF 服务中检索元数据并使用它来创建 WCF 代理可以访问该服务。 通过使用 Visual Studio 提供的“添加服务引用”功能完成此任务。 此工具从服务的 MEX 终结点获取元数据，并以所选语言（默认情况下为 C#）为客户端代理生成托管源代码文件。 除了创建客户端代理外，该工具还会创建或更新客户端配置文件，以使客户端应用程序能够连接至其某个终结点上的服务。  
  
> [!NOTE]
>  你还可以使用[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)工具生成的代理类和配置，而非使用在 Visual Studio 添加服务引用。  
  
> [!WARNING]
>  当从类库项目中调用 WCF 服务时[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]可以使用添加服务引用功能自动生成代理和关联的配置文件。  该类库项目不会使用配置文件。 您需要将生成的配置文件中的设置添加到将调用该类库的可执行文件的 app.config 文件中。  
  
 客户端应用程序使用生成的代理类与服务通信。 中介绍了此过程[如何： 使用客户端](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)。  
  
### <a name="to-create-a-windows-communication-foundation-client"></a>创建 Windows Communication Foundation 客户端  
  
1.  通过右键单击入门解决方案，依次选择创建新的控制台应用程序项目**添加**，**新项目**。 在**添加新项目**对话框中的，在对话框中，选择左侧**Windows**下**C#** 或**VB**。 在对话框的中心部分选择**控制台应用程序**。 将项目命名为 `GettingStartedClient`。  
  
2.  通过右键单击 GettingStartedClient 项目的目标框架设置为.NET Framework 4.5 **GettingStartedClient**在解决方案资源管理器并选择**属性**。 在下拉框中标记为**目标框架**选择 **.NET Framework 4.5**。 为 VB 项目是稍有不同，在 GettingStartedClient 项目属性对话框，请设置目标框架，单击**编译**屏幕中，左侧选项卡，然后单击**高级编译选项**在对话框左下角的按钮。 然后选择 **.NET Framework 4.5**的下拉框中标记为**目标框架**。  
  
     设置目标框架将导致 Visual Studio 2011 重新加载解决方案，按**确定**出现提示时。  
  
3.  将对 System.ServiceModel 的引用添加到 GettingStartedClient 项目中，右键单击**引用**在解决方案资源管理器，选择 GettingStartedClient 项目下的文件夹**添加**引用。 在**添加引用**对话框中，选择**Framework**在对话框的左侧。 请在“搜索程序集”文本框中，键入 `System.ServiceModel`。 在对话框的中心部分选择**System.ServiceModel**，单击**添加**按钮，然后单击**关闭**按钮。 通过单击保存解决方案**保存所有**主菜单下的按钮。  
  
4.  接下来，将服务引用添加到计算器服务。 在此之前，必须先启动 GettingStartedHost 控制台应用程序。 主机运行后，你可右键单击解决方案资源管理器中 GettingStartedClient 项目下的引用文件夹，并选择添加服务引用对话框的地址框中的以下 URL 中添加服务引用和类型： 超链接"http://localhost:8000/ServiceModelSamples/Service"http://localhost:8000/ServiceModelSamples/Service单击**转**按钮。 然后，CalculatorService 应显示在“服务”列表框中，双击 CalculatorService，然后它将展开并显示由该服务实现的服务协定。 保留默认命名空间，并且单击**确定**按钮。  
  
     使用 Visual Studio 将引用添加到服务时，解决方案资源管理器中 GettingStartedClient 项目下的“服务引用”文件夹下将显示一个新项。  如果你使用[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)工具将生成一个源代码文件和 app.config 文件。  
  
     你还可以使用命令行工具[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)与相应的开关来创建客户端代码。 下面的示例生成服务的代码文件和配置文件。 第一个示例显示如何在 VB 中生成代理，第二个示例显示如何在 C# 中生成代理：  
  
    ```  
    svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/ServiceModelSamples/service  
    ```  
  
    ```csharp  
    svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/ServiceModelSamples/service  
    ```  
  
 现在，您已创建了客户端应用程序将用于调用计算器服务的代理。 继续执行下一主题序列中：[如何： 配置客户端](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)  
  
## <a name="see-also"></a>请参阅  
 [ServiceModel 元数据实用工具 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [入门](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [自承载](../../../docs/framework/wcf/samples/self-host.md)  
 [如何：使用配置文件发布服务的元数据](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [如何：使用 Svcutil.exe 下载元数据文档](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
