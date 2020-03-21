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
# <a name="tutorial-use-a-windows-communication-foundation-client"></a><span data-ttu-id="ae576-102">教程：使用 Windows 通信基础客户端</span><span class="sxs-lookup"><span data-stu-id="ae576-102">Tutorial: Use a Windows Communication Foundation client</span></span>

<span data-ttu-id="ae576-103">本教程介绍创建基本 Windows 通信基础 （WCF） 应用程序所需的五个任务中的最后一个任务。</span><span class="sxs-lookup"><span data-stu-id="ae576-103">This tutorial describes the last of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="ae576-104">有关教程的概述，请参阅[教程：开始使用 Windows 通信基础应用程序](getting-started-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="ae576-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="ae576-105">创建并配置 Windows 通信基础 （WCF） 代理后，将创建客户端实例并编译客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="ae576-105">After you've created and configured a Windows Communication Foundation (WCF) proxy, you create a client instance and compile the client application.</span></span> <span data-ttu-id="ae576-106">然后，使用它与 WCF 服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="ae576-106">You then use it to communicate with the WCF service.</span></span>

<span data-ttu-id="ae576-107">在本教程中，你将了解如何执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ae576-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="ae576-108">添加代码以使用 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="ae576-108">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="ae576-109">测试 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="ae576-109">Test the WCF client.</span></span>

## <a name="add-code-to-use-the-wcf-client"></a><span data-ttu-id="ae576-110">添加代码以使用 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="ae576-110">Add code to use the WCF client</span></span>

<span data-ttu-id="ae576-111">客户端代码执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ae576-111">The client code does the following steps:</span></span>

- <span data-ttu-id="ae576-112">实例化 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="ae576-112">Instantiates the WCF client.</span></span>
- <span data-ttu-id="ae576-113">从生成的代理调用服务操作。</span><span class="sxs-lookup"><span data-stu-id="ae576-113">Calls the service operations from the generated proxy.</span></span>
- <span data-ttu-id="ae576-114">操作调用完成后关闭客户端。</span><span class="sxs-lookup"><span data-stu-id="ae576-114">Closes the client after the operation call is completed.</span></span>

<span data-ttu-id="ae576-115">从**入门客户端**项目中打开**Program.cs**或**Module1.vb**文件，并将其代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="ae576-115">Open the **Program.cs** or **Module1.vb** file from the **GettingStartedClient** project and replace its code with the following code:</span></span>

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

<span data-ttu-id="ae576-116">请注意导入`using``GettingStartedClient.ServiceReference1`的 （用于视觉`Imports`C#） 或 （用于可视基本）语句。</span><span class="sxs-lookup"><span data-stu-id="ae576-116">Notice the `using` (for Visual C#) or `Imports` (for Visual Basic) statement that imports `GettingStartedClient.ServiceReference1`.</span></span> <span data-ttu-id="ae576-117">此语句导入 Visual Studio 使用**添加服务引用**函数生成的代码。</span><span class="sxs-lookup"><span data-stu-id="ae576-117">This statement imports the code that Visual Studio generated with the **Add Service Reference** function.</span></span> <span data-ttu-id="ae576-118">代码实例化 WCF 代理并调用计算器服务公开的每个服务操作。</span><span class="sxs-lookup"><span data-stu-id="ae576-118">The code instantiates the WCF proxy and calls each of the service operations that the calculator service exposes.</span></span> <span data-ttu-id="ae576-119">然后关闭代理并结束程序。</span><span class="sxs-lookup"><span data-stu-id="ae576-119">It then closes the proxy and ends the program.</span></span>

## <a name="test-the-wcf-client"></a><span data-ttu-id="ae576-120">测试 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="ae576-120">Test the WCF client</span></span>

### <a name="test-the-application-from-visual-studio"></a><span data-ttu-id="ae576-121">从可视化工作室测试应用程序</span><span class="sxs-lookup"><span data-stu-id="ae576-121">Test the application from Visual Studio</span></span>

1. <span data-ttu-id="ae576-122">保存并生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="ae576-122">Save and build the solution.</span></span>

2. <span data-ttu-id="ae576-123">选择 **"入门项目"** 文件夹，然后从快捷菜单中选择 **"设置为启动项目**"。</span><span class="sxs-lookup"><span data-stu-id="ae576-123">Select the **GettingStartedLib** folder, and then select **Set as Startup Project** from the shortcut menu.</span></span>

3. <span data-ttu-id="ae576-124">从**启动项目**，从下拉列表中选择 **"入门Lib"，** 然后选择 **"运行"** 或按**F5**。</span><span class="sxs-lookup"><span data-stu-id="ae576-124">From **Startup Projects**, select **GettingStartedLib** from the drop-down list, then select **Run** or press **F5**.</span></span>

### <a name="test-the-application-from-a-command-prompt"></a><span data-ttu-id="ae576-125">从命令提示符测试应用程序</span><span class="sxs-lookup"><span data-stu-id="ae576-125">Test the application from a command prompt</span></span>

1. <span data-ttu-id="ae576-126">以管理员身份打开命令提示，然后导航到可视化工作室解决方案目录。</span><span class="sxs-lookup"><span data-stu-id="ae576-126">Open a command prompt as an administrator, and then navigate to your Visual Studio solution directory.</span></span>

2. <span data-ttu-id="ae576-127">要启动服务：输入*入门主机\bin\调试\入门Host.exe。*</span><span class="sxs-lookup"><span data-stu-id="ae576-127">To start the service: Enter *GettingStartedHost\bin\Debug\GettingStartedHost.exe*.</span></span>

3. <span data-ttu-id="ae576-128">要启动客户端：打开另一个命令提示符，导航到可视化工作室解决方案目录，然后输入*入门客户端\bin_Debug_获取启动客户端.exe。*</span><span class="sxs-lookup"><span data-stu-id="ae576-128">To start the client: Open another command prompt, navigate to your Visual Studio solution directory, then enter *GettingStartedClient\bin\Debug\GettingStartedClient.exe*.</span></span>

   <span data-ttu-id="ae576-129">*入门Host.exe*生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="ae576-129">*GettingStartedHost.exe* produces the following output:</span></span>

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

   <span data-ttu-id="ae576-130">*入门客户端.exe*生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="ae576-130">*GettingStartedClient.exe* produces the following output:</span></span>

   ```text
   Add(100,15.99) = 115.99
   Subtract(145,76.54) = 68.46
   Multiply(9,81.25) = 731.25
   Divide(22,7) = 3.14285714285714

   Press <Enter> to terminate the client.
   ```

## <a name="next-steps"></a><span data-ttu-id="ae576-131">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ae576-131">Next steps</span></span>

<span data-ttu-id="ae576-132">现在，您已经完成了 WCF 入门教程中的所有任务。</span><span class="sxs-lookup"><span data-stu-id="ae576-132">You've now completed all the tasks in the WCF get started tutorial.</span></span> <span data-ttu-id="ae576-133">在本教程中，你了解了如何执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ae576-133">In this tutorial, you learned how to:</span></span>

<span data-ttu-id="ae576-134">在本教程中，你将了解如何执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ae576-134">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="ae576-135">添加代码以使用 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="ae576-135">Add code to use the WCF client.</span></span>
> - <span data-ttu-id="ae576-136">测试 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="ae576-136">Test the WCF client.</span></span>

<span data-ttu-id="ae576-137">如果任一步骤中存在问题或错误，请按照疑难解答文章中的步骤进行修复。</span><span class="sxs-lookup"><span data-stu-id="ae576-137">If you have problems or errors in any of the steps, follow the steps in the troubleshooting article to fix them.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="ae576-138">使用 WCF 教程对入门进行故障排除</span><span class="sxs-lookup"><span data-stu-id="ae576-138">Troubleshoot the Get started with WCF tutorials</span></span>](troubleshooting-the-getting-started-tutorial.md)
