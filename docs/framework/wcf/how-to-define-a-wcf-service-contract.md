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
# <a name="tutorial-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="20b2b-102">教程：定义 Windows 通信基础服务协定</span><span class="sxs-lookup"><span data-stu-id="20b2b-102">Tutorial: Define a Windows Communication Foundation service contract</span></span>

<span data-ttu-id="20b2b-103">本教程介绍创建基本 Windows 通信基础 （WCF） 应用程序所需的五项任务中的第一个。</span><span class="sxs-lookup"><span data-stu-id="20b2b-103">This tutorial describes the first of five tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="20b2b-104">有关教程的概述，请参阅[教程：开始使用 Windows 通信基础应用程序](getting-started-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="20b2b-104">For an overview of the tutorials, see [Tutorial: Get started with Windows Communication Foundation applications](getting-started-tutorial.md).</span></span>

<span data-ttu-id="20b2b-105">创建 WCF 服务时，您的第一个任务是定义服务协定。</span><span class="sxs-lookup"><span data-stu-id="20b2b-105">When you create a WCF service, your first task is to define a service contract.</span></span> <span data-ttu-id="20b2b-106">服务协定指定服务支持的操作。</span><span class="sxs-lookup"><span data-stu-id="20b2b-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="20b2b-107">可以将操作视为一个 Web 服务方法。</span><span class="sxs-lookup"><span data-stu-id="20b2b-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="20b2b-108">通过定义 C# 或可视化基本接口来创建服务协定。</span><span class="sxs-lookup"><span data-stu-id="20b2b-108">You create service contracts by defining a C# or Visual Basic interface.</span></span> <span data-ttu-id="20b2b-109">接口具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="20b2b-109">An interface has the following characteristics:</span></span>

- <span data-ttu-id="20b2b-110">接口中的每个方法都对应一个特定的服务操作。</span><span class="sxs-lookup"><span data-stu-id="20b2b-110">Each method in the interface corresponds to a specific service operation.</span></span>
- <span data-ttu-id="20b2b-111">对于每个接口，必须应用该<xref:System.ServiceModel.ServiceContractAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="20b2b-111">For each interface, you must apply the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span>
- <span data-ttu-id="20b2b-112">对于每个操作/方法，必须应用该<xref:System.ServiceModel.OperationContractAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="20b2b-112">For each operation/method, you must apply the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span>

<span data-ttu-id="20b2b-113">在本教程中，你将了解如何执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="20b2b-113">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="20b2b-114">创建**WCF 服务库**项目。</span><span class="sxs-lookup"><span data-stu-id="20b2b-114">Create a **WCF Service Library** project.</span></span>
> - <span data-ttu-id="20b2b-115">定义服务协定接口。</span><span class="sxs-lookup"><span data-stu-id="20b2b-115">Define a service contract interface.</span></span>

## <a name="create-a-wcf-service-library-project-and-define-a-service-contract-interface"></a><span data-ttu-id="20b2b-116">创建 WCF 服务库项目并定义服务协定接口</span><span class="sxs-lookup"><span data-stu-id="20b2b-116">Create a WCF Service Library project and define a service contract interface</span></span>

1. <span data-ttu-id="20b2b-117">以管理员的身份打开 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="20b2b-117">Open Visual Studio as an administrator.</span></span> <span data-ttu-id="20b2b-118">为此，请在 **"开始"** 菜单中选择 Visual Studio 程序，然后从快捷菜单中选择 **"以管理员** > **身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="20b2b-118">To do so, select the Visual Studio program in the **Start** menu, and then select **More** > **Run as administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="20b2b-119">创建**WCF 服务库**项目。</span><span class="sxs-lookup"><span data-stu-id="20b2b-119">Create a **WCF Service Library** project.</span></span>

   1. <span data-ttu-id="20b2b-120">在“文件”\*\*\*\* 菜单中，选择“新建”\*\*\*\* > “项目”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="20b2b-120">From the **File** menu, select **New** > **Project**.</span></span>

   2. <span data-ttu-id="20b2b-121">在左侧的 **"新项目**"对话框中，展开**可视化 C#** 或**可视化基本**，然后选择**WCF**类别。</span><span class="sxs-lookup"><span data-stu-id="20b2b-121">In the **New Project** dialog, on the left-hand side, expand **Visual C#** or **Visual Basic**, and then select the **WCF** category.</span></span> <span data-ttu-id="20b2b-122">Visual Studio 在窗口的中心部分显示项目模板的列表。</span><span class="sxs-lookup"><span data-stu-id="20b2b-122">Visual Studio displays a list of project templates in the center section of the window.</span></span> <span data-ttu-id="20b2b-123">选择**WCF 服务库**。</span><span class="sxs-lookup"><span data-stu-id="20b2b-123">Select **WCF Service Library**.</span></span>

      > [!NOTE]
      > <span data-ttu-id="20b2b-124">如果您没有看到**WCF**项目模板类别，则可能需要安装 Visual Studio 的**Windows 通信基础**组件。</span><span class="sxs-lookup"><span data-stu-id="20b2b-124">If you don't see the **WCF** project template category, you may need to install the **Windows Communication Foundation** component of Visual Studio.</span></span> <span data-ttu-id="20b2b-125">在 **"新项目**"对话框中，选择左侧的 **"打开可视化工作室安装程序"** 链接。</span><span class="sxs-lookup"><span data-stu-id="20b2b-125">In the **New Project** dialog box, select the **Open Visual Studio Installer** link on the left side.</span></span> <span data-ttu-id="20b2b-126">选择 **"单个组件**"选项卡，然后在 **"开发活动**"类别下查找并选择**Windows 通信基础**。</span><span class="sxs-lookup"><span data-stu-id="20b2b-126">Select the **Individual components** tab, and then find and select **Windows Communication Foundation** under the **Development activities** category.</span></span> <span data-ttu-id="20b2b-127">选择 **"修改"** 以开始安装组件。</span><span class="sxs-lookup"><span data-stu-id="20b2b-127">Choose **Modify** to begin installing the component.</span></span>

   3. <span data-ttu-id="20b2b-128">在窗口的底部部分，输入"获取*入门Lib"\***以**获取**解决方案名称的名称**和*入门\*。</span><span class="sxs-lookup"><span data-stu-id="20b2b-128">In the bottom section of the window, enter *GettingStartedLib* for the **Name** and *GettingStarted* for the **Solution name**.</span></span>

   4. <span data-ttu-id="20b2b-129">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="20b2b-129">Select **OK**.</span></span>

      <span data-ttu-id="20b2b-130">Visual Studio 创建的项目有三个文件 *：IService1.cs（* 或用于可视化基础项目的*IService1.vb）、Service1.cs（* 或 Visual Basic 项目的*Service1.vb）* 和*App.config*。 *Service1.cs*Visual Studio 定义这些文件如下所示：</span><span class="sxs-lookup"><span data-stu-id="20b2b-130">Visual Studio creates the project, which has three files: *IService1.cs* (or *IService1.vb* for a Visual Basic project), *Service1.cs* (or *Service1.vb* for a Visual Basic project), and *App.config*. Visual Studio defines these files as follows:</span></span>
      - <span data-ttu-id="20b2b-131">*IService1*文件包含服务协定的默认定义。</span><span class="sxs-lookup"><span data-stu-id="20b2b-131">The *IService1* file contains the default definition of the service contract.</span></span>
      - <span data-ttu-id="20b2b-132">*Service1*文件包含服务协定的默认实现。</span><span class="sxs-lookup"><span data-stu-id="20b2b-132">The *Service1* file contains the default implementation of the service contract.</span></span>
      - <span data-ttu-id="20b2b-133">*App.config*文件包含使用 Visual Studio WCF 服务主机工具加载默认服务所需的配置信息。</span><span class="sxs-lookup"><span data-stu-id="20b2b-133">The *App.config* file contains the configuration info needed to load the default service with the Visual Studio WCF Service Host tool.</span></span> <span data-ttu-id="20b2b-134">有关 WCF 服务主机工具的详细信息，请参阅[WCF 服务主机 （WcfSvcHost.exe）。](wcf-service-host-wcfsvchost-exe.md)</span><span class="sxs-lookup"><span data-stu-id="20b2b-134">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](wcf-service-host-wcfsvchost-exe.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="20b2b-135">如果安装了具有可视化基本开发人员环境设置的 Visual Studio，则解决方案可能已隐藏。</span><span class="sxs-lookup"><span data-stu-id="20b2b-135">If you installed Visual Studio with Visual Basic developer environment settings, the solution might be hidden.</span></span> <span data-ttu-id="20b2b-136">如果是这种情况，请从 **"工具"** 菜单中选择 **"选项**"，然后在 **"选项"** 窗口中选择"**项目和解决方案** > **常规**"。</span><span class="sxs-lookup"><span data-stu-id="20b2b-136">If this is the case, select **Options** from the **Tools** menu, then select **Projects and Solutions** > **General** in the **Options** window.</span></span> <span data-ttu-id="20b2b-137">选择 **"始终显示解决方案**"。</span><span class="sxs-lookup"><span data-stu-id="20b2b-137">Select **Always show solution**.</span></span> <span data-ttu-id="20b2b-138">此外，验证是否选择了**创建时保存新项目**。</span><span class="sxs-lookup"><span data-stu-id="20b2b-138">Also, verify that **Save new projects when created** is selected.</span></span>

3. <span data-ttu-id="20b2b-139">从**解决方案资源管理器**中打开**IService1.cs**或**IService1.vb**文件，并将其代码替换为以下代码：</span><span class="sxs-lookup"><span data-stu-id="20b2b-139">From **Solution Explorer**, open the **IService1.cs** or **IService1.vb** file, and replace its code with the following code:</span></span>

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

     <span data-ttu-id="20b2b-140">本协定定义了一个在线计算器。</span><span class="sxs-lookup"><span data-stu-id="20b2b-140">This contract defines an online calculator.</span></span> <span data-ttu-id="20b2b-141">请注意，`ICalculator`接口用<xref:System.ServiceModel.ServiceContractAttribute>属性标记（简化为`ServiceContract`）。</span><span class="sxs-lookup"><span data-stu-id="20b2b-141">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute (simplified as `ServiceContract`).</span></span> <span data-ttu-id="20b2b-142">此属性定义命名空间以消除协定名称的歧义。</span><span class="sxs-lookup"><span data-stu-id="20b2b-142">This attribute defines a namespace to disambiguate the contract name.</span></span> <span data-ttu-id="20b2b-143">代码使用<xref:System.ServiceModel.OperationContractAttribute>属性标记每个计算器操作（简化为`OperationContract`）。</span><span class="sxs-lookup"><span data-stu-id="20b2b-143">The code marks each calculator operation with the <xref:System.ServiceModel.OperationContractAttribute> attribute (simplified as `OperationContract`).</span></span>

## <a name="next-steps"></a><span data-ttu-id="20b2b-144">后续步骤</span><span class="sxs-lookup"><span data-stu-id="20b2b-144">Next steps</span></span>

<span data-ttu-id="20b2b-145">在本教程中，你了解了如何执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="20b2b-145">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
>
> - <span data-ttu-id="20b2b-146">创建 WCF 服务库项目。</span><span class="sxs-lookup"><span data-stu-id="20b2b-146">Create a WCF Service Library project.</span></span>
> - <span data-ttu-id="20b2b-147">定义服务协定接口。</span><span class="sxs-lookup"><span data-stu-id="20b2b-147">Define a service contract interface.</span></span>

<span data-ttu-id="20b2b-148">进入下一个教程，了解如何实现 WCF 服务协定。</span><span class="sxs-lookup"><span data-stu-id="20b2b-148">Advance to the next tutorial to learn how to implement the WCF service contract.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="20b2b-149">教程：实现 WCF 服务协定</span><span class="sxs-lookup"><span data-stu-id="20b2b-149">Tutorial: Implement a WCF service contract</span></span>](how-to-implement-a-wcf-contract.md)
