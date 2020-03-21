---
title: 教程：托管并运行基本的 Windows 通信基础服务
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 30eb86987b83427b94c6fff22755cde3d73dd9f0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184074"
---
# <a name="tutorial-host-and-run-a-basic-windows-communication-foundation-service"></a>教程：托管并运行基本的 Windows 通信基础服务

本教程介绍创建基本 Windows 通信基础 （WCF） 应用程序所需的五个任务中的第三个。 有关教程的概述，请参阅[教程：开始使用 Windows 通信基础应用程序](getting-started-tutorial.md)。

创建 WCF 应用程序的下一个任务是在控制台应用程序中托管 WCF 服务。 WCF 服务公开一个或多个终结点，每个*终结点*公开一个或多个服务操作。 服务终结点指定以下信息：

- 您可以在其中找到服务的地址。
- 包含描述客户端必须如何与服务通信的信息的绑定。
- 定义服务为其客户端提供的功能的协定。

在本教程中，你将了解如何执行以下操作：
> [!div class="checklist"]
>
> - 创建和配置用于托管 WCF 服务的控制台应用项目。
> - 添加代码以承载 WCF 服务。
> - 更新配置文件。
> - 启动 WCF 服务并验证其正在运行。

## <a name="create-and-configure-a-console-app-project-for-hosting-the-service"></a>创建和配置托管服务的控制台应用项目

1. 在可视化工作室中创建控制台应用项目：

    1. 在 **"文件"** 菜单中，选择 **"打开** > **项目/解决方案**"并浏览到您以前创建的**入门**解决方案 （*获取入门.sln*）。 选择“打开”。

    2. 在 **"查看"** 菜单中，选择 **"解决方案资源管理器**"。

    3. 在 **"解决方案资源管理器"** 窗口中，选择 **"入门"** 解决方案（顶部节点），然后从快捷菜单中选择 **"添加新** > **项目**"。

    4. 在左侧的 **"添加新项目**"窗口中，在 **"可视 C#"** 或"**可视基本**"下选择**Windows 桌面**类别。

    5. 选择**控制台应用 （.NET 框架）** 模板，然后输入"*入门主机*"**的名称**。 选择“确定”。

2. 在**入门主机**项目中向**入门项目**添加引用：

    1. 在 **"解决方案资源管理器"** 窗口中，选择 **"入门主机**"项目下的 **"参考"** 文件夹，然后从快捷菜单中选择 **"添加引用**"。

    2. 在"**添加参考**"对话框中，在窗口左侧**的项目**下，选择 **"解决方案**"。

    3. 在窗口的中心部分选择 **"获取开始Lib"，** 然后选择 **"确定**"。

       此操作使**入门项目**中定义的类型可供**入门主机项目使用**。

3. 在**入门主机**项目中向<xref:System.ServiceModel>程序集添加引用：

    1. 在 **"解决方案资源管理器"** 窗口中，选择 **"入门主机**"项目下的 **"参考"** 文件夹，然后从快捷菜单中选择 **"添加引用**"。

    2. 在"**添加引用**"窗口中，在窗口左侧的 **"程序集**"下，选择 **"框架**"。

    3. 选择 **"系统.服务模式"，** 然后选择 **"确定**"。

    4. 通过选择 **"全部保存文件** > **"保存**解决方案。

## <a name="add-code-to-host-the-service"></a>添加代码以承载服务

要托管服务，请添加代码以执行以下步骤：

1. 为基本地址创建 URI。
2. 创建用于托管服务的类实例。
3. 创建服务终结点。
4. 启用元数据交换。
5. 打开服务主机以侦听传入消息。
  
对代码进行以下更改：

