---
title: "如何：定义 Windows Communication Foundation 服务协定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: service contracts [WCF], defining
ms.assetid: 67bf05b7-1d08-4911-83b7-a45d0b036fc3
caps.latest.revision: "58"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 062167742a70307949624066b8607a37d5c7ed71
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-define-a-windows-communication-foundation-service-contract"></a><span data-ttu-id="6fd49-102">如何：定义 Windows Communication Foundation 服务协定</span><span class="sxs-lookup"><span data-stu-id="6fd49-102">How to: Define a Windows Communication Foundation Service Contract</span></span>
<span data-ttu-id="6fd49-103">这是创建基本 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 应用程序所需的六项任务中的第一项任务。</span><span class="sxs-lookup"><span data-stu-id="6fd49-103">This is the first of six tasks required to create a basic [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] application.</span></span> <span data-ttu-id="6fd49-104">有关全部六项任务的概述，请参阅[入门教程](../../../docs/framework/wcf/getting-started-tutorial.md)主题。</span><span class="sxs-lookup"><span data-stu-id="6fd49-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="6fd49-105">创建 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务时，第一项任务是定义服务协定。</span><span class="sxs-lookup"><span data-stu-id="6fd49-105">When creating a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service, the first task is to define a service contract.</span></span> <span data-ttu-id="6fd49-106">服务协定指定服务支持的操作。</span><span class="sxs-lookup"><span data-stu-id="6fd49-106">The service contract specifies what operations the service supports.</span></span> <span data-ttu-id="6fd49-107">可以将操作视为一个 Web 服务方法。</span><span class="sxs-lookup"><span data-stu-id="6fd49-107">An operation can be thought of as a Web service method.</span></span> <span data-ttu-id="6fd49-108">通过定义 C++、C# 或 Visual Basic (VB) 接口可创建协定。</span><span class="sxs-lookup"><span data-stu-id="6fd49-108">Contracts are created by defining a C++, C#, or Visual Basic (VB) interface.</span></span> <span data-ttu-id="6fd49-109">接口中的每个方法都对应于特定的服务操作。</span><span class="sxs-lookup"><span data-stu-id="6fd49-109">Each method in the interface corresponds to a specific service operation.</span></span> <span data-ttu-id="6fd49-110">每个接口都必须将 <xref:System.ServiceModel.ServiceContractAttribute> 应用于它，而每个操作都必须将 <xref:System.ServiceModel.OperationContractAttribute> 特性应用于它。</span><span class="sxs-lookup"><span data-stu-id="6fd49-110">Each interface must have the <xref:System.ServiceModel.ServiceContractAttribute> applied to it and each operation must have the <xref:System.ServiceModel.OperationContractAttribute> attribute applied to it.</span></span> <span data-ttu-id="6fd49-111">如果接口中的一个方法具有 <xref:System.ServiceModel.ServiceContractAttribute> 特性而没有 <xref:System.ServiceModel.OperationContractAttribute> 特性，则服务不公开该方法。</span><span class="sxs-lookup"><span data-stu-id="6fd49-111">If a method within an interface that has the <xref:System.ServiceModel.ServiceContractAttribute> attribute does not have the <xref:System.ServiceModel.OperationContractAttribute> attribute, that method is not exposed by the service.</span></span>  
  
 <span data-ttu-id="6fd49-112">在操作过程后面的示例中提供了用于此任务的代码。</span><span class="sxs-lookup"><span data-stu-id="6fd49-112">The code used for this task is provided in the example following the procedure.</span></span>  
  
### <a name="to-define-a-service-contract"></a><span data-ttu-id="6fd49-113">定义服务协定</span><span class="sxs-lookup"><span data-stu-id="6fd49-113">To define a service contract</span></span>  
  
1.  <span data-ttu-id="6fd49-114">打开[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]以管理员身份中右键单击程序**启动**菜单并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="6fd49-114">Open  [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] as an administrator by right-clicking the program in the **Start** menu and selecting **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="6fd49-115">通过单击创建 WCF 服务库项目**文件**菜单并选择**新建**，**项目**。</span><span class="sxs-lookup"><span data-stu-id="6fd49-115">Create a WCF Service Library project by clicking the **File** menu and selecting **New**, **Project**.</span></span> <span data-ttu-id="6fd49-116">在**新项目**对话框中，在对话框的左侧展开**Visual C#**对于 C# 项目或**其他语言**然后**Visual Basic** Visual Basic 项目。</span><span class="sxs-lookup"><span data-stu-id="6fd49-116">In the **New Project** dialog, on the left-hand side of the dialog expand **Visual C#** for a C# project or **Other Languages** and then **Visual Basic** for a Visual Basic project.</span></span> <span data-ttu-id="6fd49-117">在所选的语言下选择**WCF**并将在对话框的中心部分上显示的项目模板列表。</span><span class="sxs-lookup"><span data-stu-id="6fd49-117">Under the language selected select **WCF** and a list of project templates will be displayed on the center section of the dialog.</span></span> <span data-ttu-id="6fd49-118">选择**WCF 服务库**，和类型`GettingStartedLib`中**名称**文本框中和`GettingStarted`中**解决方案名称**对话框底部的文本框。</span><span class="sxs-lookup"><span data-stu-id="6fd49-118">Select **WCF Service Library**, and type `GettingStartedLib` in the **Name** textbox and `GettingStarted` in the **Solution name** textbox at the bottom of the dialog.</span></span>  
  
