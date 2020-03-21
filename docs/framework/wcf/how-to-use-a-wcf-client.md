---
title: 教程：使用 Windows 通信基础客户端
ms.date: 03/19/2019
helpviewer_keywords:
- WCF clients [WCF], using
dev_langs:
- CSharp
- VB
ms.assetid: 190349fc-0573-49c7-bb85-8e316df7f31f
ms.openlocfilehash: d2357c134aef8da204dcdb19d6c1fc93cfdc068c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184010"
---
# <a name="tutorial-use-a-windows-communication-foundation-client"></a>教程：使用 Windows 通信基础客户端

本教程介绍创建基本 Windows 通信基础 （WCF） 应用程序所需的五个任务中的最后一个任务。 有关教程的概述，请参阅[教程：开始使用 Windows 通信基础应用程序](getting-started-tutorial.md)。

创建并配置 Windows 通信基础 （WCF） 代理后，将创建客户端实例并编译客户端应用程序。 然后，使用它与 WCF 服务进行通信。

在本教程中，你将了解如何执行以下操作：
> [!div class="checklist"]
>
> - 添加代码以使用 WCF 客户端。
> - 测试 WCF 客户端。

## <a name="add-code-to-use-the-wcf-client"></a>添加代码以使用 WCF 客户端

客户端代码执行以下步骤：

- 实例化 WCF 客户端。
- 从生成的代理调用服务操作。
- 操作调用完成后关闭客户端。

从**入门客户端**项目中打开**Program.cs**或**Module1.vb**文件，并将其代码替换为以下代码：

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

            // Step 3: Close the client to gracefully close the connection and clean up resources.
            Console.WriteLine("\nPress <Enter> to terminate the client.");
            Console.ReadLine();
            client.Close();
        }
    }
}
```

```vb
Imports System.Collections.Generic
Imports System.Text
Imports System.ServiceModel
Imports GettingStartedClient.ServiceReference1

Module Module1

    Sub Main()
        ' Step 1: Create an instance of the WCF proxy.
        Dim Client As New CalculatorClient()

        ' Step 2: Call the service operations.
        ' Call the Add service operation.
        Dim value1 As Double = 100D
        Dim value2 As Double = 15.99D
        Dim result As Double = Client.Add(value1, value2)
        Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result)

        ' Call the Subtract service operation.
        value1 = 145D
        value2 = 76.54D
        result = Client.Subtract(value1, value2)
        Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result)

        ' Call the Multiply service operation.
        value1 = 9D
        value2 = 81.25D
        result = Client.Multiply(value1, value2)
        Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result)

        ' Call the Divide service operation.
        value1 = 22D
        value2 = 7D
        result = Client.Divide(value1, value2)
        Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result)

        ' Step 3: Close the client to gracefully close the connection and clean up resources.
        Console.WriteLine()
        Console.WriteLine("Press <Enter> to terminate the client.")
        Console.ReadLine()
        Client.Close()

    End Sub

End Module
```

请注意导入`using``GettingStartedClient.ServiceReference1`的 （用于视觉`Imports`C#） 或 （用于可视基本）语句。 此语句导入 Visual Studio 使用**添加服务引用**函数生成的代码。 代码实例化 WCF 代理并调用计算器服务公开的每个服务操作。 然后关闭代理并结束程序。

## <a name="test-the-wcf-client"></a>测试 WCF 客户端

### <a name="test-the-application-from-visual-studio"></a>从可视化工作室测试应用程序

1. 保存并生成解决方案。

2. 选择 **"入门项目"** 文件夹，然后从快捷菜单中选择 **"设置为启动项目**"。

3. 从**启动项目**，从下拉列表中选择 **"入门Lib"，** 然后选择 **"运行"** 或按**F5**。

### <a name="test-the-application-from-a-command-prompt"></a>从命令提示符测试应用程序

1. 以管理员身份打开命令提示，然后导航到可视化工作室解决方案目录。

2. 要启动服务：输入*入门主机\bin\调试\入门Host.exe。*

3. 要启动客户端：打开另一个命令提示符，导航到可视化工作室解决方案目录，然后输入*入门客户端\bin_Debug_获取启动客户端.exe。*

   *入门Host.exe*生成以下输出：

   ```text
   The service is ready.
   Press <Enter> to terminate the service.

   Received Add(100,15.99)
   Return: 115.99
   Received Subtract(145,76.54)
   Return: 68.46
   Received Multiply(9,81.25)
   Return: 731.25
   Received Divide(22,7)
   Return: 3.14285714285714
   ```

   *入门客户端.exe*生成以下输出：

   ```text
   Add(100,15.99) = 115.99
   Subtract(145,76.54) = 68.46
   Multiply(9,81.25) = 731.25
   Divide(22,7) = 3.14285714285714

   Press <Enter> to terminate the client.
   ```

## <a name="next-steps"></a>后续步骤

现在，您已经完成了 WCF 入门教程中的所有任务。 在本教程中，你了解了如何执行以下操作：

在本教程中，你将了解如何执行以下操作：
> [!div class="checklist"]
>
> - 添加代码以使用 WCF 客户端。
> - 测试 WCF 客户端。

如果任一步骤中存在问题或错误，请按照疑难解答文章中的步骤进行修复。

> [!div class="nextstepaction"]
> [使用 WCF 教程对入门进行故障排除](troubleshooting-the-getting-started-tutorial.md)
