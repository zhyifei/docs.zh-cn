---
title: 教程：定义 Windows Communication Foundation 服务协定
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: ba88fc6ba4cba8d46ed1b43080d471b1b7c4bd75
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928874"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a>教程：定义 Windows Communication Foundation 服务协定

本教程介绍创建基本 Windows Communication Foundation （WCF）应用程序所需的五个任务中的第一个。 有关教程的概述，请参阅[教程：开始 Windows Communication Foundation 应用程序](getting-started-tutorial.md)。

创建 WCF 服务时，第一个任务是定义服务协定。 服务协定指定服务支持的操作。 可以将操作视为一个 Web 服务方法。 可以通过定义视觉对象C#或 VISUAL BASIC （VB）界面来创建服务协定。 接口具有以下特征：

- 接口中的每个方法都对应于特定的服务操作。 
- 对于每个接口，必须应用<xref:System.ServiceModel.ServiceContractAttribute>特性。
- 对于每个操作/方法，必须应用<xref:System.ServiceModel.OperationContractAttribute>特性。 

在本教程中，你将了解：
> [!div class="checklist"]
>
> - 创建一个**WCF 服务库**项目。
> - 定义服务协定接口。

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a>创建 WCF 服务库项目并定义服务协定接口

1. 以管理员身份打开 Visual Studio。 为此，请在 "**开始**" 菜单中选择 "Visual Studio" 程序，然后从快捷菜单中选择 "**更多** > **运行方式管理员**"。

2. 创建一个**WCF 服务库**项目。

   1. 从“文件”菜单中选择“新建” > “项目”。

   2. 在 "**新建项目**" 对话框的左侧，展开 "**视觉对象C#**  " 或 " **Visual Basic**"，然后选择 " **WCF** " 类别。 Visual Studio 会在窗口的中间部分显示项目模板的列表。 选择 " **WCF 服务库**"。

      > [!NOTE]
      > 如果看不到 " **WCF**项目模板" 类别，可能需要安装 Visual Studio 的**Windows Communication Foundation**组件。 在 "**新建项目**" 对话框中，选择左侧的 "**打开 Visual Studio 安装程序**" 链接。 选择 "**单个组件**" 选项卡，然后在 "**开发活动**" 类别下查找并选择**Windows Communication Foundation** 。 选择 "**修改**" 开始安装组件。

   3. 在窗口的底部，为 "**名称**" 和 " *GettingStarted* " 输入 " *GettingStartedLib* " 作为 "**解决方案名称**"。 

   4. 选择“确定”。

      Visual Studio 将创建项目，该项目具有三个文件：*IService1.cs* （或 Visual Basic 项目的*IService1* ）、 *Service1.cs* （或 Visual Basic 项目的*Service1* ）和*app.config*。Visual Studio 会按如下所示定义这些文件： 
      - *IService1*文件包含服务协定的默认定义。 
      - *Service1*文件包含服务协定的默认实现。 
      - *App.config*文件包含通过 VISUAL Studio WCF 服务主机工具加载默认服务所需的配置信息。 有关 WCF 服务主机工具的详细信息，请参阅[Wcf 服务主机（wcfsvchost.exe）](wcf-service-host-wcfsvchost-exe.md)。

      > [!NOTE]
      > 如果安装了包含 Visual Basic 开发人员环境设置的 Visual Studio，则可能会隐藏解决方案。 如果是这种情况，请从 "**工具**" 菜单中选择 "**选项**"，然后在 "**选项**" 窗口中选择 "**常规** **项目和解决方案** > "。 选择 "**始终显示解决方案**"。 同时，验证是否选择了 "**创建时保存新项目**"。

3. 在**解决方案资源管理器**中，打开**IService1.cs**或**IService1**文件，并将其代码替换为以下代码：

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

     本协定定义了一个在线计算器。 请注意`ICalculator` ，接口<xref:System.ServiceModel.ServiceContractAttribute>用特性标记（简化为`ServiceContract`）。 此属性定义一个命名空间以消除协定名称的歧义。 此代码用<xref:System.ServiceModel.OperationContractAttribute>属性标记每个计算器操作（简化为`OperationContract`）。

## <a name="next-steps"></a>后续步骤

在本教程中，你将了解：
> [!div class="checklist"]
>
> - 创建一个 WCF 服务库项目。
> - 定义服务协定接口。

转到下一教程，了解如何实现 WCF 服务协定。

> [!div class="nextstepaction"]
> [教程：实现 WCF 服务协定](how-to-implement-a-wcf-contract.md)
