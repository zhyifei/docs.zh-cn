---
title: "如何：使用 Windows Communication Foundation 客户端"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF clients [WCF], using
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
caps.latest.revision: "38"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c4b0612cc18129f9f35ed3f475bca8941a20d3ca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-a-windows-communication-foundation-client"></a>如何：使用 Windows Communication Foundation 客户端
这是创建基本 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 应用程序所需的六项任务中的最后一项任务。 有关全部六项任务的概述，请参阅[入门教程](../../../docs/framework/wcf/getting-started-tutorial.md)主题。  
  
 在创建并配置了 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 代理后，就可以创建客户端实例，进而编译客户端应用程序并使用它与 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务进行通信。 本主题描述实例化和使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端的过程。 此过程执行三项操作：  
  
1.  实例化 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 客户端。  
  
2.  从生成的代理调用服务操作。  
  
3.  在完成操作调用后关闭客户端。  
  
### <a name="to-use-a-windows-communication-foundation-client"></a>使用 Windows Communication Foundation 客户端  
  
1.  打开 GettingStartedClient 项目中的 Program.cs 或 program.vb 文件，然后将现有代码替换为以下代码：  
  
    ```  
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
  
    ```  
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
  
     请注意用于导入 GettingStartedClient.ServiceReference1 的 using 或 imports 语句。 这会导入由 Visual Studio 中的“添加服务引用”所生成的代码。 此代码实例化 WCF 代理，然后调用由计算器服务公开的每个服务操作，关闭代理并终止。  
  
 现在，您已经完成了教程。 您定义了服务协定、实现了服务协定、生成了 WCF 代理、配置了 WCF 客户端应用程序，然后使用代理调用了服务操作。 要测试应用程序，首先运行 GettingStartedHost 以启动服务，然后运行 GettingStartedClient。 GettingStartedHost 的输出应类似于：  
  
```Output  
The service is ready.Press <ENTER> to terminate service.Received Add(100,15.99)Return: 115.99Received Subtract(145,76.54)Return: 68.46Received Multiply(9,81.25)Return: 731.25Received Divide(22,7)Return: 3.14285714285714  
```  
  
 GettingStartedClient 的输出应类似于：  
  
```Output  
Add(100,15.99) = 115.99Subtract(145,76.54) = 68.46Multiply(9,81.25) = 731.25Divide(22,7) = 3.14285714285714Press <ENTER> to terminate client.  
```  
  
## <a name="see-also"></a>另请参阅  
 [生成客户端](../../../docs/framework/wcf/building-clients.md)  
 [如何：创建客户端](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [入门教程](../../../docs/framework/wcf/getting-started-tutorial.md)  
 [基本 WCF 编程](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [如何： 创建双工协定](../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)  
 [如何： 使用双工协定访问服务](../../../docs/framework/wcf/feature-details/how-to-access-services-with-a-duplex-contract.md)  
 [入门](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [自承载](../../../docs/framework/wcf/samples/self-host.md)
