---
title: 如何托管并运行基本的 Windows Communication Foundation 服务
ms.date: 09/14/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF services [WCF]
- WCF services [WCF], running
ms.assetid: 31774d36-923b-4e2d-812e-aa190127266f
ms.openlocfilehash: 73633c2c6119204f2fb608b32ae794a2e07b27d0
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "56747069"
---
# <a name="how-to-host-and-run-a-basic-windows-communication-foundation-service"></a>如何托管并运行基本的 Windows Communication Foundation 服务

这是创建 Windows Communication Foundation (WCF) 应用程序所需六项任务中的第三项。 有关全部六项任务的概述，请参阅[入门教程](getting-started-tutorial.md)主题。

本主题说明如何在控制台应用程序中承载 Windows Communication Foundation (WCF) 服务。 此过程包含以下步骤：

- 创建用于承载服务的控制台应用程序项目。

- 为服务创建服务主机。

- 启用元数据交换。

- 打开服务主机。

在过程后面的以下示例中提供了在此任务中编写的代码的完整清单。

## <a name="create-a-new-console-application-to-host-the-service"></a>创建新的控制台应用程序以承载服务

1. 通过右键单击入门解决方案并选择 Visual Studio 中创建新的控制台应用程序项目**外** > **新项目**。 在**添加新项目**对话框中的，在左侧，选择**Windows Desktop**类别中的下**Visual C#** 或者**Visual Basic**。 选择**控制台应用 (.NET Framework)** 模板，然后命名项目**GettingStartedHost**。

2. 将对 GettingStartedLib 项目的引用添加到 GettingStartedHost 项目。 右键单击**引用**文件夹中的 GettingStartedHost 项目下**解决方案资源管理器**，然后选择**添加引用**。 在中**添加引用**对话框中，选择**解决方案**在对话框的左侧，在对话框的中心部分选择 GettingStartedLib，然后选择**添加**。 这使 GettingStartedLib 项目中定义的类型可用于 GettingStartedHost 项目。

3. 将对 System.ServiceModel 的引用添加到 GettingStartedHost 项目。 右键单击**引用**文件夹中的 GettingStartedHost 项目下**解决方案资源管理器**，然后选择**添加引用**。 在中**添加引用**对话框中，选择**Framework**下的对话框左侧**程序集**。 找到并选择**System.ServiceModel**，然后选择**确定**。 通过选择保存解决方案**文件** > **全部保存**。

## <a name="host-the-service"></a>托管服务

