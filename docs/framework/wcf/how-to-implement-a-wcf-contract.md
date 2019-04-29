---
title: 教程：实现 Windows Communication Foundation 服务协定
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: fa8c5457c636d7f37215f0d4b4fdbb1c96c9481e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929048"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="6f01d-102">教程：实现 Windows Communication Foundation 服务协定</span><span class="sxs-lookup"><span data-stu-id="6f01d-102">Tutorial: Implement a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="6f01d-103">本教程介绍创建基本 Windows Communication Foundation (WCF) 应用程序所需的五个任务的第二个。</span><span class="sxs-lookup"><span data-stu-id="6f01d-103">This tutorial describes the second of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="6f01d-104">有关教程的概述，请参阅[教程：开始使用 Windows Communication Foundation 应用程序](getting-started-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="6f01d-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="6f01d-105">创建 WCF 应用程序的下一步是添加代码以实现在上一步中创建的 WCF 服务接口。</span><span class="sxs-lookup"><span data-stu-id="6f01d-105">The next step for creating a WCF application is to add code to implement the WCF service interface that you created in the previous step.</span></span> <span data-ttu-id="6f01d-106">在此步骤中，创建一个名为类`CalculatorService`，用于实现用户定义`ICalculator`接口。</span><span class="sxs-lookup"><span data-stu-id="6f01d-106">In this step, you create a class named `CalculatorService` that implements the user-defined `ICalculator` interface.</span></span> <span data-ttu-id="6f01d-107">下面的代码中的每个方法调用计算器操作，并将文本写入到控制台，以对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="6f01d-107">Each method in the following code calls a calculator operation and writes text to the console to test it.</span></span> 

<span data-ttu-id="6f01d-108">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="6f01d-108">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="6f01d-109">添加代码以实现 WCF 服务约定。</span><span class="sxs-lookup"><span data-stu-id="6f01d-109">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="6f01d-110">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="6f01d-110">Build the solution.</span></span>

## <a name="add-code-to-implement-the-wcf-service-contract"></a><span data-ttu-id="6f01d-111">添加代码以实现 WCF 服务约定</span><span class="sxs-lookup"><span data-stu-id="6f01d-111">Add code to implement the WCF service contract</span></span>

<span data-ttu-id="6f01d-112">在中**GettingStartedLib**，打开**Service1.cs**或**Service1.vb**文件，其代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="6f01d-112">In **GettingStartedLib**, open the **Service1.cs** or **Service1.vb** file and replace its code with the following code:</span></span>

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

## <a name="edit-appconfig"></a><span data-ttu-id="6f01d-113">编辑 App.config</span><span class="sxs-lookup"><span data-stu-id="6f01d-113">Edit App.config</span></span>

<span data-ttu-id="6f01d-114">编辑**App.config**中**GettingStartedLib**以反映所做的更改所做的代码。</span><span class="sxs-lookup"><span data-stu-id="6f01d-114">Edit **App.config** in **GettingStartedLib** to reflect the changes you made to the code.</span></span>
- <span data-ttu-id="6f01d-115">视觉对象C#项目：</span><span class="sxs-lookup"><span data-stu-id="6f01d-115">For Visual C# projects:</span></span>
  - <span data-ttu-id="6f01d-116">更改第 14 行 `<service name="GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="6f01d-116">Change line 14 to `<service name="GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="6f01d-117">更改到的第 17 行 `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="6f01d-117">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="6f01d-118">更改到第 22 行 `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="6f01d-118">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`</span></span>

- <span data-ttu-id="6f01d-119">对于 Visual Basic 项目：</span><span class="sxs-lookup"><span data-stu-id="6f01d-119">For Visual Basic projects:</span></span>
  - <span data-ttu-id="6f01d-120">更改第 14 行 `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span><span class="sxs-lookup"><span data-stu-id="6f01d-120">Change line 14 to `<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`</span></span>
  - <span data-ttu-id="6f01d-121">更改到的第 17 行 `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span><span class="sxs-lookup"><span data-stu-id="6f01d-121">Change line 17 to `<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`</span></span>
  - <span data-ttu-id="6f01d-122">更改到第 22 行 `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span><span class="sxs-lookup"><span data-stu-id="6f01d-122">Change line 22 to `<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`</span></span>

## <a name="compile-the-code"></a><span data-ttu-id="6f01d-123">编译代码</span><span class="sxs-lookup"><span data-stu-id="6f01d-123">Compile the code</span></span>

<span data-ttu-id="6f01d-124">生成解决方案以验证已不存在任何编译错误。</span><span class="sxs-lookup"><span data-stu-id="6f01d-124">Build the solution to verify there aren't any compilation errors.</span></span> <span data-ttu-id="6f01d-125">如果在使用 Visual Studio 中，**构建**菜单中选择**生成解决方案**(或按**Ctrl**+**Shift** + **B**)。</span><span class="sxs-lookup"><span data-stu-id="6f01d-125">If you're using Visual Studio, on the **Build** menu select **Build Solution** (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="next-steps"></a><span data-ttu-id="6f01d-126">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6f01d-126">Next steps</span></span>

<span data-ttu-id="6f01d-127">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="6f01d-127">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="6f01d-128">添加代码以实现 WCF 服务约定。</span><span class="sxs-lookup"><span data-stu-id="6f01d-128">Add code to implement the WCF service contract.</span></span>
> - <span data-ttu-id="6f01d-129">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="6f01d-129">Build the solution.</span></span>

<span data-ttu-id="6f01d-130">转到下一步的教程，了解如何运行 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="6f01d-130">Advance to the next tutorial to learn how to run the WCF service.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6f01d-131">教程：托管并运行基本的 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="6f01d-131">Tutorial: Host and run a basic WCF service</span></span>](how-to-host-and-run-a-basic-wcf-service.md)
