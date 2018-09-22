---
title: 如何：在托管应用程序中承载 WCF 服务
ms.date: 09/17/2018
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
ms.openlocfilehash: 131d99457427e0818f78076d987f550a99ad7cf0
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2018
ms.locfileid: "46696274"
---
# <a name="how-to-host-a-wcf-service-in-a-managed-app"></a>如何： 承载的托管应用中的 WCF 服务

若要在托管应用程序中承载某项服务，请在托管应用程序代码内嵌入该服务的代码，在代码中强制定义、通过配置以声明的方式定义或者使用默认终结点定义该服务的终结点，然后创建 <xref:System.ServiceModel.ServiceHost> 的实例。

若要开始接收消息，请调用 <xref:System.ServiceModel.ICommunicationObject.Open%2A> 上的 <xref:System.ServiceModel.ServiceHost>。 这样即可创建并打开服务的侦听器。 以这种方式承载服务的做法通常称为“自承载”，原因是托管的应用程序会自己处理承载工作。 若要关闭服务，请调用 <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> 上的 <xref:System.ServiceModel.ServiceHost>。

在托管的 Windows 服务中、在 Internet Information Services (IIS) 中或在 Windows 进程激活服务 (WAS) 中也可以承载服务。 有关托管服务的选项的详细信息，请参阅[托管服务](../../../docs/framework/wcf/hosting-services.md)。

在托管应用程序中承载服务是一个非常灵活的选项，因为采用此选项时，所需部署的基础结构最少。 有关在托管应用程序中承载服务的详细信息，请参阅[托管应用程序中承载](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)。

下面的过程演示如何在控制台应用程序中实现自承载的服务。

## <a name="create-a-self-hosted-service"></a>创建自承载的服务

1. 创建新的控制台应用程序：

   1. 打开 Visual Studio 并选择**新建** > **项目**从**文件**菜单。

   2. 在中**已安装的模板**列表中，选择**Visual C#** 或**Visual Basic**，然后选择**Windows 桌面**。

   3. 选择**控制台应用**模板。 类型`SelfHost`中**名称**框，然后选择**确定**。

2. 右键单击**SelfHost**中**解决方案资源管理器**，然后选择**添加引用**。 选择**System.ServiceModel**从 **.NET**选项卡，然后选择**确定**。

    > [!TIP]
    > 如果**解决方案资源管理器**窗口不可见，请选择**解决方案资源管理器**从**视图**菜单。

3. 双击**Program.cs**或**Module1.vb**中**解决方案资源管理器**打开在代码窗口中，如果已打开。 在文件顶部添加以下语句：

     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]

4. 定义和实现服务协定。 此示例定义了一个 `HelloWorldService`，它基于对服务的输入返回消息。

     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]

    > [!NOTE]
    > 有关如何定义和实现服务接口的详细信息，请参阅[如何： 定义服务协定](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)并[如何： 实现服务协定](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)。

5. 在 `Main` 方法的顶部，使用该服务的基址创建 <xref:System.Uri> 类的实例。

     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]

6. 创建 <xref:System.ServiceModel.ServiceHost> 类的实例，并将表示服务类型的 <xref:System.Type> 和基址统一资源标识符 (URI) 传递到 <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>。 启用元数据发布，然后调用 <xref:System.ServiceModel.ICommunicationObject.Open%2A> 上的 <xref:System.ServiceModel.ServiceHost> 方法，以初始化服务并使其准备好接收消息。

     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]

    > [!NOTE]
    > 此示例使用默认终结点，且该服务不需要任何配置文件。 如果未配置任何终结点，则运行时会为该服务实现的每个服务协定的每个基地址创建一个终结点。 有关默认终结点的详细信息，请参阅[Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md)并[WCF 服务的简化配置](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。

7. 按**Ctrl**+**Shift**+**B**以生成解决方案。

## <a name="test-the-service"></a>测试服务

1. 按**Ctrl**+**F5**来运行服务。

2. 打开**WCF 测试客户端**。

    > [!TIP]
    > 若要打开**WCF 测试客户端**，打开 Visual Studio 开发人员命令提示符并执行**WcfTestClient.exe**。

3. 选择**添加的服务**从**文件**菜单。

4. 类型`http://localhost:8080/hello`到地址框，然后单击**确定**。

    > [!TIP]
    > 确保服务正在运行，否则此步骤将失败。 如果已经更改了代码中的基址，则在此步骤中使用修改后的基址。

5. 双击**SayHello**下**我的服务项目**节点。 键入到您的姓名**值**中的列**请求**列表，然后单击**Invoke**。

   回复消息出现在**响应**列表。

## <a name="example"></a>示例

下面的示例创建 <xref:System.ServiceModel.ServiceHost> 对象以承载 `HelloWorldService` 类型的服务，然后调用 <xref:System.ServiceModel.ICommunicationObject.Open%2A> 上的 <xref:System.ServiceModel.ServiceHost> 方法。 在代码中提供基址，启用元数据发布，并使用默认终结点。

[!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
[!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]

## <a name="see-also"></a>请参阅

- <xref:System.Uri>
- <xref:System.Configuration.ConfigurationManager.AppSettings%2A>
- <xref:System.Configuration.ConfigurationManager>
- [如何：在 IIS 中承载 WCF 服务](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)
- [自承载](../../../docs/framework/wcf/samples/self-host.md)
- [托管服务](../../../docs/framework/wcf/hosting-services.md)
- [如何：定义服务协定](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)
- [如何：实现服务协定](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)
- [ServiceModel 元数据实用工具 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [使用绑定配置服务和客户端](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [系统提供的绑定](../../../docs/framework/wcf/system-provided-bindings.md)