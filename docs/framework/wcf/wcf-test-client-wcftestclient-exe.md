---
title: WCF 测试客户端 (WcfTestClient.exe)
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4302855-677f-4640-aa90-c5d785d72fb7
caps.latest.revision: 45
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2eb32d36b1e6710f666391f918aff68c33566ab8
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="wcf-test-client-wcftestclientexe"></a>WCF 测试客户端 (WcfTestClient.exe)
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 测试客户端 (WcfTestClient.exe) 是一个 GUI 工具，使用该工具，用户可以输入测试参数、将该输入提交给服务并查看服务发回的响应。 当与 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务主机结合时，它可以提供完美的服务测试体验。  
  
 通常可以找到[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]测试客户端 (WcfTestClient.exe) 在以下位置： C:\Program Files (x86) \Microsoft Visual Studio\2017\Community\Common7\IDE-社区可能是"企业"、"专业"或"社区"之一具体取决于安装的 Visual Studio 的级别。
  
## <a name="scenarios-for-using-test-client"></a>使用测试客户端的方案  
 以下各节讨论了使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端简化开发流程的最常见方案。  
  
### <a name="inside-visual-studio"></a>Visual Studio 内部  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-a-single-service"></a>WCF 服务主机启动 WCF 测试客户端和一项服务  
 在创建新的 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务项目并按 F5 启动调试器后，[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务主机将开始承载项目中的服务。 然后 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端将会打开，并显示在配置文件中定义的服务终结点列表。 可以测试参数和调用服务，并可以重复此过程以继续测试和验证服务。  
  
#### <a name="wcf-service-host-starts-wcf-test-client-with-multiple-services"></a>WCF 服务主机启动 WCF 测试客户端和多项服务  
 也可以使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端来帮助调试包含多项服务的服务项目。 打开 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端时，它将自动循环访问项目服务列表并打开这些服务进行测试。  
  
### <a name="outside-visual-studio"></a>Visual Studio 外部  
 您还可以在 Visual Studio 外部调用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端 (WcfTestClient.exe)，以测试 Internet 上的任意服务。 若要找到此工具，请转到以下位置：  
  
 C:\Program Files\Microsoft Visual Studio 9.0\Common7\IDE\  
  
 若要使用该工具，可以双击此文件名从该位置打开它，也可以从命令行启动它。  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端将任意数目的 URI 作为命令行参数。  这些 URI 是可以测试的服务的 URI。  
  
 `wcfTestClient.exe URI1 URI2 …`  
  
 后[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]测试客户端窗口打开，请单击**文件**->**添加服务**，并输入你想要打开的服务的终结点地址。  
  
## <a name="wcf-test-client-user-interface"></a>WCF 测试客户端用户界面  
 可以将 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端用于一项或多项服务。  
  
### <a name="service-operations"></a>服务操作  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端主窗口的左窗格列出了所有可用的服务及其各自的终结点和操作。  
  
 双击某个操作后，可以在具有此操作名称的新选项卡内的右窗格中查看其内容。  
  
 左窗格还列出了客户端配置文件。 双击任何项可以在新选项卡式窗口内的右窗格中显示文件的内容。  
  
### <a name="entering-test-parameters"></a>输入测试参数  
 若要查看测试参数，请双击某个操作以在右侧窗格中打开它。 参数显示在**格式化**默认情况下，视图，你可以输入任意值的服务进行测试的参数。  
  
 若要查看消息的 XML，请单击**XML**。 若要将其发送给服务，请单击**Invoke**。  
  
 数据集参数，请单击 **...** 下一步按钮**编辑...** 若要在新窗口中显示数据网格中编辑它。 请注意**复制数据集**和**粘贴数据集**按钮。 如果第一次编辑时 DataSet 对象的架构未知，则 DataGrid 为空。 您必须将具有相同架构的 DataSet 对象粘贴到 DataGrid 中的当前对象。 （请注意，在粘贴操作之前需要从其他位置复制架构。）你可以通过单击来复制 Dataset 对象以供将来使用**复制数据集**按钮。  
  
 服务响应将出现在测试参数下面。  
  
> [!NOTE]
>  如果预期的返回值是字符串，则结果将显示为带引号的字符串，即使提供的输入未包含在引号中，也是如此。  
  
 如果在创建服务约定时将特定操作指定为单向操作，则不会显示服务响应。 消息一旦处于排队等待发送状态，则会弹出一个对话框，通知您已成功发送消息。  
  
### <a name="session-support"></a>会话支持  
 **启动新的代理**服务操作的选项卡中的复选框可以切换会话支持。 默认情况下清除此框。  
  
 当您输入某个特定操作 （或相同的服务终结点中的另一个操作） 的测试参数并单击**Invoke**多次清除此复选框，这些操作将共用一个代理且服务状态在多个操作中保持。  
  
 如果**启动新的代理**复选框已选中，则为每个启动新的代理**Invoke**、 以前的会话方案终止，和重置服务状态。  
  
### <a name="editing-client-configuration"></a>编辑客户端配置  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端主窗口的左窗格列出了客户端配置文件。 双击任何项可以在右窗格中显示文件的内容。  
  
#### <a name="edit-with-service-configuration-editor"></a>使用服务配置编辑器进行编辑  
 右键单击**配置文件**在左窗格中，选择上下文菜单**用 SvcConfigEditor 进行编辑**。 服务配置编辑器启动并显示客户端配置内容。 可以编辑配置，然后将其保存在此工具中。  
  
 在服务配置编辑器中保存此文件后，[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端将显示一条警告消息，通知您该文件已在外部修改，并询问您是否要重新加载它。  
  
 如果你选择**是**，"Client.dll.config"选项卡中的配置内容将反映在编辑器中所做的更改。  
  
 如果你选择**否**，"Client.dll.config"选项卡中的配置内容保持不变并已更改的内容自动保存到源代码文件。  
  
#### <a name="restore-to-default-configuration"></a>还原到默认配置  
 如果你想要取消所有更改并还原到默认客户端配置，右键单击**配置文件**在左窗格中，选择上下文菜单**还原到默认配置**。默认配置值将加载并还原"Client.dll.config"选项卡中的内容。  
  
#### <a name="validate-changes"></a>验证更改  
 在 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端中加载已保存的更改时，会对照 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 架构检查配置的有效性。 如果发现错误，将显示一个对话框来给出错误详细信息。  
  
 在代理生成、 二进制编译或服务调用，支持编辑 （即，"编辑..."、"还原 …"等） 的菜单项被禁用。 将更新后的配置加载到 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端时还将禁用服务调用。  
  
#### <a name="persist-client-configuration"></a>使客户端配置保持不变  
 **工具**->**选项**->**客户端配置**选项卡包含**始终重新生成配置时启动服务**选项，它默认处于启用状态。 该选项指定每次 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端加载服务时，都会基于最新的服务协定和服务 App.config 文件重新生成一个配置文件。  
  
 如果你已编辑的客户端配置你[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]服务并想要始终使用此更新的文件来调试你的服务，你可以取消选中**重新生成**选项。 这样，即使更新服务并重新打开 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端，Client.dll.config 文件将是您先前更新过的配置文件，而不是基于已更新的服务重新生成的文件。  
  
 但是，您可能需要编辑此配置文件以使其与重新生成的代理一致。 如果由于更新了服务而导致重新生成的代理与配置文件不匹配，则调用该服务时将出错。  
  
> [!CAUTION]
>  如果您已修改了客户端配置文件并选择以后再使用它，则可以在以下位置找到此文件：  
>   
>  \Documents and 设置\\[User Account] \My Documents\Test 客户端项目。  
>   
>  任何存储到客户端配置文件的已更新的凭据信息都是由此文件夹的访问控制列表 (ACL) 保护的。  
  
### <a name="adding-removing-and-refreshing-services"></a>添加、删除和刷新服务  
  
#### <a name="add-service"></a>添加服务  
 单击**文件**->**添加服务**将服务添加到[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]测试客户端。 然后您需要键入要添加的服务的 URI（终结点地址）。 该服务的地址可以是 mex 地址，也可以是 WSDL 地址。  
  
 您还可以在 10 个最近添加的服务的终结点的列表**最近维修**子菜单。 如果选择其中一个终结点，指定的服务就会添加到 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端。  
  
 此外可以右击服务树的根**我的服务项目**，然后选择**添加服务**来实现相同的结果。  
  
 在代理生成、二进制编译或服务调用期间，支持添加服务的菜单项被禁用。 服务调用也被禁用。  
  
#### <a name="remove-service"></a>移除服务  
 右击要被移除，而选择的服务的服务根目录**删除服务**移除的服务从[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]测试客户端。  
  
 在代理生成、二进制编译或服务调用期间，支持删除服务的菜单项被禁用。 服务调用也被禁用。  
  
#### <a name="refresh-service"></a>刷新服务  
 如果更改时服务[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]运行测试客户端，并且你想要确保[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]为该服务的测试客户端实现是最新，右击该服务的服务根目录，并选择**刷新服务**。 请注意，刷新后服务状态将重置。  
  
 在代理生成、二进制编译或服务调用期间，支持刷新服务的菜单项被禁用。 服务调用也被禁用。  
  
## <a name="location-of-files-generated-by-the-test-client"></a>测试客户端生成的文件的位置  
 默认情况下，[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]测试客户端将生成客户端代码和配置文件存储在"%appdata%\Local\temp\Test Client Projects"文件夹中。 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端退出后，该文件夹随即删除。 如果在修改配置文件，则[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]测试客户端和**始终重新生成启动服务时配置**选项处于禁用状态，则修改后的文件复制到"My Documents\Test 下的"Cached Config"文件夹Client Projects Documents\Test Client Projects"使用一个映射 （元数据地址-到-文件名） XML 文件作为索引。  
  
 也可以在命令行启动 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端，使用 `/ProjectPath` 开关指定一个希望用于存储生成的文件的新路径，或者使用 `/RestoreProjectPath` 开关还原默认位置。 语法如下所示：  
  
 `wcfTestClient.exe /ProjectPath [desired location]`  
  
 运行此命令并不会打开 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端， 而只会更改文件夹位置。 无论 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端运行与否，都可以运行此命令。 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端重新启动时将应用新位置。 在注册表中，或在"%appdata%\Local\temp\Test Client Projects"文件夹的 WcfTestClient.exe.option 文件中，可以保存的位置信息。  
  
## <a name="features-supported-by-wcf-test-client"></a>WCF 测试客户端支持的功能  
 下面是 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端支持的功能的列表：  
  
-   服务调用：请求/响应和单向消息。  
  
-   绑定：Svcutil.exe 支持的所有绑定。  
  
-   控制会话。  
  
-   消息协定。  
  
-   XML 序列化。  
  
 下面是 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端不支持的功能的列表：  
  
-   类型：<xref:System.IO.Stream>、<xref:System.ServiceModel.Channels.Message>、<xref:System.Xml.XmlElement>、<xref:System.Xml.XmlAttribute>、<xref:System.Xml.XmlNode>、实现 <xref:System.Xml.Serialization.IXmlSerializable> 接口的类型（包括相关 <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> 特性）、<xref:System.Xml.Linq.XDocument> 和 <xref:System.Xml.Linq.XElement> 类型以及 ADO.NET <xref:System.Data.DataTable> 类型。  
  
-   双工协定。  
  
-   事务。  
  
-   安全性：[!INCLUDE[infocard](../../../includes/infocard-md.md)]、证书和用户名/密码。  
  
-   绑定：WSFederationbinding、任何上下文绑定和 Https 绑定、WebHttpbinding（Json 响应消息支持）。  
  
## <a name="closing-wcf-test-client"></a>关闭 WCF 测试客户端  
 可以通过以下方式关闭 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 测试客户端：  
  
-   上**文件**菜单上，单击**退出**。 或者，在[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]测试客户端主窗口中，单击**关闭**。 这两种操作还关闭[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]服务自动主机，如果 Visual Studio 调试处理的停止[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]测试客户端由 Visual Studio 启动。  
  
-   右键单击**WCF 服务主机**在通知区域中，然后单击图标**退出。** 这将关闭[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]服务自动主机和[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]测试客户端并停止 Visual Studio 调试处理。  
  
## <a name="see-also"></a>请参阅  
 [WCF 服务主机 (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)
