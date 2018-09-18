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
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46009001"
---
# <a name="how-to-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="96bea-102">如何：定义 Windows Communication Foundation 服务协定</span><span class="sxs-lookup"><span data-stu-id="96bea-102">How to: Define a Windows Communication Foundation Service Contract</span></span>

<span data-ttu-id="96bea-103">这是创建基本 Windows Communication Foundation (WCF) 应用程序所需的六项任务的第一个。</span><span class="sxs-lookup"><span data-stu-id="96bea-103">This is the first of six tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="96bea-104">有关全部六项任务的概述，请参阅[入门教程](../../../docs/framework/wcf/getting-started-tutorial.md)主题。</span><span class="sxs-lookup"><span data-stu-id="96bea-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>

 <span data-ttu-id="96bea-105">创建 WCF 服务时，第一个任务是定义服务协定。</span><span class="sxs-lookup"><span data-stu-id="96bea-105">When creating a WCF service, the first task is to define a service contract.</span></span> <span data-ttu-id="96bea-106">服务协定指定服务支持的操作。</span><span class="sxs-lookup"><span data-stu-id="96bea-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="96bea-107">可以将操作视为一个 Web 服务方法。</span><span class="sxs-lookup"><span data-stu-id="96bea-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="96bea-108">通过定义 C++、C# 或 Visual Basic (VB) 接口可创建协定。</span><span class="sxs-lookup"><span data-stu-id="96bea-108">Contracts are created by defining a C++, C#, or Visual Basic (VB) interface.</span></span> <span data-ttu-id="96bea-109">接口中的每个方法都对应于特定的服务操作。</span><span class="sxs-lookup"><span data-stu-id="96bea-109">Each method in the interface corresponds to a specific service operation.</span></span> <span data-ttu-id="96bea-110">每个接口都必须将 <xref:System.ServiceModel.ServiceContractAttribute> 应用于它，而每个操作都必须将 <xref:System.ServiceModel.OperationContractAttribute> 特性应用于它。</span><span class="sxs-lookup"><span data-stu-id="96bea-110">Each interface must have the <xref:System.ServiceModel.ServiceContractAttribute> applied to it and each operation must have the <xref:System.ServiceModel.OperationContractAttribute> attribute applied to it.</span></span> <span data-ttu-id="96bea-111">如果接口中的一个方法具有 <xref:System.ServiceModel.ServiceContractAttribute> 特性而没有 <xref:System.ServiceModel.OperationContractAttribute> 特性，则服务不公开该方法。</span><span class="sxs-lookup"><span data-stu-id="96bea-111">If a method within an interface that has the <xref:System.ServiceModel.ServiceContractAttribute> attribute does not have the <xref:System.ServiceModel.OperationContractAttribute> attribute, that method is not exposed by the service.</span></span>

 <span data-ttu-id="96bea-112">在操作过程后面的示例中提供了用于此任务的代码。</span><span class="sxs-lookup"><span data-stu-id="96bea-112">The code used for this task is provided in the example following the procedure.</span></span>

## <a name="define-a-service-contract"></a><span data-ttu-id="96bea-113">定义服务协定</span><span class="sxs-lookup"><span data-stu-id="96bea-113">Define a service contract</span></span>

1. <span data-ttu-id="96bea-114">右键单击该程序中的以管理员身份打开 Visual Studio**启动**菜单并选择**详细** > **以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="96bea-114">Open Visual Studio as an administrator by right-clicking the program in the **Start** menu and selecting **More** > **Run as administrator**.</span></span>

