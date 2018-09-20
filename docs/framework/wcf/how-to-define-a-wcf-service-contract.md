---
title: 如何：定义 Windows Communication Foundation 服务协定
ms.date: 09/14/2018
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: 4f85a51c47eb045d1d2f0111cb217199c9acf0d7
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2018
ms.locfileid: "46489154"
---
# <a name="how-to-define-a-windows-communication-foundation-service-contract"></a>如何：定义 Windows Communication Foundation 服务协定

这是创建基本 Windows Communication Foundation (WCF) 应用程序所需的六项任务的第一个。 有关全部六项任务的概述，请参阅[入门教程](../../../docs/framework/wcf/getting-started-tutorial.md)主题。

 创建 WCF 服务时，第一个任务是定义服务协定。 服务协定指定服务支持的操作。 可以将操作视为一个 Web 服务方法。 通过定义 C++、C# 或 Visual Basic (VB) 接口可创建协定。 接口中的每个方法都对应于特定的服务操作。 每个接口都必须将 <xref:System.ServiceModel.ServiceContractAttribute> 应用于它，而每个操作都必须将 <xref:System.ServiceModel.OperationContractAttribute> 特性应用于它。 如果接口中的一个方法具有 <xref:System.ServiceModel.ServiceContractAttribute> 特性而没有 <xref:System.ServiceModel.OperationContractAttribute> 特性，则服务不公开该方法。

 在操作过程后面的示例中提供了用于此任务的代码。

## <a name="define-a-service-contract"></a>定义服务协定

1. 右键单击该程序中的以管理员身份打开 Visual Studio**启动**菜单并选择**详细** > **以管理员身份运行**。

2. 创建 WCF 服务库项目。

   1. 从“文件”菜单中选择“新建” > “项目”。

   2. 在中**新的项目**对话框中的，在左侧，展开**Visual C#** 或**Visual Basic**，然后选择**WCF**类别。 在对话框的中心部分显示的项目模板列表。 选择**WCF 服务库**。

   3. 输入`GettingStartedLib`中**名称**文本框中并`GettingStarted`中**解决方案名称**文本框中，对话框的底部。

   > [!NOTE]
   > 如果没有看到**WCF**项目模板类别中，您可能需要安装**Windows Communication Foundation**组件的 Visual Studio。 在中**新的项目**对话框框中，单击链接**打开 Visual Studio 安装程序**。 选择**各个组件**选项卡，然后找到并选择**Windows Communication Foundation**下**开发活动**类别。 选择**修改**以开始安装该组件。

   Visual Studio 将创建包含 3 个文件的项目： IService1.cs （或 IService1.vb）、 Service1.cs （或 Service1.vb） 和 App.config。IService1 文件包含默认的服务协定。 Service1 文件包含服务协定的默认实现。 App.config 文件包含 Visual Studio WCF 服务主机加载默认服务所需的配置。 有关 WCF 服务主机工具的详细信息，请参阅[WCF 服务主机 (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)

3. 打开 IService1.cs 或 IService1.vb 文件并删除保留的命名空间声明的命名空间声明内的代码。 在命名空间声明内，定义名为 `ICalculator` 的新接口，如下面的代码所示。

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

     本协定定义了一个在线计算器。 注意，`ICalculator` 接口用 <xref:System.ServiceModel.ServiceContractAttribute> 特性标记。 此特性定义用于消除协定名称的歧义的命名空间。 每个计算器操作都用 <xref:System.ServiceModel.OperationContractAttribute> 特性标记。

## <a name="next-steps"></a>后续步骤

> [!div class="nextstepaction"]
> [如何： 实现服务协定](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)

## <a name="see-also"></a>请参阅

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [如何：实现服务协定](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)
- [入门](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [自承载](../../../docs/framework/wcf/samples/self-host.md)