1. 打开**入门霍斯特**项目中**的Program.cs**或**Module1.vb**文件，并将其代码替换为以下代码：

    ```csharp
    using System;
    using System.ServiceModel;
    using System.ServiceModel.Description;
    using GettingStartedLib;

    namespace GettingStartedHost
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Step 1: Create a URI to serve as the base address.
                Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

                // Step 2: Create a ServiceHost instance.
                ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

                try
                {
                    // Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                    // Step 4: Enable metadata exchange.
                    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                    smb.HttpGetEnabled = true;
                    selfHost.Description.Behaviors.Add(smb)    ;

                    // Step 5: Start the service.
                    selfHost.Open();
                    Console.WriteLine("The service is ready.");

                    // Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.");
                    Console.WriteLine();
                    Console.ReadLine();
                    selfHost.Close();
                }
                catch (CommunicationException ce)
                {
                    Console.WriteLine("An exception occurred: {0}", ce.Message);
                    selfHost.Abort();
                }
            }
        }
    }
    ```

    ```vb
    Imports System.ServiceModel
    Imports System.ServiceModel.Description
    Imports GettingStartedLib.GettingStartedLib

    Module Service

        Class Program
            Shared Sub Main()
                ' Step 1: Create a URI to serve as the base address.
                Dim baseAddress As New Uri("http://localhost:8000/GettingStarted/")

                ' Step 2: Create a ServiceHost instance.
                Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
               Try

                    ' Step 3: Add a service endpoint.
                    selfHost.AddServiceEndpoint( _
                        GetType(ICalculator), _
                        New WSHttpBinding(), _
                        "CalculatorService")

                    ' Step 4: Enable metadata exchange.
                    Dim smb As New ServiceMetadataBehavior()
                    smb.HttpGetEnabled = True
                    selfHost.Description.Behaviors.Add(smb)

                    ' Step 5: Start the service.
                    selfHost.Open()
                    Console.WriteLine("The service is ready.")

                    ' Close the ServiceHost to stop the service.
                    Console.WriteLine("Press <Enter> to terminate the service.")
                    Console.WriteLine()
                    Console.ReadLine()
                    selfHost.Close()

                Catch ce As CommunicationException
                    Console.WriteLine("An exception occurred: {0}", ce.Message)
                    selfHost.Abort()
                End Try
            End Sub
        End Class

    End Module
    ```

    有关此代码的工作原理的信息，请参阅[服务托管程序步骤](#service-hosting-program-steps)。

2. 更新项目属性：

   1. 在 **"解决方案资源管理器"** 窗口中，选择 **"入门主机"** 文件夹，然后从快捷菜单中选择 **"属性**"。

   2. 在 **"入门主机"** 属性页上，选择"**应用程序**"选项卡：

      - 对于 C# 项目，从**启动对象**列表中选择 **"入门主机.程序"。**

      - 对于可视化基本项目，从**启动对象**列表中选择 **"服务.程序**"。

   3. 在 **"文件"** 菜单中，选择 **"全部保存**"。

## <a name="verify-the-service-is-working"></a>验证服务是否正常工作

1. 构建解决方案，然后从 Visual Studio 内部运行**入门主机**控制台应用程序。

    服务必须具有管理员权限运行。 由于您使用管理员权限打开了 Visual Studio，因此在可视化工作室中运行 **"入门主机"** 时，应用程序也具有管理员权限运行。 作为替代方法，您可以以管理员身份打开新的命令提示符（从快捷菜单中选择 **"以管理员身份运行"），** > **Run as administrator**并在其中运行 **"获取启动Host.exe"。**

2. 打开 Web 浏览器，然后浏览到 服务页面`http://localhost:8000/GettingStarted/CalculatorService`。

   > [!NOTE]
   > 此类服务需要适当的权限才能在计算机上注册 HTTP 地址以进行侦听。 管理员帐户具有此权限，但对于非管理员帐户来说，必须授予对 HTTP 命名空间的权限。 有关如何配置命名空间预留的详细信息，请参阅[配置 HTTP 和 HTTPS](feature-details/configuring-http-and-https.md)。

## <a name="service-hosting-program-steps"></a>服务托管程序步骤

添加到托管服务的代码中的步骤描述如下：

- **步骤 1：** 创建类的`Uri`实例以保存服务的基本地址。 包含基本地址的 URL 具有标识服务的可选 URI。 基本地址的格式如下： `<transport>://<machine-name or domain><:optional port #>/<optional URI segment>`。 计算器服务的基本地址使用 HTTP 传输、本地主机、端口 8000 和 URI 段"入门"。

- **步骤 2：** 创建类的<xref:System.ServiceModel.ServiceHost>实例，用于托管服务。 构造函数采用两个参数：实现服务协定的类类型和服务的基本地址。

- **步骤 3**：<xref:System.ServiceModel.Description.ServiceEndpoint>创建实例。 服务终结点由地址、绑定和服务协定组成。 <xref:System.ServiceModel.Description.ServiceEndpoint>构造函数由服务协定接口类型、绑定和地址组成。 服务协定是在服务类型中定义和实现的 `ICalculator`。 此示例的绑定是<xref:System.ServiceModel.WSHttpBinding>，这是一个内置绑定，并连接到符合 WS-* 规范的终结点。 有关 WCF 绑定的详细信息，请参阅[WCF 绑定概述](bindings-overview.md)。 将地址追加到基本地址以标识终结点。 代码将地址指定为计算器服务，终结点的完全限定地址为`http://localhost:8000/GettingStarted/CalculatorService`。

    > [!IMPORTANT]
    > 对于 .NET 框架版本 4 及更高版本，添加服务终结点是可选的。 对于这些版本，如果不添加代码或配置，WCF 会为服务实现的每个基本地址和协定组合添加一个默认终结点。 有关默认终结点的详细信息，请参阅[指定终结点地址](specifying-an-endpoint-address.md)。 有关默认终结点、绑定和行为的详细信息，请参阅[WCF 服务的](samples/simplified-configuration-for-wcf-services.md)[简化配置](simplified-configuration.md)和简化配置。

- **步骤 4**：启用元数据交换。 客户端使用元数据交换生成用于调用服务操作的代理。 要启用元数据交换，请创建<xref:System.ServiceModel.Description.ServiceMetadataBehavior>实例，将其<xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled>属性设置为`true`，并将`ServiceMetadataBehavior`对象添加到<xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A><xref:System.ServiceModel.ServiceHost>实例的集合中。

- **步骤 5** <xref:System.ServiceModel.ServiceHost> ： 打开以侦听传入的消息。 应用程序等待您按**Enter**。 应用程序实例化后<xref:System.ServiceModel.ServiceHost>，它执行一个 try/catch 块。 有关安全捕获引发<xref:System.ServiceModel.ServiceHost>异常的详细信息，请参阅[使用关闭和中止来释放 WCF 客户端资源](samples/use-close-abort-release-wcf-client-resources.md)。

> [!IMPORTANT]
> 添加 WCF 服务库时，如果通过启动服务主机来调试它，Visual Studio 会为您托管它。 为了避免冲突，您可以阻止 Visual Studio 托管 WCF 服务库。
>
> 1. 在**解决方案资源管理器**中选择**入门项目**，然后从快捷菜单中选择 **"属性**"。
> 2. 在同**一解决方案中调试另一个项目时**，选择**WCF 选项**并取消选中"启动 WCF 服务主机"。

## <a name="next-steps"></a>后续步骤

在本教程中，你了解了如何执行以下操作：
> [!div class="checklist"]
>
> - 创建和配置用于托管 WCF 服务的控制台应用项目。
> - 添加代码以承载 WCF 服务。
> - 更新配置文件。
> - 启动 WCF 服务并验证其正在运行。

进入下一个教程，了解如何创建 WCF 客户端。

> [!div class="nextstepaction"]
> [教程：创建 WCF 客户端](how-to-create-a-wcf-client.md)
