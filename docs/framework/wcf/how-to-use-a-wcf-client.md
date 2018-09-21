---
title: 如何：使用 Windows Communication Foundation 客户端
ms.date: 09/14/2018
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: 12e911fb899cb85121c129b762828cdda01e64f1
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46532579"
---
# <a name="how-to-use-a-windows-communication-foundation-client"></a>如何：使用 Windows Communication Foundation 客户端

这是创建基本 Windows Communication Foundation (WCF) 应用程序所需的六项任务的最后一个。 有关全部六项任务的概述，请参阅[入门教程](../../../docs/framework/wcf/getting-started-tutorial.md)主题。

一旦创建并配置 Windows Communication Foundation (WCF) 代理，可以创建一个客户端实例和可以编译客户端应用程序，并将其用于与 WCF 服务进行通信。 本主题介绍用于实例化和使用 WCF 客户端的过程。 此过程执行三项操作：

1.  实例化 WCF 客户端。

2.  从生成的代理调用服务操作。

3.  在完成操作调用后关闭客户端。

## <a name="use-a-windows-communication-foundation-client"></a>使用 Windows Communication Foundation 客户端

打开 GettingStartedClient 项目中的 Program.cs 或 program.vb 文件，然后将现有代码替换为以下代码：

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using GettingStartedClient.ServiceReference1;

namespace GettingStartedClient
{
    class Program
    {
        static void Main(string[] args)
        {
            //Step 1: Create an instance of the WCF proxy.
            CalculatorClient client = new CalculatorClient();

            // Step 2: Call the service operations.
            // Call the Add service operation.
            double value1 = 100.00D;
            double value2 = 15.99D;
            double result = client.Add(value1, value2);
            Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

            // Call the Subtract service operation.
            value1 = 145.00D;
            value2 = 76.54D;
            result = client.Subtract(value1, value2);
            Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

            // Call the Multiply service operation.
            value1 = 9.00D;
            value2 = 81.25D;
            result = client.Multiply(value1, value2);
            Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

            // Call the Divide service operation.
            value1 = 22.00D;
            value2 = 7.00D;
            result = client.Divide(value1, value2);
            Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);

            //Step 3: Closing the client gracefully closes the connection and cleans up resources.
            client.Close();
        }
    }
}
```

```vb
Imports System
Imports System.Collections.Generic
Imports System.Text
Imports System.ServiceModel
Imports GettingStartedClientVB2.ServiceReference1

Module Module1

    Sub Main()
        ' Step 1: Create an instance of the WCF proxy
        Dim Client As New CalculatorClient()

        'Step 2: Call the service operations.
        'Call the Add service operation.
        Dim value1 As Double = 100D
        Dim value2 As Double = 15.99D
        Dim result As Double = Client.Add(value1, value2)
        Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

        'Call the Subtract service operation.
        value1 = 145D
        value2 = 76.54D
        result = Client.Subtract(value1, value2)
        Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

        'Call the Multiply service operation.
        value1 = 9D
        value2 = 81.25D
        result = Client.Multiply(value1, value2)
        Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

        'Call the Divide service operation.
        value1 = 22D
        value2 = 7D
        result = Client.Divide(value1, value2)
        Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

        ' Step 3: Closing the client gracefully closes the connection and cleans up resources.
        Client.Close()

        Console.WriteLine()
        Console.WriteLine("Press <ENTER> to terminate client.")
        Console.ReadLine()

    End Sub

End Module
```

请注意`using`或`Imports`导入语句`GettingStartedClient.ServiceReference1`。 这将生成的代码导入**添加服务引用**Visual Studio 中。 该代码实例化 WCF 代理然后调用由计算器服务公开的服务操作的每个，关闭代理，并终止。

现在，您已经完成了教程。 您定义了服务协定、实现了服务协定、生成了 WCF 代理、配置了 WCF 客户端应用程序，然后使用代理调用了服务操作。 若要测试应用程序，首先运行 GettingStartedHost 以启动服务，然后运行 GettingStartedClient。

GettingStartedHost 的输出应类似于：

```text
The service is ready.Press <ENTER> to terminate service.Received Add(100,15.99)Return: 115.99Received Subtract(145,76.54)Return: 68.46Received Multiply(9,81.25)Return: 731.25Received Divide(22,7)Return: 3.14285714285714
```

GettingStartedClient 的输出应类似于：

```text
Add(100,15.99) = 115.99Subtract(145,76.54) = 68.46Multiply(9,81.25) = 731.25Divide(22,7) = 3.14285714285714Press <ENTER> to terminate client.
```

## <a name="see-also"></a>请参阅

- [生成客户端](../../../docs/framework/wcf/building-clients.md)
- [如何：创建客户端](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [入门教程](../../../docs/framework/wcf/getting-started-tutorial.md)
- [基本 WCF 编程](../../../docs/framework/wcf/basic-wcf-programming.md)
- [如何：创建双工协定](../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
- [如何：使用双工协定访问服务](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)
- [入门](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [自承载](../../../docs/framework/wcf/samples/self-host.md)