打开 Program.cs 或 Module.vb 文件，并输入以下代码：

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
            // Step 1 Create a URI to serve as the base address.
            Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

            // Step 2 Create a ServiceHost instance
            ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

            try
            {
                // Step 3 Add a service endpoint.
                selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                // Step 4 Enable metadata exchange.
                ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                smb.HttpGetEnabled = true;
                selfHost.Description.Behaviors.Add(smb);

                // Step 5 Start the service.
                selfHost.Open();
                Console.WriteLine("The service is ready.");
                Console.WriteLine("Press <ENTER> to terminate service.");
                Console.WriteLine();
                Console.ReadLine();

                // Close the ServiceHostBase to shutdown the service.
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
Imports GettingStartedLibVB.GettingStartedLib

Module Service

    Class Program
        Shared Sub Main()
            ' Step 1 Create a URI to serve as the base address
            Dim baseAddress As New Uri("http://localhost:8000/GettingStarted")

            ' Step 2 Create a ServiceHost instance
            Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
           Try

                ' Step 3 Add a service endpoint
                ' Add a service endpoint
                selfHost.AddServiceEndpoint( _
                    GetType(ICalculator), _
                    New WSHttpBinding(), _
                    "CalculatorService")

                ' Step 4 Enable metadata exchange.
                Dim smb As New ServiceMetadataBehavior()
                smb.HttpGetEnabled = True
                selfHost.Description.Behaviors.Add(smb)

                ' Step 5 Start the service
                selfHost.Open()
                Console.WriteLine("The service is ready.")
                Console.WriteLine("Press <ENTER> to terminate service.")
                Console.WriteLine()
                Console.ReadLine()

                ' Close the ServiceHostBase to shutdown the service.
                selfHost.Close()
            Catch ce As CommunicationException
                Console.WriteLine("An exception occurred: {0}", ce.Message)
                selfHost.Abort()
            End Try
        End Sub
    End Class

End Module
```

**步骤 1** -创建要保存服务的基址的 Uri 类的实例。 服务由包含一个基址和一个可选 URI 的 URL 来标识。 基址的格式如下：[传输协议]://[计算机名或域][:可选端口号]/[可选 URI 段]。计算器服务的基址使用 HTTP 传输协议、本地主机、端口 8000 和 URI 段“GettingStarted”

**步骤 2** – 创建的实例<xref:System.ServiceModel.ServiceHost>类以承载服务。 构造函数采用两个参数：实现服务协定的类的类型，以及服务的基址。

**步骤 3** – 创建<xref:System.ServiceModel.Description.ServiceEndpoint>实例。 服务终结点由地址、绑定和服务协定组成。 因此<xref:System.ServiceModel.Description.ServiceEndpoint> 构造函数采用服务协定接口类型、绑定和地址。 服务协定是在服务类型中定义和实现的 `ICalculator`。 在此示例中使用的绑定是 <xref:System.ServiceModel.WSHttpBinding>，这是用于连接到符合 WS-＊ 规范的终结点的内置绑定。 有关 WCF 绑定的详细信息，请参阅 [WCF 绑定概述](bindings-overview.md)。 该地址追加到基址以标识终结点。 在此代码中指定的地址为"CalculatorService"，因此终结点的完全限定的地址是`"http://localhost:8000/GettingStarted/CalculatorService"`。

> [!IMPORTANT]
> 使用 .NET Framework 4 或更高版本时，添加服务终结点是可选的。 在这些版本中，如果在代码或配置中未添加任何终结点，则 WCF 为该服务实现的基址和协定的每个组合添加一个默认终结点。 有关默认终结点的详细信息，请参阅[指定终结点地址](specifying-an-endpoint-address.md)。 有关默认终结点、绑定和行为的详细信息，请参阅[简化配置](simplified-configuration.md)和 [WCF 服务的简化配置](./samples/simplified-configuration-for-wcf-services.md)。

**步骤 4** -启用元数据交换。 客户端将使用元数据交换来生成将用于调用服务操作的代理。 要启用元数据交换，请创建 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 实例，将其 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> 属性设置为 `true`，并将行为添加到 <xref:System.ServiceModel.Description.ServiceDescription.Behaviors%2A> 实例的 <xref:System.ServiceModel.ServiceHost> 集合。

**步骤 5** – 打开<xref:System.ServiceModel.ServiceHost>侦听传入消息。 注意，代码会等待用户按 Enter。 如果不这样做，应用程序将立即关闭，并且服务将关闭。另请注意，使用了 try/catch 块。 在实例化 <xref:System.ServiceModel.ServiceHost> 后，所有其他代码放置在 try/catch 块中。 有关安全捕获引发的异常详细信息<xref:System.ServiceModel.ServiceHost>，请参阅[使用关闭和中止发布 WCF 客户端资源](samples/use-close-abort-release-wcf-client-resources.md)

> [!IMPORTANT]
> 当添加 WCF 服务库时，Visual Studio 可以承载它为您调试通过启动服务主机时。 若要避免冲突可以禁用此。 
> 1. 打开 GettingStartedLib 项目属性。
> 2. 转到**WCF 选项**并取消选中**启动 WCF 服务主机时调试**。

## <a name="verify-the-service-is-working"></a>验证服务正常工作

1. 运行 GettingStartedHost 控制台应用程序从 Visual Studio 内部。

   必须使用管理员特权运行服务。 使用管理员特权打开 Visual Studio，因为 GettingStartedHost 也是使用管理员特权运行。 此外可以打开新命令提示符处使用**以管理员身份运行**并运行 service.exe。

2. 打开 web 浏览器并浏览到服务的调试页在`http://localhost:8000/GettingStarted/`。 **请注意 ！结束斜杠很重要。**

## <a name="example"></a>示例

下面的示例包括本教程中前面步骤的服务协定和实现，并将服务承载于控制台应用程序中。

若要此命令行编译器进行编译，编译 IService1.cs 和 Service1.cs 到引用的类库`System.ServiceModel.dll`。 将 Program.cs 编译为一个控制台应用程序。

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
        [ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
        public interface ICalculator
        {
            [OperationContract]
            double Add(double n1, double n2);
            [OperationContract]
            double Subtract(double n1, double n2);
            [OperationContract]
            double Multiply(double n1, double n2);
            [OperationContract]
            double Divide(double n1, double n2);
        }
}
```

```csharp
using System;
using System.ServiceModel;

namespace GettingStartedLib
{
    public class CalculatorService : ICalculator
    {
        public double Add(double n1, double n2)
        {
            double result = n1 + n2;
            Console.WriteLine("Received Add({0},{1})", n1, n2);
            // Code added to write output to the console window.
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Subtract(double n1, double n2)
        {
            double result = n1 - n2;
            Console.WriteLine("Received Subtract({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Multiply(double n1, double n2)
        {
            double result = n1 * n2;
            Console.WriteLine("Received Multiply({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }

        public double Divide(double n1, double n2)
        {
            double result = n1 / n2;
            Console.WriteLine("Received Divide({0},{1})", n1, n2);
            Console.WriteLine("Return: {0}", result);
            return result;
        }
    }
}
```

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
            // Step 1 of the address configuration procedure: Create a URI to serve as the base address.
            Uri baseAddress = new Uri("http://localhost:8000/GettingStarted/");

            // Step 2 of the hosting procedure: Create ServiceHost
            ServiceHost selfHost = new ServiceHost(typeof(CalculatorService), baseAddress);

            try
            {
                // Step 3 of the hosting procedure: Add a service endpoint.
                selfHost.AddServiceEndpoint(typeof(ICalculator), new WSHttpBinding(), "CalculatorService");

                // Step 4 of the hosting procedure: Enable metadata exchange.
                ServiceMetadataBehavior smb = new ServiceMetadataBehavior();
                smb.HttpGetEnabled = true;
                selfHost.Description.Behaviors.Add(smb);

                // Step 5 of the hosting procedure: Start (and then stop) the service.
                selfHost.Open();
                Console.WriteLine("The service is ready.");
                Console.WriteLine("Press <ENTER> to terminate service.");
                Console.WriteLine();
                Console.ReadLine();

                // Close the ServiceHostBase to shutdown the service.
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

Namespace GettingStartedLib

    <ServiceContract(Namespace:="http://Microsoft.ServiceModel.Samples")> _
    Public Interface ICalculator

        <OperationContract()> _
        Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double
        <OperationContract()> _
        Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double
    End Interface
End Namespace
```

```vb
Imports System.ServiceModel

Namespace GettingStartedLib

    Public Class CalculatorService
        Implements ICalculator

        Public Function Add(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Add
            Dim result As Double = n1 + n2
            ' Code added to write output to the console window.
            Console.WriteLine("Received Add({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result
        End Function

        Public Function Subtract(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Subtract
            Dim result As Double = n1 - n2
            Console.WriteLine("Received Subtract({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Multiply(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Multiply
            Dim result As Double = n1 * n2
            Console.WriteLine("Received Multiply({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function

        Public Function Divide(ByVal n1 As Double, ByVal n2 As Double) As Double Implements ICalculator.Divide
            Dim result As Double = n1 / n2
            Console.WriteLine("Received Divide({0},{1})", n1, n2)
            Console.WriteLine("Return: {0}", result)
            Return result

        End Function
    End Class
End Namespace
```

```vb
Imports System.ServiceModel
Imports System.ServiceModel.Description
Imports GettingStartedLibVB.GettingStartedLib

Module Service

    Class Program
        Shared Sub Main()
            ' Step 1 of the address configuration procedure: Create a URI to serve as the base address.
            Dim baseAddress As New Uri("http://localhost:8000/GettingStarted/")

            ' Step 2 of the hosting procedure: Create ServiceHost
            Dim selfHost As New ServiceHost(GetType(CalculatorService), baseAddress)
            Try

                ' Step 3 of the hosting procedure: Add a service endpoint.
                ' Add a service endpoint
                selfHost.AddServiceEndpoint( _
                    GetType(ICalculator), _
                    New WSHttpBinding(), _
                    "CalculatorService")

                ' Step 4 of the hosting procedure: Enable metadata exchange.
                ' Enable metadata exchange
                Dim smb As New ServiceMetadataBehavior()
                smb.HttpGetEnabled = True
                selfHost.Description.Behaviors.Add(smb)

                ' Step 5 of the hosting procedure: Start (and then stop) the service.
                selfHost.Open()
                Console.WriteLine("The service is ready.")
                Console.WriteLine("Press <ENTER> to terminate service.")
                Console.WriteLine()
                Console.ReadLine()

                ' Close the ServiceHostBase to shutdown the service.
                selfHost.Close()
            Catch ce As CommunicationException
                Console.WriteLine("An exception occurred: {0}", ce.Message)
                selfHost.Abort()
            End Try
        End Sub
    End Class

End Module
```

> [!NOTE]
> 此类服务需要在计算机上注册 HTTP 地址以进行侦听的权限。 管理员帐户具有此权限，但对于非管理员帐户来说，必须授予对 HTTP 命名空间的权限。 有关如何配置命名空间预留的详细信息，请参阅[配置 HTTP 和 HTTPS](feature-details/configuring-http-and-https.md)。 在 Visual Studio 下运行时，必须使用管理员特权运行 service.exe。

## <a name="next-steps"></a>后续步骤

此时服务正在运行。 在下一个任务中，将创建 WCF 客户端。

> [!div class="nextstepaction"]
> [如何：创建 WCF 客户端](how-to-create-a-wcf-client.md)

有关疑难解答的信息，请参阅[疑难解答入门教程](troubleshooting-the-getting-started-tutorial.md)。

## <a name="see-also"></a>请参阅

- [入门](samples/getting-started-sample.md)
- [自承载](samples/self-host.md)
- [托管服务](hosting-services.md)
