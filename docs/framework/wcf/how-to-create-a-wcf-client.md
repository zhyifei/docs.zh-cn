---
title: 教程：创建 Windows 通信基础客户端
ms.date: 03/19/2019
helpviewer_keywords:
- clients [WCF], running
- WCF clients [WCF], running
ms.assetid: a67884cc-1c4b-416b-8c96-5c954099f19f
ms.openlocfilehash: bfa4cbacc5a947cb51d577503b5e46f9a5f8de39
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184100"
---
# <a name="tutorial-create-a-windows-communication-foundation-client"></a>教程：创建 Windows 通信基础客户端

本教程介绍创建基本 Windows 通信基础 （WCF） 应用程序所需的五项任务中的第四个。 有关教程的概述，请参阅[教程：开始使用 Windows 通信基础应用程序](getting-started-tutorial.md)。

创建 WCF 应用程序的下一个任务是通过从 WCF 服务检索元数据来创建客户端。 您可以使用 Visual Studio 添加服务引用，该服务引用从服务的 MEX 终结点获取元数据。 然后，Visual Studio 会以您选择的语言为客户端代理生成托管源代码文件。 它还创建一个客户端配置文件 *（App.config*）。 此文件使客户端应用程序能够在终结点连接到服务。

> [!NOTE]
> 如果从 Visual Studio 中的类库项目调用 WCF 服务，请使用 **"添加服务参考"** 功能自动生成代理和相关配置文件。 但是，由于类库项目不使用此配置文件，因此您需要将生成的配置文件中的设置添加到调用类库的可执行文件*App.config*文件中。

> [!NOTE]
> 作为替代方法，请使用[ServiceModel 元数据实用程序工具](#servicemodel-metadata-utility-tool)而不是 Visual Studio 来生成代理类和配置文件。

客户端应用程序使用生成的代理类与服务通信。 此过程在教程中描述[：使用客户端](how-to-use-a-wcf-client.md)。

在本教程中，你将了解如何执行以下操作：
> [!div class="checklist"]
>
> - 为 WCF 客户端创建和配置控制台应用项目。
> - 向 WCF 服务添加服务引用以生成代理类和配置文件。

## <a name="create-a-windows-communication-foundation-client"></a>创建 Windows 通信基础客户端

1. 在可视化工作室中创建控制台应用项目：

    1. 在 **"文件"** 菜单中，选择 **"打开** > **项目/解决方案**"并浏览到您以前创建的**入门**解决方案 （*获取入门.sln*）。 选择“打开”。

    2. 在 **"查看"** 菜单中，选择 **"解决方案资源管理器**"。

    3. 在 **"解决方案资源管理器"** 窗口中，选择 **"入门"** 解决方案（顶部节点），然后从快捷菜单中选择 **"添加新** > **项目**"。

    4. 在左侧的 **"添加新项目**"窗口中，在 **"可视 C#"** 或"**可视基本**"下选择**Windows 桌面**类别。

    5. 选择**控制台应用 （.NET 框架）** 模板，然后输入"*开始客户端*"**名称**。 选择“确定”。

2. 在**入门客户端**项目中向<xref:System.ServiceModel>程序集添加引用：

    1. 在 **"解决方案资源管理器"** 窗口中，选择 **"入门客户端**"项目下的 **"参考"** 文件夹，然后从快捷菜单中选择 **"添加引用**"。

    2. 在"**添加引用**"窗口中，在窗口左侧的 **"程序集**"下，选择 **"框架**"。

    3. 查找并选择 **"系统.服务模式**"，然后选择 **"确定**"。

    4. 通过选择 **"全部保存文件** > **"保存**解决方案。

3. 向计算器服务添加服务引用：

   1. 在 **"解决方案资源管理器"** 窗口中，选择 **"入门客户端**"项目下的 **"参考"** 文件夹，然后从快捷菜单中选择 **"添加服务参考**"。

   2. 在 **"添加服务参考"** 窗口中，选择 **"发现**"。

      计算器服务启动，可视化工作室在 **"服务**"框中显示它。

   3. 选择**计算器服务**以展开它并显示服务实现的服务协定。 保留默认**命名空间**并选择 **"确定**"。

      Visual Studio 在 **"入门客户端**"项目中的 **"已连接服务**"文件夹下添加新项目。

### <a name="servicemodel-metadata-utility-tool"></a>服务模型元数据实用程序工具

以下示例演示如何选择使用[ServiceModel 元数据实用程序工具 （Svcutil.exe）](servicemodel-metadata-utility-tool-svcutil-exe.md)来生成代理类文件。 此工具生成代理类文件和*App.config*文件。 以下示例分别演示如何在 C# 和 Visual Basic 中生成代理：

```shell
svcutil.exe /language:cs /out:generatedProxy.cs /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

```shell
svcutil.exe /language:vb /out:generatedProxy.vb /config:app.config http://localhost:8000/GettingStarted/CalculatorService
```

### <a name="client-configuration-file"></a>客户端配置文件

创建客户端后，Visual Studio 将在 **"入门Client"** 项目中创建**App.config**配置文件，该文件应类似于以下示例：

```xml
    <?xml version="1.0" encoding="utf-8" ?>
    <configuration>
        <startup>
            <!-- specifies the version of WCF to use-->
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.6.1" />
        </startup>
        <system.serviceModel>
            <bindings>
                <!-- Uses wsHttpBinding-->
                <wsHttpBinding>
                    <binding name="WSHttpBinding_ICalculator" />
                </wsHttpBinding>
            </bindings>
            <client>
                <!-- specifies the endpoint to use when calling the service -->
                <endpoint address="http://localhost:8000/GettingStarted/CalculatorService"
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">
                    <identity>
                        <dns value="localhost" />
                    </identity>
                </endpoint>
            </client>
        </system.serviceModel>
    </configuration>
```

在[\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md)部分下，请注意[\<终结点>](../configure-apps/file-schema/wcf/endpoint-element.md)元素。 **&lt;终结点&gt;** 元素定义客户端用于访问服务的终结点，如下所示：

- 地址： `http://localhost:8000/GettingStarted/CalculatorService`. 终结点的地址。
- 服务合同： `ServiceReference1.ICalculator`. 服务协定处理 WCF 客户端和服务之间的通信。 当您使用其 **"添加服务参考"** 功能时，Visual Studio 生成了此协定。 它实质上是您在入门项目中定义的合同副本。
- 绑定： <xref:System.ServiceModel.WSHttpBinding>. 绑定指定 HTTP 作为传输、可互操作的安全性和其他配置详细信息。

## <a name="next-steps"></a>后续步骤

在本教程中，你了解了如何执行以下操作：
> [!div class="checklist"]
>
> - 为 WCF 客户端创建和配置控制台应用项目。
> - 向 WCF 服务添加服务引用，以生成客户端应用程序的代理类和配置文件。

前进至下一个教程，了解如何使用生成的客户端。

> [!div class="nextstepaction"]
> [教程：使用 WCF 客户端](how-to-use-a-wcf-client.md)
