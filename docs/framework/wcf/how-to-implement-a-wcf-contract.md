---
title: 教程：实现 Windows Communication Foundation 服务协定
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: 05923dc0a2223da5e5fcda483abc1ee1dd2d643f
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928711"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="d2d39-102">教程：实现 Windows Communication Foundation 服务协定</span><span class="sxs-lookup"><span data-stu-id="d2d39-102">Tutorial: Implement a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="d2d39-103">本教程介绍创建基本 Windows Communication Foundation （WCF）应用程序所需的五个任务中的第二个。</span><span class="sxs-lookup"><span data-stu-id="d2d39-103">This tutorial describes the second of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="d2d39-104">有关教程的概述，请参阅[教程：开始 Windows Communication Foundation 应用程序](getting-started-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="d2d39-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="d2d39-105">创建 WCF 应用程序的下一步是添加代码以实现在上一步中创建的 WCF 服务接口。</span><span class="sxs-lookup"><span data-stu-id="d2d39-105">The next step for creating a WCF application is to add code to implement the WCF service interface that you created in the previous step.</span></span> <span data-ttu-id="d2d39-106">在此步骤中，你将创建一个`CalculatorService`名为的类，用于`ICalculator`实现用户定义的接口。</span><span class="sxs-lookup"><span data-stu-id="d2d39-106">In this step, you create a class named `CalculatorService` that implements the user-defined `ICalculator` interface.</span></span> <span data-ttu-id="d2d39-107">下面代码中的每个方法都调用计算器操作，并将文本写入控制台以对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="d2d39-107">Each method in the following code calls a calculator operation and writes text to the console to test it.</span></span> 

<span data-ttu-id="d2d39-108">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="d2d39-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="d2d39-109">添加代码以实现 WCF 服务协定。</span><span class="sxs-lookup"><span data-stu-id="d2d39-109">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="d2d39-110">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="d2d39-110">Build the solution.</span></span>

## <a name="add-code-to-implement-the-wcf-service-contract"></a><span data-ttu-id="d2d39-111">添加代码以实现 WCF 服务协定</span><span class="sxs-lookup"><span data-stu-id="d2d39-111">Add code to implement the WCF service contract</span></span>

<span data-ttu-id="d2d39-112">在**GettingStartedLib**中，打开**Service1.cs**或**Service1**文件，并将其代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="d2d39-112">In **GettingStartedLib**, open the **Service1.cs** or **Service1.vb** file and replace its code with the following code:</span></span>

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

## <a name="edit-appconfig"></a><span data-ttu-id="d2d39-113">编辑 App.config</span><span class="sxs-lookup"><span data-stu-id="d2d39-113">Edit App.config</span></span>

<span data-ttu-id="d2d39-114">在**GettingStartedLib**中编辑**app.config** ，以反映对代码所做的更改。</span><span class="sxs-lookup"><span data-stu-id="d2d39-114">Edit **App.config** in **GettingStartedLib** to reflect the changes you made to the code.</span></span>

- <span data-ttu-id="d2d39-115">对于 Visual C#项目：</span><span class="sxs-lookup"><span data-stu-id="d2d39-115">For Visual C# projects:</span></span>
  - <span data-ttu-id="d2d39-116">将第14行更改为`<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="d2d39-116">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="d2d39-117">将第17行更改为`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="d2d39-117">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="d2d39-118">将第22行更改为`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="d2d39-118">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>

- <span data-ttu-id="d2d39-119">对于 Visual Basic 项目：</span><span class="sxs-lookup"><span data-stu-id="d2d39-119">For Visual Basic projects:</span></span>
  - <span data-ttu-id="d2d39-120">将第14行更改为`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="d2d39-120">Change line 14 to `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="d2d39-121">将第17行更改为`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="d2d39-121">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="d2d39-122">将第22行更改为`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="d2d39-122">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="d2d39-123">编译代码</span><span class="sxs-lookup"><span data-stu-id="d2d39-123">Compile the code</span></span>

<span data-ttu-id="d2d39-124">生成解决方案以验证是否不存在任何编译错误。</span><span class="sxs-lookup"><span data-stu-id="d2d39-124">Build the solution to verify there aren't any compilation errors.</span></span> <span data-ttu-id="d2d39-125">如果使用的是 Visual Studio，请在 "**生成**" 菜单中选择 "**生成解决方案**" （或按**Ctrl**+**Shift**+**B**）。</span><span class="sxs-lookup"><span data-stu-id="d2d39-125">If you're using Visual Studio, on the **Build** menu select **Build Solution** (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d2d39-126">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d2d39-126">Next steps</span></span>

<span data-ttu-id="d2d39-127">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="d2d39-127">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="d2d39-128">添加代码以实现 WCF 服务协定。</span><span class="sxs-lookup"><span data-stu-id="d2d39-128">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="d2d39-129">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="d2d39-129">Build the solution.</span></span>

<span data-ttu-id="d2d39-130">转到下一教程，了解如何运行 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="d2d39-130">Advance to the next tutorial to learn how to run the WCF service.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d2d39-131">教程：承载和运行基本 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="d2d39-131">Tutorial: Host and run a basic WCF service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)
