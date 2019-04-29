---
title: 教程：定义 Windows Communication Foundation 服务协定
ms.date: 03/19/2019
helpviewer_keywords:
- service contracts [WCF], defining
dev_langs:
- CSharp
- VB
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
ms.openlocfilehash: a1908339460191fcb81d03d45c56dd57b2cf4c4e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61929345"
---
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="b2c04-102">教程：定义 Windows Communication Foundation 服务协定</span><span class="sxs-lookup"><span data-stu-id="b2c04-102">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="b2c04-103">本教程介绍创建基本 Windows Communication Foundation (WCF) 应用程序所需的五个任务的第一个。</span><span class="sxs-lookup"><span data-stu-id="b2c04-103">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="b2c04-104">有关教程的概述，请参阅[教程：开始使用 Windows Communication Foundation 应用程序](getting-started-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="b2c04-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="b2c04-105">创建 WCF 服务时，您的首要任务是定义服务协定。</span><span class="sxs-lookup"><span data-stu-id="b2c04-105">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="b2c04-106">服务协定指定服务支持的操作。</span><span class="sxs-lookup"><span data-stu-id="b2c04-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="b2c04-107">可以将操作视为一个 Web 服务方法。</span><span class="sxs-lookup"><span data-stu-id="b2c04-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="b2c04-108">通过定义视觉对象创建服务协定C#或 Visual Basic (VB) 接口。</span><span class="sxs-lookup"><span data-stu-id="b2c04-108">You create service contracts by defining a Visual C# or Visual Basic (VB) interface.</span></span> <span data-ttu-id="b2c04-109">接口具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="b2c04-109">An interface has the following characteristics:</span></span>

- <span data-ttu-id="b2c04-110">接口中的每个方法都对应于特定的服务操作。</span><span class="sxs-lookup"><span data-stu-id="b2c04-110">Each method in the interface corresponds to a specific service operation.</span></span> 
- <span data-ttu-id="b2c04-111">对于每个接口，你必须应用<xref:System.ServiceModel.ServiceContractAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="b2c04-111">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="b2c04-112">对于每个操作/方法，你必须应用<xref:System.ServiceModel.OperationContractAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="b2c04-112">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span> 

<span data-ttu-id="b2c04-113">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="b2c04-113">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="b2c04-114">创建**WCF 服务库**项目。</span><span class="sxs-lookup"><span data-stu-id="b2c04-114">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="b2c04-115">定义服务协定接口。</span><span class="sxs-lookup"><span data-stu-id="b2c04-115">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="b2c04-116">创建 WCF 服务库项目并定义服务协定接口</span><span class="sxs-lookup"><span data-stu-id="b2c04-116">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="b2c04-117">以管理员身份打开 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="b2c04-117">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="b2c04-118">若要执行此操作，请选择中的 Visual Studio 程序**启动**菜单，并选择**详细** > **以管理员身份运行**从快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="b2c04-118">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="b2c04-119">创建**WCF 服务库**项目。</span><span class="sxs-lookup"><span data-stu-id="b2c04-119">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="b2c04-120">从“文件”菜单中选择“新建” > “项目”。</span><span class="sxs-lookup"><span data-stu-id="b2c04-120">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="b2c04-121">在中**新的项目**对话框中的，在左侧，展开**Visual C#** 或**Visual Basic**，然后选择**WCF**类别。</span><span class="sxs-lookup"><span data-stu-id="b2c04-121">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="b2c04-122">Visual Studio 窗口的中心部分中显示项目模板的列表。</span><span class="sxs-lookup"><span data-stu-id="b2c04-122">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="b2c04-123">选择**WCF 服务库**。</span><span class="sxs-lookup"><span data-stu-id="b2c04-123">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="b2c04-124">如果没有看到**WCF**项目模板类别中，您可能需要安装**Windows Communication Foundation**组件的 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="b2c04-124">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="b2c04-125">在中**新的项目**对话框中，选择**打开 Visual Studio 安装程序**左侧和右侧的链接。</span><span class="sxs-lookup"><span data-stu-id="b2c04-125">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="b2c04-126">选择**各个组件**选项卡，然后找到并选择**Windows Communication Foundation**下**开发活动**类别。</span><span class="sxs-lookup"><span data-stu-id="b2c04-126">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="b2c04-127">选择**修改**以开始安装该组件。</span><span class="sxs-lookup"><span data-stu-id="b2c04-127">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="b2c04-128">在窗口的下半部分中，输入*GettingStartedLib*有关**名称**并*GettingStarted*有关**解决方案名称**。</span><span class="sxs-lookup"><span data-stu-id="b2c04-128">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span> 

   4. <span data-ttu-id="b2c04-129">选择 **确定**。</span><span class="sxs-lookup"><span data-stu-id="b2c04-129">Select **OK**.</span></span>

      <span data-ttu-id="b2c04-130">Visual Studio 创建项目，它具有三个文件：*IService1.cs* (或*IService1.vb* Visual Basic 项目)， *Service1.cs* (或*Service1.vb* Visual Basic 项目)，和*App.config*。Visual Studio 定义这些文件，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b2c04-130">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span> 
      - <span data-ttu-id="b2c04-131">*IService1*文件包含服务协定的默认定义。</span><span class="sxs-lookup"><span data-stu-id="b2c04-131">The *IService1* file contains the default definition of the service contract.</span></span> 
      - <span data-ttu-id="b2c04-132">*Service1*文件包含服务协定的默认实现。</span><span class="sxs-lookup"><span data-stu-id="b2c04-132">The *Service1* file contains the default implementation of the service contract.</span></span> 
      - <span data-ttu-id="b2c04-133">*App.config*文件包含加载具有 Visual Studio WCF 服务主机工具的默认服务所需的配置信息。</span><span class="sxs-lookup"><span data-stu-id="b2c04-133">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="b2c04-134">有关 WCF 服务主机工具的详细信息，请参阅[WCF 服务主机 (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="b2c04-134">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="b2c04-135">如果使用 Visual Basic 开发人员环境设置安装 Visual Studio，解决方案可能被隐藏。</span><span class="sxs-lookup"><span data-stu-id="b2c04-135">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="b2c04-136">如果这种情况，请选择**选项**从**工具**菜单中，然后选择**项目和解决方案** > **常规**中**选项**窗口。</span><span class="sxs-lookup"><span data-stu-id="b2c04-136">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="b2c04-137">选择**总是显示解决方案**。</span><span class="sxs-lookup"><span data-stu-id="b2c04-137">Select **Always show solution**.</span></span> <span data-ttu-id="b2c04-138">此外，检查是否**保存新项目时创建**处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="b2c04-138">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="b2c04-139">从**解决方案资源管理器**，打开**IService1.cs**或**IService1.vb**文件，并其代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="b2c04-139">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

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

     <span data-ttu-id="b2c04-140">本协定定义了一个在线计算器。</span><span class="sxs-lookup"><span data-stu-id="b2c04-140">This contract defines an online calculator.</span></span> <span data-ttu-id="b2c04-141">请注意`ICalculator`接口将标有<xref:System.ServiceModel.ServiceContractAttribute>属性 (为简化`ServiceContract`)。</span><span class="sxs-lookup"><span data-stu-id="b2c04-141">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="b2c04-142">此属性定义一个命名空间以消除协定名称的歧义。</span><span class="sxs-lookup"><span data-stu-id="b2c04-142">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="b2c04-143">该代码将标记与每个计算器操作<xref:System.ServiceModel.OperationContractAttribute>属性 (为简化`OperationContract`)。</span><span class="sxs-lookup"><span data-stu-id="b2c04-143">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b2c04-144">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b2c04-144">Next steps</span></span>

<span data-ttu-id="b2c04-145">在本教程中，你将了解：</span><span class="sxs-lookup"><span data-stu-id="b2c04-145">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> - <span data-ttu-id="b2c04-146">创建 WCF 服务库项目。</span><span class="sxs-lookup"><span data-stu-id="b2c04-146">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="b2c04-147">定义服务协定接口。</span><span class="sxs-lookup"><span data-stu-id="b2c04-147">Define a service contract interface.</span></span>

<span data-ttu-id="b2c04-148">转到下一步的教程，了解如何实现 WCF 服务约定。</span><span class="sxs-lookup"><span data-stu-id="b2c04-148">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b2c04-149">教程：实现 WCF 服务约定</span><span class="sxs-lookup"><span data-stu-id="b2c04-149">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