2. <span data-ttu-id="96bea-115">创建 WCF 服务库项目。</span><span class="sxs-lookup"><span data-stu-id="96bea-115">Create a WCF Service Library project.</span></span>

   1. <span data-ttu-id="96bea-116">从“文件”菜单中选择“新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="96bea-116">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="96bea-117">在中**新的项目**对话框中的，在左侧，展开**Visual C#** 或**Visual Basic**，然后选择**WCF**类别。</span><span class="sxs-lookup"><span data-stu-id="96bea-117">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="96bea-118">在对话框的中心部分显示的项目模板列表。</span><span class="sxs-lookup"><span data-stu-id="96bea-118">A list of project templates is displayed in the center section of the dialog.</span></span> <span data-ttu-id="96bea-119">选择**WCF 服务库**。</span><span class="sxs-lookup"><span data-stu-id="96bea-119">Select **WCF Service Library**.</span></span>

   3. <span data-ttu-id="96bea-120">输入`GettingStartedLib`中**名称**文本框中并`GettingStarted`中**解决方案名称**文本框中，对话框的底部。</span><span class="sxs-lookup"><span data-stu-id="96bea-120">Enter `GettingStartedLib` in the **Name** textbox and `GettingStarted` in the **Solution name** textbox at the bottom of the dialog.</span></span>

   > [!NOTE]
   > <span data-ttu-id="96bea-121">如果没有看到**WCF**项目模板类别中，您可能需要安装**Windows Communication Foundation**组件的 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="96bea-121">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="96bea-122">在中**新的项目**对话框框中，单击链接**打开 Visual Studio 安装程序**。</span><span class="sxs-lookup"><span data-stu-id="96bea-122">In the **New Project** dialog box, click the link that says **Open Visual Studio Installer**.</span></span> <span data-ttu-id="96bea-123">选择**各个组件**选项卡，然后找到并选择**Windows Communication Foundation**下**开发活动**类别。</span><span class="sxs-lookup"><span data-stu-id="96bea-123">Select the **Individual Components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="96bea-124">选择**修改**以开始安装该组件。</span><span class="sxs-lookup"><span data-stu-id="96bea-124">Choose **Modify** to begin installing the component.</span></span>

   <span data-ttu-id="96bea-125">Visual Studio 将创建包含 3 个文件的项目： IService1.cs （或 IService1.vb）、 Service1.cs （或 Service1.vb） 和 App.config。IService1 文件包含默认的服务协定。</span><span class="sxs-lookup"><span data-stu-id="96bea-125">Visual Studio creates the project, which contains 3 files: IService1.cs (or IService1.vb), Service1.cs (or Service1.vb), and App.config. The IService1 file contains a default service contract.</span></span> <span data-ttu-id="96bea-126">Service1 文件包含服务协定的默认实现。</span><span class="sxs-lookup"><span data-stu-id="96bea-126">The Service1 file contains a default implementation of the service contract.</span></span> <span data-ttu-id="96bea-127">App.config 文件包含 Visual Studio WCF 服务主机加载默认服务所需的配置。</span><span class="sxs-lookup"><span data-stu-id="96bea-127">The App.config file contains configuration needed to load the default service with the Visual Studio WCF Service Host.</span></span> <span data-ttu-id="96bea-128">有关 WCF 服务主机工具的详细信息，请参阅[WCF 服务主机 (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span><span class="sxs-lookup"><span data-stu-id="96bea-128">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span></span>

3. <span data-ttu-id="96bea-129">打开 IService1.cs 或 IService1.vb 文件并删除保留的命名空间声明的命名空间声明内的代码。</span><span class="sxs-lookup"><span data-stu-id="96bea-129">Open the IService1.cs or IService1.vb file and delete the code within the namespace declaration, leaving the namespace declaration.</span></span> <span data-ttu-id="96bea-130">在命名空间声明内，定义名为 `ICalculator` 的新接口，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="96bea-130">Inside the namespace declaration define a new interface called `ICalculator` as shown in the code below.</span></span>

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

     <span data-ttu-id="96bea-131">本协定定义了一个在线计算器。</span><span class="sxs-lookup"><span data-stu-id="96bea-131">This contract defines an online calculator.</span></span> <span data-ttu-id="96bea-132">注意，`ICalculator` 接口用 <xref:System.ServiceModel.ServiceContractAttribute> 特性标记。</span><span class="sxs-lookup"><span data-stu-id="96bea-132">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="96bea-133">此特性定义用于消除协定名称的歧义的命名空间。</span><span class="sxs-lookup"><span data-stu-id="96bea-133">This attribute defines a namespace that is used to disambiguate the contract name.</span></span> <span data-ttu-id="96bea-134">每个计算器操作都用 <xref:System.ServiceModel.OperationContractAttribute> 特性标记。</span><span class="sxs-lookup"><span data-stu-id="96bea-134">Each calculator operation is marked with the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span>

## <a name="next-steps"></a><span data-ttu-id="96bea-135">后续步骤</span><span class="sxs-lookup"><span data-stu-id="96bea-135">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="96bea-136">如何： 实现服务协定</span><span class="sxs-lookup"><span data-stu-id="96bea-136">How to: Implement a service contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)

## <a name="see-also"></a><span data-ttu-id="96bea-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="96bea-137">See also</span></span>

- <xref:System.ServiceModel.ServiceContractAttribute>
- <xref:System.ServiceModel.OperationContractAttribute>
- [<span data-ttu-id="96bea-138">如何：实现服务协定</span><span class="sxs-lookup"><span data-stu-id="96bea-138">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)
- [<span data-ttu-id="96bea-139">入门</span><span class="sxs-lookup"><span data-stu-id="96bea-139">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [<span data-ttu-id="96bea-140">自承载</span><span class="sxs-lookup"><span data-stu-id="96bea-140">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)