---
title: 教程：定义 Windows 通信基础服务协定
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 7c1c42c4f22a1a9627c147440e8e198551470b7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184096"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a>教程：定义 Windows 通信基础服务协定

本教程介绍创建基本 Windows 通信基础 （WCF） 应用程序所需的五项任务中的第一个。 有关教程的概述，请参阅[教程：开始使用 Windows 通信基础应用程序](getting-started-tutorial.md)。

创建 WCF 服务时，您的第一个任务是定义服务协定。 服务协定指定服务支持的操作。 可以将操作视为一个 Web 服务方法。 通过定义 C# 或可视化基本接口来创建服务协定。 接口具有以下特征：

- 接口中的每个方法都对应一个特定的服务操作。
- 对于每个接口，必须应用该<xref:System.ServiceModel.ServiceContractAttribute>属性。
- 对于每个操作/方法，必须应用该<xref:System.ServiceModel.OperationContractAttribute>属性。

在本教程中，你将了解如何执行以下操作：
> [!div class="checklist"]
>
> - 创建**WCF 服务库**项目。
> - 定义服务协定接口。

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a>创建 WCF 服务库项目并定义服务协定接口

1. 以管理员的身份打开 Visual Studio。 为此，请在 **"开始"** 菜单中选择 Visual Studio 程序，然后从快捷菜单中选择 **"以管理员** > **身份运行**"。

2. 创建**WCF 服务库**项目。

   1. 在“文件”**** 菜单中，选择“新建”**** > “项目”****。

   2. 在左侧的 **"新项目**"对话框中，展开**可视化 C#** 或**可视化基本**，然后选择**WCF**类别。 Visual Studio 在窗口的中心部分显示项目模板的列表。 选择**WCF 服务库**。

      > [!NOTE]
      > 如果您没有看到**WCF**项目模板类别，则可能需要安装 Visual Studio 的**Windows 通信基础**组件。 在 **"新项目**"对话框中，选择左侧的 **"打开可视化工作室安装程序"** 链接。 选择 **"单个组件**"选项卡，然后在 **"开发活动**"类别下查找并选择**Windows 通信基础**。 选择 **"修改"** 以开始安装组件。

   3. 在窗口的底部部分，输入"获取*入门Lib"***以**获取**解决方案名称的名称**和*入门*。

   4. 选择“确定”。

      Visual Studio 创建的项目有三个文件 *：IService1.cs（* 或用于可视化基础项目的*IService1.vb）、Service1.cs（* 或 Visual Basic 项目的*Service1.vb）* 和*App.config*。 *Service1.cs*Visual Studio 定义这些文件如下所示：
      - *IService1*文件包含服务协定的默认定义。
      - *Service1*文件包含服务协定的默认实现。
      - *App.config*文件包含使用 Visual Studio WCF 服务主机工具加载默认服务所需的配置信息。 有关 WCF 服务主机工具的详细信息，请参阅[WCF 服务主机 （WcfSvcHost.exe）。](wcf-service-host-wcfsvchost-exe.md)

      > [!NOTE]
      > 如果安装了具有可视化基本开发人员环境设置的 Visual Studio，则解决方案可能已隐藏。 如果是这种情况，请从 **"工具"** 菜单中选择 **"选项**"，然后在 **"选项"** 窗口中选择"**项目和解决方案** > **常规**"。 选择 **"始终显示解决方案**"。 此外，验证是否选择了**创建时保存新项目**。

3. 从**解决方案资源管理器**中打开**IService1.cs**或**IService1.vb**文件，并将其代码替换为以下代码：

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

     本协定定义了一个在线计算器。 请注意，`ICalculator`接口用<xref:System.ServiceModel.ServiceContractAttribute>属性标记（简化为`ServiceContract`）。 此属性定义命名空间以消除协定名称的歧义。 代码使用<xref:System.ServiceModel.OperationContractAttribute>属性标记每个计算器操作（简化为`OperationContract`）。

## <a name="next-steps"></a>后续步骤

在本教程中，你了解了如何执行以下操作：
> [!div class="checklist"]
>
> - 创建 WCF 服务库项目。
> - 定义服务协定接口。

进入下一个教程，了解如何实现 WCF 服务协定。

> [!div class="nextstepaction"]
> [教程：实现 WCF 服务协定](how-to-implement-a-wcf-contract.md)