3.  <span data-ttu-id="6fd49-119">Visual Studio 将创建包含以下 3 个文件的项目：IService1.cs（或 IService1.vb）、Service1.cs（或 Service1.vb）和 App.config。IService1 文件包含默认的服务协定。</span><span class="sxs-lookup"><span data-stu-id="6fd49-119">Visual Studio will create the project which contains 3 files: IService1.cs (or IService1.vb), Service1.cs (or Service1.vb), and App.config.  The IService1 file contains a default service contract.</span></span>  <span data-ttu-id="6fd49-120">Service1 文件包含服务协定的默认实现。</span><span class="sxs-lookup"><span data-stu-id="6fd49-120">The Service1 file contains a default implementation of the service contract.</span></span> <span data-ttu-id="6fd49-121">App.config 文件包含 Visual Studio WCF 服务主机加载默认服务所需的配置。</span><span class="sxs-lookup"><span data-stu-id="6fd49-121">The App.config file contains configuration needed to load the default service with the Visual Studio WCF Service Host.</span></span> <span data-ttu-id="6fd49-122">有关 WCF 服务主机工具的详细信息，请参阅[WCF 服务主机 (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span><span class="sxs-lookup"><span data-stu-id="6fd49-122">For more information about the WCF Service Host tool, see [WCF Service Host (WcfSvcHost.exe)](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)</span></span>  
  
4.  <span data-ttu-id="6fd49-123">打开 IService1.cs 或 IService1.vb 文件，删除命名空间声明内的代码，而留下命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="6fd49-123">Open the IService1.cs or IService1.vb file and delete the code within the namespace declaration leaving the namespace declaration.</span></span> <span data-ttu-id="6fd49-124">在命名空间声明内，定义名为 `ICalculator` 的新接口，如下面的代码所示。</span><span class="sxs-lookup"><span data-stu-id="6fd49-124">Inside the namespace declaration define a new interface called `ICalculator` as shown in the code below.</span></span>  
  
    ```  
    // IService.cs  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Runtime.Serialization;  
    using System.ServiceModel;  
    using System.Text;  
  
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
  
    ```  
    ‘IService.vb  
    Imports System  
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
  
     <span data-ttu-id="6fd49-125">本协定定义了一个在线计算器。</span><span class="sxs-lookup"><span data-stu-id="6fd49-125">This contract defines an online calculator.</span></span> <span data-ttu-id="6fd49-126">注意，`ICalculator` 接口用 <xref:System.ServiceModel.ServiceContractAttribute> 特性标记。</span><span class="sxs-lookup"><span data-stu-id="6fd49-126">Notice the `ICalculator` interface is marked with the <xref:System.ServiceModel.ServiceContractAttribute> attribute.</span></span> <span data-ttu-id="6fd49-127">此特性定义用于消除协定名称的歧义的命名空间。</span><span class="sxs-lookup"><span data-stu-id="6fd49-127">This attribute defines a namespace that is used to disambiguate the contract name.</span></span> <span data-ttu-id="6fd49-128">每个计算器操作都用 <xref:System.ServiceModel.OperationContractAttribute> 特性标记。</span><span class="sxs-lookup"><span data-stu-id="6fd49-128">Each calculator operation is marked with the <xref:System.ServiceModel.OperationContractAttribute> attribute.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6fd49-129">使用特性给接口、成员或类进行批注时，可以从特性名称中去掉“Attribute”部分。</span><span class="sxs-lookup"><span data-stu-id="6fd49-129">When using attributes to annotate an interface, member, or class, you can drop the "Attribute" part from the attribute name.</span></span> <span data-ttu-id="6fd49-130">因此 <xref:System.ServiceModel.ServiceContractAttribute> 在 C# 中为 `[ServiceContract]`，在 Visual Basic 中为 `<ServiceContract>`。</span><span class="sxs-lookup"><span data-stu-id="6fd49-130">So <xref:System.ServiceModel.ServiceContractAttribute> becomes `[ServiceContract]` in C#, or `<ServiceContract>` in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fd49-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6fd49-131">See Also</span></span>  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>  
 [<span data-ttu-id="6fd49-132">如何：实现服务协定</span><span class="sxs-lookup"><span data-stu-id="6fd49-132">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 [<span data-ttu-id="6fd49-133">入门</span><span class="sxs-lookup"><span data-stu-id="6fd49-133">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="6fd49-134">自承载</span><span class="sxs-lookup"><span data-stu-id="6fd49-134">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
