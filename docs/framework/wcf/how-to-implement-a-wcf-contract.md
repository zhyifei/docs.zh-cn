---
title: 教程：实现 Windows 通信基础服务协定
ms.date: 03/19/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- service contracts [WCF], implementing
ms.assetid: d5ab51ba-61ae-403e-b3c8-e2669e326806
ms.openlocfilehash: debdeeac7064f5bae21622b2d9de84a4d8a0e66f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184071"
---
# <a name="tutorial-implement-a-windows-communication-foundation-service-contract"></a>教程：实现 Windows 通信基础服务协定

本教程介绍创建基本 Windows 通信基础 （WCF） 应用程序所需的五项任务中的第二个。 有关教程的概述，请参阅[教程：开始使用 Windows 通信基础应用程序](getting-started-tutorial.md)。

创建 WCF 应用程序的下一步是添加代码以实现您在上一步中创建的 WCF 服务接口。 在此步骤中，您将创建一个名为`CalculatorService`实现用户定义的`ICalculator`接口的类。 以下代码中的每个方法调用计算器操作，并将文本写入控制台以进行测试。

在本教程中，你将了解如何执行以下操作：
> [!div class="checklist"]
>
> - 添加代码以实现 WCF 服务协定。
> - 生成解决方案。

## <a name="add-code-to-implement-the-wcf-service-contract"></a>添加代码以实现 WCF 服务协定

在**入门计划中**，打开**Service1.cs**或**Service1.vb**文件，并将其代码替换为以下代码：

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

## <a name="edit-appconfig"></a>编辑应用程序.配置

在**入门Lib**中编辑**App.config，** 以反映对代码所做的更改。

- 对于可视化 C# 项目：
  - 将行 14 更改为`<service name="GettingStartedLib.CalculatorService">`
  - 将行 17 更改为`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - 将行 22 更改为`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.ICalculator">`

- 对于 Visual Basic 项目：
  - 将行 14 更改为`<service name="GettingStartedLib.GettingStartedLib.CalculatorService">`
  - 将行 17 更改为`<add baseAddress = "http://localhost:8000/GettingStarted/CalculatorService" />`
  - 将行 22 更改为`<endpoint address="" binding="wsHttpBinding" contract="GettingStartedLib.GettingStartedLib.ICalculator">`

## <a name="compile-the-code"></a>编译代码

生成解决方案以验证没有任何编译错误。 如果您使用的是可视化工作室，请在 **"生成"** 菜单上选择 **"生成解决方案**"（或按**Ctrl**+**Shift**+**B**）。

## <a name="next-steps"></a>后续步骤

在本教程中，你了解了如何执行以下操作：
> [!div class="checklist"]
>
> - 添加代码以实现 WCF 服务协定。
> - 生成解决方案。

请先到下一教程，了解如何运行 WCF 服务。

> [!div class="nextstepaction"]
> [教程：托管并运行基本的 WCF 服务](how-to-host-and-run-a-basic-wcf-service.md)
