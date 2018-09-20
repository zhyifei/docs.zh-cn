---
title: 如何：创建 Windows Communication Foundation 客户端
ms.date: 09/14/2018
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: 1eadb5008575a1a53d685db14d68e42d0dce1360
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2018
ms.locfileid: "46478287"
---
# <a name="how-to-create-a-windows-communication-foundation-client"></a>如何：创建 Windows Communication Foundation 客户端

这是创建 Windows Communication Foundation (WCF) 应用程序所需的六项任务的第四个。 有关全部六项任务的概述，请参阅[入门教程](../../../docs/framework/wcf/getting-started-tutorial.md)主题。

本主题介绍如何从 WCF 服务检索元数据和使用它来创建可以访问该服务的 WCF 代理。 完成此任务是借助**添加服务引用**Visual Studio 提供的功能。 此工具从服务的 MEX 终结点获取元数据，并以所选语言（默认情况下为 C#）为客户端代理生成托管源代码文件。 除了创建客户端代理外，该工具还会创建或更新客户端配置文件，以使客户端应用程序能够连接至其某个终结点上的服务。

> [!NOTE]
> 此外可以使用[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)工具生成的代理类和配置而不是使用**添加服务引用**Visual Studio 中。

> [!NOTE]
> 当从一个在 Visual Studio 类库项目中调用 WCF 服务，可以使用**添加服务引用**功能来自动生成代理和关联的配置文件。 该类库项目不会使用配置文件。 您需要向调用该类库的可执行文件的 app.config 文件中生成的配置文件添加设置。

客户端应用程序使用生成的代理类与服务通信。 此过程所述[如何： 使用客户端](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)。

## <a name="to-create-a-windows-communication-foundation-client"></a>创建 Windows Communication Foundation 客户端

1. 在 Visual Studio 中创建新的控制台应用程序项目。 右键单击入门解决方案中**解决方案资源管理器**，然后选择**添加** > **新建项目**。 在**添加新项目**对话框中的，在左侧，选择**Windows Desktop**类别中的下**Visual C#** 或者**Visual Basic**。 选择**控制台应用 (.NET Framework)** 模板，然后命名项目**GettingStartedClient**。

2. 将对 System.ServiceModel 的引用添加到 GettingStartedClient 项目。 右键单击**引用**GettingStartedClient 项目下的文件夹**解决方案资源管理器**，然后选择**添加引用**。 在中**添加引用**对话框中，选择**Framework**下的对话框左侧**程序集**。 找到并选择**System.ServiceModel**，然后选择**确定**。 通过选择保存解决方案**文件** > **全部保存**。

3. 添加到计算器服务的服务引用。

   1. 首先，启动 GettingStartedHost 控制台应用程序。

   2. 主机运行后，右键单击**引用**GettingStartedClient 项目下的文件夹**解决方案资源管理器**，然后选择**添加** >  **服务引用**。

   3. 在的地址框中输入以下 URL**添加服务引用**对话框： [http://localhost:8000/GettingStartedClient/Service](http://localhost:8000/GettingStartedClient/Service)

   4. 选择**转**。

   中显示 CalculatorService **Services**列表框。 双击 CalculatorService 可展开它并显示由该服务实现的服务协定。 保留为默认命名空间的并选择**确定**。

    在出现新项时添加到使用 Visual Studio 服务的引用，请**解决方案资源管理器**下**服务引用**GettingStartedClient 项目下的文件夹。 如果您使用[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)生成工具、 源代码文件和 app.config 文件。

    您还可以使用命令行工具[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)使用适当的开关来创建客户端代码。 下面的示例生成服务的代码文件和配置文件。 第一个示例演示如何在 VB 中生成代理，并第二个演示如何在 C# 中生成代理：

    ```shell
    svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStartedClient/service
    ```

    ```shell
    svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStartedClient/service
    ```

## <a name="next-steps"></a>后续步骤

你已创建客户端应用程序将用于调用计算器服务的代理。 请转到序列中下一主题。

> [!div class="nextstepaction"]
> [如何：配置客户端](../../../docs/framework/wcf/how-to-configure-a-basic-wcf-client.md)

## <a name="see-also"></a>请参阅

- [ServiceModel 元数据实用工具 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [入门](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [自承载](../../../docs/framework/wcf/samples/self-host.md)
- [如何：使用配置文件发布服务的元数据](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [如何：使用 Svcutil.exe 下载元数据文档](../../../docs/framework/wcf/feature-details/how-to-use-svcutil-exe-to-download-metadata-documents.md)
