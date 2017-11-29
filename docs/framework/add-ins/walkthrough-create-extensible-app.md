---
title: "演练：创建可扩展的应用程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [.NET Framework], add-in pipeline
- host-side adapters for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], creating
- add-in-side adapter [.NET Framework]
- contracts for add-in pipelines [.NET Framework]
ms.assetid: 694a33c5-a040-450d-aed5-ac49fc88ce61
caps.latest.revision: "32"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6609f30844421f94965fbe05114db96ed8edbb31
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-creating-an-extensible-application"></a><span data-ttu-id="a34ed-102">演练：创建可扩展的应用程序</span><span class="sxs-lookup"><span data-stu-id="a34ed-102">Walkthrough: Creating an Extensible Application</span></span>
<span data-ttu-id="a34ed-103">本演练介绍如何创建用于执行简单的计算器功能的外接程序的管道。</span><span class="sxs-lookup"><span data-stu-id="a34ed-103">This walkthrough describes how to create a pipeline for an add-in that performs simple calculator functions.</span></span> <span data-ttu-id="a34ed-104">它并不演示实际方案;相反，它演示了管道以及如何外接程序可以提供主机服务的基本功能。</span><span class="sxs-lookup"><span data-stu-id="a34ed-104">It does not demonstrate a real-world scenario; rather, it demonstrates the basic functionality of a pipeline and how an add-in can provide services for a host.</span></span>  
  
 <span data-ttu-id="a34ed-105">本演练介绍了以下任务：</span><span class="sxs-lookup"><span data-stu-id="a34ed-105">This walkthrough describes the following tasks:</span></span>  
  
-   <span data-ttu-id="a34ed-106">创建 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="a34ed-106">Creating a Visual Studio solution.</span></span>  
  
-   <span data-ttu-id="a34ed-107">创建管线目录结构。</span><span class="sxs-lookup"><span data-stu-id="a34ed-107">Creating the pipeline directory structure.</span></span>  
  
-   <span data-ttu-id="a34ed-108">创建的协定和视图。</span><span class="sxs-lookup"><span data-stu-id="a34ed-108">Creating the contract and views.</span></span>  
  
-   <span data-ttu-id="a34ed-109">创建外接程序端适配器。</span><span class="sxs-lookup"><span data-stu-id="a34ed-109">Creating the add-in-side adapter.</span></span>  
  
-   <span data-ttu-id="a34ed-110">创建主机端适配器。</span><span class="sxs-lookup"><span data-stu-id="a34ed-110">Creating the host-side adapter.</span></span>  
  
-   <span data-ttu-id="a34ed-111">创建主机。</span><span class="sxs-lookup"><span data-stu-id="a34ed-111">Creating the host.</span></span>  
  
-   <span data-ttu-id="a34ed-112">创建外接程序。</span><span class="sxs-lookup"><span data-stu-id="a34ed-112">Creating the add-in.</span></span>  
  
-   <span data-ttu-id="a34ed-113">部署管道。</span><span class="sxs-lookup"><span data-stu-id="a34ed-113">Deploying the pipeline.</span></span>  
  
-   <span data-ttu-id="a34ed-114">运行主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="a34ed-114">Running the host application.</span></span>  
  
 <span data-ttu-id="a34ed-115">此管道传递仅可序列化的类型 (<xref:System.Double>和<xref:System.String>)、 主机和外接程序之间。</span><span class="sxs-lookup"><span data-stu-id="a34ed-115">This pipeline passes only serializable types (<xref:System.Double> and <xref:System.String>), between the host and the add-in.</span></span> <span data-ttu-id="a34ed-116">有关示例，演示如何将传递复杂数据类型的集合，请参阅[演练： 将集合传递之间主机和外接程序](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5)。</span><span class="sxs-lookup"><span data-stu-id="a34ed-116">For an example that shows how to pass collections of complex data types, see [Walkthrough: Passing Collections Between Hosts and Add-Ins](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5).</span></span>  
  
 <span data-ttu-id="a34ed-117">此管道协定定义四个算术运算的对象模型： 添加、 减、 乘和除。</span><span class="sxs-lookup"><span data-stu-id="a34ed-117">The contract for this pipeline defines an object model of four arithmetic operations: add, subtract, multiply, and divide.</span></span> <span data-ttu-id="a34ed-118">主机外接程序提供的公式来计算，如 2 + 2，和外接程序将结果返回给主机。</span><span class="sxs-lookup"><span data-stu-id="a34ed-118">The host provides the add-in with an equation to calculate, such as 2 + 2, and the add-in returns the result to the host.</span></span>  
  
 <span data-ttu-id="a34ed-119">版本 2 的计算器外接程序提供更多的计算的可能性，并演示版本控制。</span><span class="sxs-lookup"><span data-stu-id="a34ed-119">Version 2 of the calculator add-in provides more calculating possibilities and demonstrates versioning.</span></span> <span data-ttu-id="a34ed-120">中描述的那样[演练： 启用作为主机所做的更改的向后兼容性](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848)。</span><span class="sxs-lookup"><span data-stu-id="a34ed-120">It is described in [Walkthrough: Enabling Backward Compatibility as Your Host Changes](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a34ed-121">先决条件</span><span class="sxs-lookup"><span data-stu-id="a34ed-121">Prerequisites</span></span>  
 <span data-ttu-id="a34ed-122">若要完成本演练，你需要具备以下条件：</span><span class="sxs-lookup"><span data-stu-id="a34ed-122">You need the following to complete this walkthrough:</span></span>  
  
-   [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]<span data-ttu-id="a34ed-123">。</span><span class="sxs-lookup"><span data-stu-id="a34ed-123">.</span></span>  
  
## <a name="creating-a-visual-studio-solution"></a><span data-ttu-id="a34ed-124">创建 Visual Studio 解决方案</span><span class="sxs-lookup"><span data-stu-id="a34ed-124">Creating a Visual Studio Solution</span></span>  
 <span data-ttu-id="a34ed-125">使用一种解决方案[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]以包含的管道段的项目。</span><span class="sxs-lookup"><span data-stu-id="a34ed-125">Use a solution in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] to contain the projects of your pipeline segments.</span></span>  
  
#### <a name="to-create-the-pipeline-solution"></a><span data-ttu-id="a34ed-126">若要创建管道解决方案</span><span class="sxs-lookup"><span data-stu-id="a34ed-126">To create the pipeline solution</span></span>  
  
1.  <span data-ttu-id="a34ed-127">在[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]，创建一个名为的新项目`Calc1Contract`。</span><span class="sxs-lookup"><span data-stu-id="a34ed-127">In [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], create a new project named `Calc1Contract`.</span></span> <span data-ttu-id="a34ed-128">使该项目基于**类库**模板。</span><span class="sxs-lookup"><span data-stu-id="a34ed-128">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="a34ed-129">将解决方案命名`CalculatorV1`。</span><span class="sxs-lookup"><span data-stu-id="a34ed-129">Name the solution `CalculatorV1`.</span></span>  
  
## <a name="creating-the-pipeline-directory-structure"></a><span data-ttu-id="a34ed-130">创建管线目录结构</span><span class="sxs-lookup"><span data-stu-id="a34ed-130">Creating the Pipeline Directory Structure</span></span>  
 <span data-ttu-id="a34ed-131">外接程序模型需要置于指定的目录结构中的管道段程序集。</span><span class="sxs-lookup"><span data-stu-id="a34ed-131">The add-in model requires the pipeline segment assemblies to be placed in a specified directory structure.</span></span> <span data-ttu-id="a34ed-132">有关管道结构的详细信息，请参阅[管线开发要求](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)。</span><span class="sxs-lookup"><span data-stu-id="a34ed-132">For more information about the pipeline structure, see [Pipeline Development Requirements](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
#### <a name="to-create-the-pipeline-directory-structure"></a><span data-ttu-id="a34ed-133">若要创建管线目录结构</span><span class="sxs-lookup"><span data-stu-id="a34ed-133">To create the pipeline directory structure</span></span>  
  
1.  <span data-ttu-id="a34ed-134">在你的计算机上的任何位置创建应用程序文件夹。</span><span class="sxs-lookup"><span data-stu-id="a34ed-134">Create an application folder anywhere on your computer.</span></span>  
  
2.  <span data-ttu-id="a34ed-135">在该文件夹中，创建以下结构：</span><span class="sxs-lookup"><span data-stu-id="a34ed-135">In that folder, create the following structure:</span></span>  
  
    ```  
    Pipeline  
      AddIns  
        CalcV1  
        CalcV2  
      AddInSideAdapters  
      AddInViews  
      Contracts  
      HostSideAdapters  
    ```  
  
     <span data-ttu-id="a34ed-136">不需要将管道文件夹结构放在应用程序文件夹中;它仅为方便起见在此处完成。</span><span class="sxs-lookup"><span data-stu-id="a34ed-136">It is not necessary to put the pipeline folder structure in your application folder; it is done here only for convenience.</span></span> <span data-ttu-id="a34ed-137">在相应的步骤，本演练说明如何更改代码，如果管道文件夹结构是在不同的位置。</span><span class="sxs-lookup"><span data-stu-id="a34ed-137">At the appropriate step, the walkthrough explains how to change the code if the pipeline folder structure is in a different location.</span></span> <span data-ttu-id="a34ed-138">请参阅中的管道 directory 要求讨论[管线开发要求](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)。</span><span class="sxs-lookup"><span data-stu-id="a34ed-138">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a34ed-139">`CalcV2`文件夹不会使用在本演练中; 它是一个占位符，供[演练： 启用作为主机所做的更改的向后兼容性](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848)。</span><span class="sxs-lookup"><span data-stu-id="a34ed-139">The `CalcV2` folder is not used in this walkthrough; it is a placeholder for [Walkthrough: Enabling Backward Compatibility as Your Host Changes](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="creating-the-contract-and-views"></a><span data-ttu-id="a34ed-140">正在创建协定和视图</span><span class="sxs-lookup"><span data-stu-id="a34ed-140">Creating the Contract and Views</span></span>  
 <span data-ttu-id="a34ed-141">此管道的合约段定义`ICalc1Contract`接口，定义四个方法： `add`， `subtract`， `multiply`，和`divide`。</span><span class="sxs-lookup"><span data-stu-id="a34ed-141">The contract segment for this pipeline defines the `ICalc1Contract` interface, which defines four methods: `add`, `subtract`, `multiply`, and `divide`.</span></span>  
  
#### <a name="to-create-the-contract"></a><span data-ttu-id="a34ed-142">若要创建协定</span><span class="sxs-lookup"><span data-stu-id="a34ed-142">To create the contract</span></span>  
  
1.  <span data-ttu-id="a34ed-143">在 Visual Studio 解决方案中名为`CalculatorV1`，打开`Calc1Contract`项目。</span><span class="sxs-lookup"><span data-stu-id="a34ed-143">In the Visual Studio solution named `CalculatorV1`, open the `Calc1Contract` project.</span></span>  
  
2.  <span data-ttu-id="a34ed-144">在**解决方案资源管理器**，添加到了下列程序集的引用`Calc1Contract`项目：</span><span class="sxs-lookup"><span data-stu-id="a34ed-144">In **Solution Explorer**, add references to the following assemblies to the `Calc1Contract` project:</span></span>  
  
     <span data-ttu-id="a34ed-145">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="a34ed-145">System.AddIn.Contract.dll</span></span>  
  
     <span data-ttu-id="a34ed-146">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="a34ed-146">System.AddIn.dll</span></span>  
  
3.  <span data-ttu-id="a34ed-147">在**解决方案资源管理器**，排除添加到新的默认类**类库**项目。</span><span class="sxs-lookup"><span data-stu-id="a34ed-147">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects.</span></span>  
  
4.  <span data-ttu-id="a34ed-148">在**解决方案资源管理器**，将新项添加到项目中，使用**接口**模板。</span><span class="sxs-lookup"><span data-stu-id="a34ed-148">In **Solution Explorer**, add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="a34ed-149">在**添加新项**对话框中，名称接口`ICalc1Contract`。</span><span class="sxs-lookup"><span data-stu-id="a34ed-149">In the **Add New Item** dialog box, name the interface `ICalc1Contract`.</span></span>  
  
5.  <span data-ttu-id="a34ed-150">在接口文件中，添加到的命名空间引用<xref:System.AddIn.Contract>和<xref:System.AddIn.Pipeline>。</span><span class="sxs-lookup"><span data-stu-id="a34ed-150">In the interface file, add namespace references to <xref:System.AddIn.Contract> and <xref:System.AddIn.Pipeline>.</span></span>  
  
6.  <span data-ttu-id="a34ed-151">使用下面的代码来完成此合约段。</span><span class="sxs-lookup"><span data-stu-id="a34ed-151">Use the following code to complete this contract segment.</span></span> <span data-ttu-id="a34ed-152">请注意，此接口必须具有<xref:System.AddIn.Pipeline.AddInContractAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="a34ed-152">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInContractAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1Contract#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Contract/cs/ICalc1Contract.cs#1)]
     [!code-vb[AddInP1Contract#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Contract/vb/ICalc1Contract.vb#1)]  
  
7.  <span data-ttu-id="a34ed-153">（可选） 生成的 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="a34ed-153">Optionally, build the Visual Studio solution.</span></span> <span data-ttu-id="a34ed-154">无法运行该解决方案，直到最后的过程中，但之后的每个过程可确保每个项目都进行生成更正。</span><span class="sxs-lookup"><span data-stu-id="a34ed-154">The solution cannot be run until the final procedure, but building it after each procedure ensures that each project is correct.</span></span>  
  
 <span data-ttu-id="a34ed-155">由于外接程序视图和主机查看的外接程序通常具有相同的代码，尤其是在外接程序中的第一个版本，你可以轻松地在同一时间创建视图。</span><span class="sxs-lookup"><span data-stu-id="a34ed-155">Because the add-in view and the host view of the add-in usually have the same code, especially in the first version of an add-in, you can easily create the views at the same time.</span></span> <span data-ttu-id="a34ed-156">它们只能有一个方面不同： 外接程序中查看要求<xref:System.AddIn.Pipeline.AddInBaseAttribute>特性，尽管外接程序的主机视图不要求任何属性。</span><span class="sxs-lookup"><span data-stu-id="a34ed-156">They differ by only one factor: the add-in view requires the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute, while the host view of the add-in does not require any attributes.</span></span>  
  
#### <a name="to-create-the-add-in-view"></a><span data-ttu-id="a34ed-157">若要创建外接程序视图</span><span class="sxs-lookup"><span data-stu-id="a34ed-157">To create the add-in view</span></span>  
  
1.  <span data-ttu-id="a34ed-158">添加一个名为的新项目`Calc1AddInView`到`CalculatorV1`解决方案。</span><span class="sxs-lookup"><span data-stu-id="a34ed-158">Add a new project named `Calc1AddInView` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="a34ed-159">使该项目基于**类库**模板。</span><span class="sxs-lookup"><span data-stu-id="a34ed-159">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="a34ed-160">在**解决方案资源管理器**，添加引用到 System.AddIn.dll`Calc1AddInView`项目。</span><span class="sxs-lookup"><span data-stu-id="a34ed-160">In **Solution Explorer**, add a reference to System.AddIn.dll to the `Calc1AddInView` project.</span></span>  
  
3.  <span data-ttu-id="a34ed-161">在**解决方案资源管理器**，排除添加到新的默认类**类库**项目，并将新项添加到项目中，使用**接口**模板。</span><span class="sxs-lookup"><span data-stu-id="a34ed-161">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="a34ed-162">在**添加新项**对话框中，名称接口`ICalculator`。</span><span class="sxs-lookup"><span data-stu-id="a34ed-162">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
4.  <span data-ttu-id="a34ed-163">在接口文件中，添加对的命名空间引用<xref:System.AddIn.Pipeline>。</span><span class="sxs-lookup"><span data-stu-id="a34ed-163">In the interface file, add a namespace reference to <xref:System.AddIn.Pipeline>.</span></span>  
  
5.  <span data-ttu-id="a34ed-164">使用下面的代码来完成此外接程序视图。</span><span class="sxs-lookup"><span data-stu-id="a34ed-164">Use the following code to complete this add-in view.</span></span> <span data-ttu-id="a34ed-165">请注意，此接口必须具有<xref:System.AddIn.Pipeline.AddInBaseAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="a34ed-165">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1AddInViews#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInViews/cs/Calc1AddInView.cs#1)]
     [!code-vb[AddInP1AddInViews#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInViews/vb/Calc1AddInView.vb#1)]  
  
6.  <span data-ttu-id="a34ed-166">（可选） 生成的 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="a34ed-166">Optionally, build the Visual Studio solution.</span></span>  
  
#### <a name="to-create-the-host-view-of-the-add-in"></a><span data-ttu-id="a34ed-167">若要创建的外接程序的主机视图</span><span class="sxs-lookup"><span data-stu-id="a34ed-167">To create the host view of the add-in</span></span>  
  
1.  <span data-ttu-id="a34ed-168">添加一个名为的新项目`Calc1HVA`到`CalculatorV1`解决方案。</span><span class="sxs-lookup"><span data-stu-id="a34ed-168">Add a new project named `Calc1HVA` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="a34ed-169">使该项目基于**类库**模板。</span><span class="sxs-lookup"><span data-stu-id="a34ed-169">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="a34ed-170">在**解决方案资源管理器**，排除添加到新的默认类**类库**项目，并将新项添加到项目中，使用**接口**模板。</span><span class="sxs-lookup"><span data-stu-id="a34ed-170">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="a34ed-171">在**添加新项**对话框中，名称接口`ICalculator`。</span><span class="sxs-lookup"><span data-stu-id="a34ed-171">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
3.  <span data-ttu-id="a34ed-172">在接口文件中，使用下面的代码完成的外接程序的主机视图。</span><span class="sxs-lookup"><span data-stu-id="a34ed-172">In the interface file, use the following code to complete the host view of the add-in.</span></span>  
  
     [!code-csharp[AddInP1HVA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HVA/cs/calc1hva.cs#1)]
     [!code-vb[AddInP1HVA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HVA/vb/Calc1HVA.vb#1)]  
  
4.  <span data-ttu-id="a34ed-173">（可选） 生成的 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="a34ed-173">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in-side-adapter"></a><span data-ttu-id="a34ed-174">创建接程序端适配器</span><span class="sxs-lookup"><span data-stu-id="a34ed-174">Creating the Add-in-side Adapter</span></span>  
 <span data-ttu-id="a34ed-175">此接程序端适配器包含一个视图协定适配器。</span><span class="sxs-lookup"><span data-stu-id="a34ed-175">This add-in-side adapter consists of one view-to-contract adapter.</span></span> <span data-ttu-id="a34ed-176">此管道段将从外接程序视图的类型转换为协定中。</span><span class="sxs-lookup"><span data-stu-id="a34ed-176">This pipeline segment converts the types from the add-in view to the contract.</span></span>  
  
 <span data-ttu-id="a34ed-177">此管道中外接程序提供到主机，和服务类型从外接程序流到主机。</span><span class="sxs-lookup"><span data-stu-id="a34ed-177">In this pipeline, the add-in provides a service to the host, and the types flow from the add-in to the host.</span></span> <span data-ttu-id="a34ed-178">由于没有类型流向从主机到外接程序，你无需包含协定视图适配器一侧外接程序中的此管道。</span><span class="sxs-lookup"><span data-stu-id="a34ed-178">Because no types flow from the host to the add-in, you do not have to include a contract-to-view adapter on the add-in side of this pipeline.</span></span>  
  
#### <a name="to-create-the-add-in-side-adapter"></a><span data-ttu-id="a34ed-179">若要创建的外接程序端适配器</span><span class="sxs-lookup"><span data-stu-id="a34ed-179">To create the add-in-side adapter</span></span>  
  
1.  <span data-ttu-id="a34ed-180">添加一个名为的新项目`Calc1AddInSideAdapter`到`CalculatorV1`解决方案。</span><span class="sxs-lookup"><span data-stu-id="a34ed-180">Add a new project named `Calc1AddInSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="a34ed-181">使该项目基于**类库**模板。</span><span class="sxs-lookup"><span data-stu-id="a34ed-181">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="a34ed-182">在**解决方案资源管理器**，添加到了下列程序集的引用`Calc1AddInSideAdapter`项目：</span><span class="sxs-lookup"><span data-stu-id="a34ed-182">In **Solution Explorer**, add references to the following assemblies to the `Calc1AddInSideAdapter` project:</span></span>  
  
     <span data-ttu-id="a34ed-183">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="a34ed-183">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="a34ed-184">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="a34ed-184">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="a34ed-185">添加对相邻的管道段的项目的项目引用：</span><span class="sxs-lookup"><span data-stu-id="a34ed-185">Add project references to the projects for the adjacent pipeline segments:</span></span>  
  
     `Calc1AddInView`  
  
     `Calc1Contract`  
  
4.  <span data-ttu-id="a34ed-186">选择每个项目引用，然后在**属性**设置**Copy Local**到**False**。</span><span class="sxs-lookup"><span data-stu-id="a34ed-186">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="a34ed-187">在 Visual Basic 中，使用**引用**选项卡**项目属性**设置**Copy Local**到**False**的两个项目的引用。</span><span class="sxs-lookup"><span data-stu-id="a34ed-187">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="a34ed-188">重命名项目的默认类`CalculatorViewToContractAddInSideAdapter`。</span><span class="sxs-lookup"><span data-stu-id="a34ed-188">Rename the project's default class `CalculatorViewToContractAddInSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="a34ed-189">在类文件中，添加到的命名空间引用<xref:System.AddIn.Pipeline>。</span><span class="sxs-lookup"><span data-stu-id="a34ed-189">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="a34ed-190">在类文件中，添加相邻的段的命名空间引用：`CalcAddInViews`和`CalculatorContracts`。</span><span class="sxs-lookup"><span data-stu-id="a34ed-190">In the class file, add namespace references for the adjacent segments: `CalcAddInViews` and `CalculatorContracts`.</span></span> <span data-ttu-id="a34ed-191">(在 Visual Basic 中，可以这些命名空间引用`Calc1AddInView.CalcAddInViews`和`Calc1Contract.CalculatorContracts`，除非是关闭 Visual Basic 项目中的默认命名空间。)</span><span class="sxs-lookup"><span data-stu-id="a34ed-191">(In Visual Basic, these namespace references are `Calc1AddInView.CalcAddInViews` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="a34ed-192">应用<xref:System.AddIn.Pipeline.AddInAdapterAttribute>属性设为`CalculatorViewToContractAddInSideAdapter`类中，以标识为外接程序端适配器。</span><span class="sxs-lookup"><span data-stu-id="a34ed-192">Apply the <xref:System.AddIn.Pipeline.AddInAdapterAttribute> attribute to the `CalculatorViewToContractAddInSideAdapter` class, to identify it as the add-in-side adapter.</span></span>  
  
9. <span data-ttu-id="a34ed-193">请`CalculatorViewToContractAddInSideAdapter`类继承<xref:System.AddIn.Pipeline.ContractBase>，该属性提供的默认实现<xref:System.AddIn.Contract.IContract>接口，并实现管道，协定接口`ICalc1Contract`。</span><span class="sxs-lookup"><span data-stu-id="a34ed-193">Make the `CalculatorViewToContractAddInSideAdapter` class inherit <xref:System.AddIn.Pipeline.ContractBase>, which provides a default implementation of the <xref:System.AddIn.Contract.IContract> interface, and implement the contract interface for the pipeline, `ICalc1Contract`.</span></span>  
  
10. <span data-ttu-id="a34ed-194">添加一个公共构造函数接受的`ICalculator`，在私有字段中，对其进行缓存并调用基类构造函数。</span><span class="sxs-lookup"><span data-stu-id="a34ed-194">Add a public constructor that accepts an `ICalculator`, caches it in a private field, and calls the base class constructor.</span></span>  
  
11. <span data-ttu-id="a34ed-195">若要实现的成员`ICalc1Contract`，只需调用的对应成员`ICalculator`传递给构造函数中，并返回结果的实例。</span><span class="sxs-lookup"><span data-stu-id="a34ed-195">To implement the members of `ICalc1Contract`, simply call the corresponding members of the `ICalculator` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="a34ed-196">这使视图 (`ICalculator`) 到协定 (`ICalc1Contract`)。</span><span class="sxs-lookup"><span data-stu-id="a34ed-196">This adapts the view (`ICalculator`) to the contract (`ICalc1Contract`).</span></span>  
  
     <span data-ttu-id="a34ed-197">下面的代码显示已完成的接程序端适配器。</span><span class="sxs-lookup"><span data-stu-id="a34ed-197">The following code shows the completed add-in-side adapter.</span></span>  
  
     [!code-csharp[AddInP1AddInSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInSideAdapters/cs/Calc1ViewToContractAddInSideAdapter.cs#1)]
     [!code-vb[AddInP1AddInSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInSideAdapters/vb/Calc1ViewToContractAddInSideAdapter.vb#1)]  
  
12. <span data-ttu-id="a34ed-198">（可选） 生成的 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="a34ed-198">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host-side-adapter"></a><span data-ttu-id="a34ed-199">创建主机端适配器</span><span class="sxs-lookup"><span data-stu-id="a34ed-199">Creating the Host-side Adapter</span></span>  
 <span data-ttu-id="a34ed-200">此主机端适配器包含一个协定视图适配器。</span><span class="sxs-lookup"><span data-stu-id="a34ed-200">This host-side adapter consists of one contract-to-view adapter.</span></span> <span data-ttu-id="a34ed-201">此段采用的外接程序的主机视图的协定。</span><span class="sxs-lookup"><span data-stu-id="a34ed-201">This segment adapts the contract to the host view of the add-in.</span></span>  
  
 <span data-ttu-id="a34ed-202">此管道中外接程序提供服务对主机和类型流从外接程序到主机。</span><span class="sxs-lookup"><span data-stu-id="a34ed-202">In this pipeline, the add-in provides a service to the host and the types flow from the add-in to the host.</span></span> <span data-ttu-id="a34ed-203">由于没有类型流向从主机到外接程序，你无需包括视图协定适配器。</span><span class="sxs-lookup"><span data-stu-id="a34ed-203">Because no types flow from the host to the add-in, you do not have to include a view-to-contract adapter.</span></span>  
  
 <span data-ttu-id="a34ed-204">若要实现生存期管理，使用<xref:System.AddIn.Pipeline.ContractHandle>对象以将生存期令牌附加到的协定。</span><span class="sxs-lookup"><span data-stu-id="a34ed-204">To implement lifetime management, use a <xref:System.AddIn.Pipeline.ContractHandle> object to attach a lifetime token to the contract.</span></span> <span data-ttu-id="a34ed-205">按顺序生存期管理工作，必须保持对此句柄的引用。</span><span class="sxs-lookup"><span data-stu-id="a34ed-205">You must keep a reference to this handle in order for lifetime management to work.</span></span> <span data-ttu-id="a34ed-206">应用令牌后，无需任何其他编程是必需的因为外接程序系统可以的对象时释放它们不再使用，并使它们可供垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="a34ed-206">After the token is applied, no additional programming is required because the add-in system can dispose of objects when they are no longer being used and make them available for garbage collection.</span></span> <span data-ttu-id="a34ed-207">有关详细信息，请参阅 [生存期管理](http://msdn.microsoft.com/en-us/57a9c87e-394c-4fef-89f2-aa4223a2aeb5)。</span><span class="sxs-lookup"><span data-stu-id="a34ed-207">For more information, see [Lifetime Management](http://msdn.microsoft.com/en-us/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span></span>  
  
#### <a name="to-create-the-host-side-adapter"></a><span data-ttu-id="a34ed-208">若要创建的主机端适配器</span><span class="sxs-lookup"><span data-stu-id="a34ed-208">To create the host-side adapter</span></span>  
  
1.  <span data-ttu-id="a34ed-209">添加一个名为的新项目`Calc1HostSideAdapter`到`CalculatorV1`解决方案。</span><span class="sxs-lookup"><span data-stu-id="a34ed-209">Add a new project named `Calc1HostSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="a34ed-210">使该项目基于**类库**模板。</span><span class="sxs-lookup"><span data-stu-id="a34ed-210">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="a34ed-211">在**解决方案资源管理器**，添加到了下列程序集的引用`Calc1HostSideAdapter`项目：</span><span class="sxs-lookup"><span data-stu-id="a34ed-211">In **Solution Explorer**, add references to the following assemblies to the `Calc1HostSideAdapter` project:</span></span>  
  
     <span data-ttu-id="a34ed-212">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="a34ed-212">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="a34ed-213">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="a34ed-213">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="a34ed-214">添加对相邻的段的项目的项目引用：</span><span class="sxs-lookup"><span data-stu-id="a34ed-214">Add project references to the projects for the adjacent segments:</span></span>  
  
     `Calc1Contract`  
  
     `Calc1HVA`  
  
4.  <span data-ttu-id="a34ed-215">选择每个项目引用，然后在**属性**设置**Copy Local**到**False**。</span><span class="sxs-lookup"><span data-stu-id="a34ed-215">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="a34ed-216">在 Visual Basic 中，使用**引用**选项卡**项目属性**设置**Copy Local**到**False**的两个项目的引用。</span><span class="sxs-lookup"><span data-stu-id="a34ed-216">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="a34ed-217">重命名项目的默认类`CalculatorContractToViewHostSideAdapter`。</span><span class="sxs-lookup"><span data-stu-id="a34ed-217">Rename the project's default class `CalculatorContractToViewHostSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="a34ed-218">在类文件中，添加到的命名空间引用<xref:System.AddIn.Pipeline>。</span><span class="sxs-lookup"><span data-stu-id="a34ed-218">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="a34ed-219">在类文件中，添加相邻的段的命名空间引用：`CalcHVAs`和`CalculatorContracts`。</span><span class="sxs-lookup"><span data-stu-id="a34ed-219">In the class file, add namespace references for the adjacent segments: `CalcHVAs` and `CalculatorContracts`.</span></span> <span data-ttu-id="a34ed-220">(在 Visual Basic 中，可以这些命名空间引用`Calc1HVA.CalcHVAs`和`Calc1Contract.CalculatorContracts`，除非是关闭 Visual Basic 项目中的默认命名空间。)</span><span class="sxs-lookup"><span data-stu-id="a34ed-220">(In Visual Basic, these namespace references are `Calc1HVA.CalcHVAs` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="a34ed-221">应用<xref:System.AddIn.Pipeline.HostAdapterAttribute>属性设为`CalculatorContractToViewHostSideAdapter`类中，以标识为宿主端适配器段。</span><span class="sxs-lookup"><span data-stu-id="a34ed-221">Apply the <xref:System.AddIn.Pipeline.HostAdapterAttribute> attribute to the `CalculatorContractToViewHostSideAdapter` class, to identify it as the host-side adapter segment.</span></span>  
  
9. <span data-ttu-id="a34ed-222">请`CalculatorContractToViewHostSideAdapter`类实现接口表示外接程序的主机视图： `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator`在 Visual Basic 中)。</span><span class="sxs-lookup"><span data-stu-id="a34ed-222">Make the `CalculatorContractToViewHostSideAdapter` class implement the interface that represents the host view of the add-in: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` in Visual Basic).</span></span>  
  
10. <span data-ttu-id="a34ed-223">添加一个公共构造函数，以接受管道协定类型， `ICalc1Contract`。</span><span class="sxs-lookup"><span data-stu-id="a34ed-223">Add a public constructor that accepts the pipeline contract type, `ICalc1Contract`.</span></span> <span data-ttu-id="a34ed-224">构造函数必须缓存对协定的引用。</span><span class="sxs-lookup"><span data-stu-id="a34ed-224">The constructor must cache the reference to the contract.</span></span> <span data-ttu-id="a34ed-225">它还必须创建并缓存新<xref:System.AddIn.Pipeline.ContractHandle>对于协定，若要管理的外接程序的生存期。</span><span class="sxs-lookup"><span data-stu-id="a34ed-225">It must also create and cache a new <xref:System.AddIn.Pipeline.ContractHandle> for the contract, to manage the lifetime of the add-in.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a34ed-226"><xref:System.AddIn.Pipeline.ContractHandle>至关重要生命期管理。</span><span class="sxs-lookup"><span data-stu-id="a34ed-226">The <xref:System.AddIn.Pipeline.ContractHandle> is critical to lifetime management.</span></span> <span data-ttu-id="a34ed-227">如果您不能保持对引用<xref:System.AddIn.Pipeline.ContractHandle>对象，垃圾回收将回收，以及当你的程序不需要其管道将关闭。</span><span class="sxs-lookup"><span data-stu-id="a34ed-227">If you fail to keep a reference to the <xref:System.AddIn.Pipeline.ContractHandle> object, garbage collection will reclaim it, and the pipeline will shut down when your program does not expect it.</span></span> <span data-ttu-id="a34ed-228">这可能导致的错误很难诊断，如<xref:System.AppDomainUnloadedException>。</span><span class="sxs-lookup"><span data-stu-id="a34ed-228">This can lead to errors that are difficult to diagnose, such as <xref:System.AppDomainUnloadedException>.</span></span> <span data-ttu-id="a34ed-229">关闭是管道的生活中，正常阶段，因此没有检测到这种情况是管道的错误的生存期管理代码的方法。</span><span class="sxs-lookup"><span data-stu-id="a34ed-229">Shutdown is a normal stage in the life of a pipeline, so there is no way for the lifetime management code to detect that this condition is an error.</span></span>  
  
11. <span data-ttu-id="a34ed-230">若要实现的成员`ICalculator`，只需调用的对应成员`ICalc1Contract`传递给构造函数中，并返回结果的实例。</span><span class="sxs-lookup"><span data-stu-id="a34ed-230">To implement the members of `ICalculator`, simply call the corresponding members of the `ICalc1Contract` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="a34ed-231">这使协定 (`ICalc1Contract`) 到视图 (`ICalculator`)。</span><span class="sxs-lookup"><span data-stu-id="a34ed-231">This adapts the contract (`ICalc1Contract`) to the view (`ICalculator`).</span></span>  
  
     <span data-ttu-id="a34ed-232">下面的代码显示已完成的主机端适配器。</span><span class="sxs-lookup"><span data-stu-id="a34ed-232">The following code shows the completed host-side adapter.</span></span>  
  
     [!code-csharp[AddInP1HostSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HostSideAdapters/cs/Calc1ContractToViewHostSideAdapter.cs#1)]
     [!code-vb[AddInP1HostSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HostSideAdapters/vb/Calc1ContractToViewHostSideAdapter.vb#1)]  
  
12. <span data-ttu-id="a34ed-233">（可选） 生成的 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="a34ed-233">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host"></a><span data-ttu-id="a34ed-234">创建主机</span><span class="sxs-lookup"><span data-stu-id="a34ed-234">Creating the Host</span></span>  
 <span data-ttu-id="a34ed-235">将主机应用程序交互与外接程序通过外接程序的主机视图。</span><span class="sxs-lookup"><span data-stu-id="a34ed-235">A host application interacts with the add-in through the host view of the add-in.</span></span> <span data-ttu-id="a34ed-236">它使用外接程序发现和激活方法提供的<xref:System.AddIn.Hosting.AddInStore>和<xref:System.AddIn.Hosting.AddInToken>类来执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a34ed-236">It uses add-in discovery and activation methods provided by the <xref:System.AddIn.Hosting.AddInStore> and <xref:System.AddIn.Hosting.AddInToken> classes to do the following:</span></span>  
  
-   <span data-ttu-id="a34ed-237">更新管道和外接程序信息的缓存。</span><span class="sxs-lookup"><span data-stu-id="a34ed-237">Update the cache of pipeline and add-in information.</span></span>  
  
-   <span data-ttu-id="a34ed-238">查找宿主视图类型的加载项`ICalculator`，指定的管道根目录下。</span><span class="sxs-lookup"><span data-stu-id="a34ed-238">Find add-ins of the host view type, `ICalculator`, under the specified pipeline root directory.</span></span>  
  
-   <span data-ttu-id="a34ed-239">提示用户指定的外接程序使用。</span><span class="sxs-lookup"><span data-stu-id="a34ed-239">Prompt the user to specify which add-in to use.</span></span>  
  
-   <span data-ttu-id="a34ed-240">激活的所选外接程序中具有指定的安全信任级别的新应用程序域。</span><span class="sxs-lookup"><span data-stu-id="a34ed-240">Activate the selected add-in in a new application domain with a specified security trust level.</span></span>  
  
-   <span data-ttu-id="a34ed-241">运行自定义`RunCalculator`方法，调用指定的外接程序的主机视图的外接程序的方法。</span><span class="sxs-lookup"><span data-stu-id="a34ed-241">Run the custom `RunCalculator` method, which calls the add-in's methods as specified by the host view of the add-in.</span></span>  
  
#### <a name="to-create-the-host"></a><span data-ttu-id="a34ed-242">若要创建的主机</span><span class="sxs-lookup"><span data-stu-id="a34ed-242">To create the host</span></span>  
  
1.  <span data-ttu-id="a34ed-243">添加一个名为的新项目`Calc1Host`到`CalculatorV1`解决方案。</span><span class="sxs-lookup"><span data-stu-id="a34ed-243">Add a new project named `Calc1Host` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="a34ed-244">使该项目基于**控制台应用程序**模板。</span><span class="sxs-lookup"><span data-stu-id="a34ed-244">Base it on the **Console Application** template.</span></span>  
  
2.  <span data-ttu-id="a34ed-245">在**解决方案资源管理器**，添加到 System.AddIn.dll 程序集的引用`Calc1Host`项目。</span><span class="sxs-lookup"><span data-stu-id="a34ed-245">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the `Calc1Host` project.</span></span>  
  
3.  <span data-ttu-id="a34ed-246">添加到项目引用`Calc1HVA`项目。</span><span class="sxs-lookup"><span data-stu-id="a34ed-246">Add a project reference to the `Calc1HVA` project.</span></span> <span data-ttu-id="a34ed-247">选择该项目引用，然后在**属性**设置**Copy Local**到**False**。</span><span class="sxs-lookup"><span data-stu-id="a34ed-247">Select the project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="a34ed-248">在 Visual Basic 中，使用**引用**选项卡**项目属性**设置**Copy Local**到**False**。</span><span class="sxs-lookup"><span data-stu-id="a34ed-248">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False**.</span></span>  
  
4.  <span data-ttu-id="a34ed-249">重命名类文件 （在 Visual Basic 中的模块） `MathHost1`。</span><span class="sxs-lookup"><span data-stu-id="a34ed-249">Rename the class file (module in Visual Basic) `MathHost1`.</span></span>  
  
5.  <span data-ttu-id="a34ed-250">在 Visual Basic 中，使用**应用程序**选项卡**项目属性**对话框可设置**启动对象**到**Sub Main**。</span><span class="sxs-lookup"><span data-stu-id="a34ed-250">In Visual Basic, use the **Application** tab of the **Project Properties** dialog box to set **Startup object** to **Sub Main**.</span></span>  
  
6.  <span data-ttu-id="a34ed-251">在类或模块文件中，添加对的命名空间引用<xref:System.AddIn.Hosting>。</span><span class="sxs-lookup"><span data-stu-id="a34ed-251">In the class or module file, add a namespace reference to <xref:System.AddIn.Hosting>.</span></span>  
  
7.  <span data-ttu-id="a34ed-252">在类或模块文件中，添加的外接程序的主机视图的命名空间引用： `CalcHVAs`。</span><span class="sxs-lookup"><span data-stu-id="a34ed-252">In the class or module file, add a namespace reference for the host view of the add-in: `CalcHVAs`.</span></span> <span data-ttu-id="a34ed-253">(在 Visual Basic 中，此命名空间引用是`Calc1HVA.CalcHVAs`，除非是关闭 Visual Basic 项目中的默认命名空间。)</span><span class="sxs-lookup"><span data-stu-id="a34ed-253">(In Visual Basic, this namespace reference is `Calc1HVA.CalcHVAs`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="a34ed-254">在**解决方案资源管理器**，选择解决方案并从**项目**菜单中，选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="a34ed-254">In **Solution Explorer**, select the solution and from the **Project** menu choose **Properties**.</span></span> <span data-ttu-id="a34ed-255">在**解决方案属性页**对话框中，设置**单启动项目**为此主机应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="a34ed-255">In the **Solution Property Pages** dialog box, set the **Single Startup Project** to be this host application project.</span></span>  
  
9. <span data-ttu-id="a34ed-256">在类或模块文件中，使用<xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType>方法来更新缓存。</span><span class="sxs-lookup"><span data-stu-id="a34ed-256">In the class or module file, use the <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> method to update the cache.</span></span> <span data-ttu-id="a34ed-257">使用<xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType>方法以获取令牌的集合，并使用<xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType>方法以激活外接程序。</span><span class="sxs-lookup"><span data-stu-id="a34ed-257">Use the <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> method to get a collection of tokens, and use the <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> method to activate an add-in.</span></span>  
  
     <span data-ttu-id="a34ed-258">下面的代码显示已完成的宿主应用程序。</span><span class="sxs-lookup"><span data-stu-id="a34ed-258">The following code shows the completed host application.</span></span>  
  
     [!code-csharp[AddInP1Host#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Host/cs/MathHost1.cs#1)]
     [!code-vb[AddInP1Host#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Host/vb/MathHost1.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="a34ed-259">此代码假定管道文件夹结构位于应用程序文件夹。</span><span class="sxs-lookup"><span data-stu-id="a34ed-259">This code assumes that the pipeline folder structure is located in the application folder.</span></span> <span data-ttu-id="a34ed-260">如果在其他位置位于，更改的设置的代码行`addInRoot`变量，以便该变量包含管线目录结构的路径。</span><span class="sxs-lookup"><span data-stu-id="a34ed-260">If you located it elsewhere, change the line of code that sets the `addInRoot` variable, so that the variable contains the path to your pipeline directory structure.</span></span>  
  
     <span data-ttu-id="a34ed-261">该代码使用`ChooseCalculator`方法来列出标记，并提示用户选择外接程序。</span><span class="sxs-lookup"><span data-stu-id="a34ed-261">The code uses a `ChooseCalculator` method to list the tokens and to prompt the user to choose an add-in.</span></span> <span data-ttu-id="a34ed-262">`RunCalculator`方法提示用户提供简单的数学表达式、 分析使用的表达式`Parser`类，并显示返回的结果外接程序。</span><span class="sxs-lookup"><span data-stu-id="a34ed-262">The `RunCalculator` method prompts the user for simple math expressions, parses the expressions using the `Parser` class, and displays the results returned by the add-in.</span></span>  
  
10. <span data-ttu-id="a34ed-263">（可选） 生成的 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="a34ed-263">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in"></a><span data-ttu-id="a34ed-264">创建的外接程序</span><span class="sxs-lookup"><span data-stu-id="a34ed-264">Creating the Add-In</span></span>  
 <span data-ttu-id="a34ed-265">外接程序中实现指定的外接程序视图的方法。</span><span class="sxs-lookup"><span data-stu-id="a34ed-265">An add-in implements the methods specified by the add-in view.</span></span> <span data-ttu-id="a34ed-266">此外接程序实现`Add`， `Subtract`， `Multiply`，和`Divide`操作并将结果返回给主机。</span><span class="sxs-lookup"><span data-stu-id="a34ed-266">This add-in implements the `Add`, `Subtract`, `Multiply`, and `Divide` operations and returns the results to the host.</span></span>  
  
#### <a name="to-create-the-add-in"></a><span data-ttu-id="a34ed-267">若要创建外接程序</span><span class="sxs-lookup"><span data-stu-id="a34ed-267">To create the add-in</span></span>  
  
1.  <span data-ttu-id="a34ed-268">添加一个名为的新项目`AddInCalcV1`到`CalculatorV1`解决方案。</span><span class="sxs-lookup"><span data-stu-id="a34ed-268">Add a new project named `AddInCalcV1` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="a34ed-269">使该项目基于**类库**模板。</span><span class="sxs-lookup"><span data-stu-id="a34ed-269">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="a34ed-270">在**解决方案资源管理器**，向项目添加 System.AddIn.dll 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="a34ed-270">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the project.</span></span>  
  
3.  <span data-ttu-id="a34ed-271">添加到项目引用`Calc1AddInView`项目。</span><span class="sxs-lookup"><span data-stu-id="a34ed-271">Add a project reference to the `Calc1AddInView` project.</span></span> <span data-ttu-id="a34ed-272">选择该项目引用，然后在**属性**，将其设置**Copy Local**到**False**。</span><span class="sxs-lookup"><span data-stu-id="a34ed-272">Select the project reference, and in **Properties**, set **Copy Local** to **False**.</span></span> <span data-ttu-id="a34ed-273">在 Visual Basic 中，使用**引用**选项卡**项目属性**设置**Copy Local**到**False**项目引用。</span><span class="sxs-lookup"><span data-stu-id="a34ed-273">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the project reference.</span></span>  
  
4.  <span data-ttu-id="a34ed-274">重命名类`AddInCalcV1`。</span><span class="sxs-lookup"><span data-stu-id="a34ed-274">Rename the class `AddInCalcV1`.</span></span>  
  
5.  <span data-ttu-id="a34ed-275">在类文件中，添加对的命名空间引用<xref:System.AddIn>和外接程序视图分段： `CalcAddInViews` (`Calc1AddInView.CalcAddInViews`在 Visual Basic 中)。</span><span class="sxs-lookup"><span data-stu-id="a34ed-275">In the class file, add a namespace reference to <xref:System.AddIn> and the add-in view segment: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` in Visual Basic).</span></span>  
  
6.  <span data-ttu-id="a34ed-276">应用<xref:System.AddIn.AddInAttribute>属性设为`AddInCalcV1`类中，以将类标识为外接程序。</span><span class="sxs-lookup"><span data-stu-id="a34ed-276">Apply the <xref:System.AddIn.AddInAttribute> attribute to the `AddInCalcV1` class, to identify the class as an add-in.</span></span>  
  
7.  <span data-ttu-id="a34ed-277">请`AddInCalcV1`类实现接口表示外接程序视图： `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator`在 Visual Basic 中)。</span><span class="sxs-lookup"><span data-stu-id="a34ed-277">Make the `AddInCalcV1` class implement the interface that represents the add-in view: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` in Visual Basic).</span></span>  
  
8.  <span data-ttu-id="a34ed-278">实现的成员`ICalculator`通过返回相应的计算的结果。</span><span class="sxs-lookup"><span data-stu-id="a34ed-278">Implement the members of `ICalculator` by returning the results of the appropriate calculations.</span></span>  
  
     <span data-ttu-id="a34ed-279">下面的代码演示的已完成外接程序。</span><span class="sxs-lookup"><span data-stu-id="a34ed-279">The following code shows the completed add-in.</span></span>  
  
     [!code-csharp[AddInP1AddInCalcV1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInCalcV1/cs/AddInCalcV1.cs#1)]
     [!code-vb[AddInP1AddInCalcV1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInCalcV1/vb/AddInCalcV1.vb#1)]  
  
9. <span data-ttu-id="a34ed-280">（可选） 生成的 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="a34ed-280">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="deploying-the-pipeline"></a><span data-ttu-id="a34ed-281">部署管道</span><span class="sxs-lookup"><span data-stu-id="a34ed-281">Deploying the Pipeline</span></span>  
 <span data-ttu-id="a34ed-282">现在你就可以生成并部署到所需的管线目录结构的外接程序段。</span><span class="sxs-lookup"><span data-stu-id="a34ed-282">You are now ready to build and deploy the add-in segments to the required pipeline directory structure.</span></span>  
  
#### <a name="to-deploy-the-segments-to-the-pipeline"></a><span data-ttu-id="a34ed-283">若要将段部署到管道</span><span class="sxs-lookup"><span data-stu-id="a34ed-283">To deploy the segments to the pipeline</span></span>  
  
1.  <span data-ttu-id="a34ed-284">对于每个项目解决方案中，使用**生成**选项卡**项目属性**(**编译**在 Visual Basic 中的选项卡) 若要设置的值**输出路径** (**生成输出路径**在 Visual Basic 中)。</span><span class="sxs-lookup"><span data-stu-id="a34ed-284">For each project in the solution, use the **Build** tab of **Project Properties** (the **Compile** tab in Visual Basic) to set the value of the **Output path** (the **Build output path** in Visual Basic).</span></span> <span data-ttu-id="a34ed-285">如果名为应用程序文件夹`MyApp`，例如，你的项目将生成到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="a34ed-285">If you named your application folder `MyApp`, for example, your projects would build into the following folders:</span></span>  
  
    |<span data-ttu-id="a34ed-286">Project</span><span class="sxs-lookup"><span data-stu-id="a34ed-286">Project</span></span>|<span data-ttu-id="a34ed-287">路径</span><span class="sxs-lookup"><span data-stu-id="a34ed-287">Path</span></span>|  
    |-------------|----------|  
    |<span data-ttu-id="a34ed-288">AddInCalcV1</span><span class="sxs-lookup"><span data-stu-id="a34ed-288">AddInCalcV1</span></span>|<span data-ttu-id="a34ed-289">MyApp\Pipeline\AddIns\CalcV1</span><span class="sxs-lookup"><span data-stu-id="a34ed-289">MyApp\Pipeline\AddIns\CalcV1</span></span>|  
    |<span data-ttu-id="a34ed-290">Calc1AddInSideAdapter</span><span class="sxs-lookup"><span data-stu-id="a34ed-290">Calc1AddInSideAdapter</span></span>|<span data-ttu-id="a34ed-291">MyApp\Pipeline\AddInSideAdapters</span><span class="sxs-lookup"><span data-stu-id="a34ed-291">MyApp\Pipeline\AddInSideAdapters</span></span>|  
    |<span data-ttu-id="a34ed-292">Calc1AddInView</span><span class="sxs-lookup"><span data-stu-id="a34ed-292">Calc1AddInView</span></span>|<span data-ttu-id="a34ed-293">MyApp\Pipeline\AddInViews</span><span class="sxs-lookup"><span data-stu-id="a34ed-293">MyApp\Pipeline\AddInViews</span></span>|  
    |<span data-ttu-id="a34ed-294">Calc1Contract</span><span class="sxs-lookup"><span data-stu-id="a34ed-294">Calc1Contract</span></span>|<span data-ttu-id="a34ed-295">MyApp\Pipeline\Contracts</span><span class="sxs-lookup"><span data-stu-id="a34ed-295">MyApp\Pipeline\Contracts</span></span>|  
    |<span data-ttu-id="a34ed-296">Calc1Host</span><span class="sxs-lookup"><span data-stu-id="a34ed-296">Calc1Host</span></span>|<span data-ttu-id="a34ed-297">MyApp</span><span class="sxs-lookup"><span data-stu-id="a34ed-297">MyApp</span></span>|  
    |<span data-ttu-id="a34ed-298">Calc1HostSideAdapter</span><span class="sxs-lookup"><span data-stu-id="a34ed-298">Calc1HostSideAdapter</span></span>|<span data-ttu-id="a34ed-299">MyApp\Pipeline\HostSideAdapters</span><span class="sxs-lookup"><span data-stu-id="a34ed-299">MyApp\Pipeline\HostSideAdapters</span></span>|  
    |<span data-ttu-id="a34ed-300">Calc1HVA</span><span class="sxs-lookup"><span data-stu-id="a34ed-300">Calc1HVA</span></span>|<span data-ttu-id="a34ed-301">MyApp</span><span class="sxs-lookup"><span data-stu-id="a34ed-301">MyApp</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="a34ed-302">如果你决定将管道文件夹结构放在应用程序文件夹以外的位置，则必须修改相应的表所示的路径。</span><span class="sxs-lookup"><span data-stu-id="a34ed-302">If you decided to put your pipeline folder structure in a location other than your application folder, you must modify the paths shown in the table accordingly.</span></span> <span data-ttu-id="a34ed-303">请参阅中的管道 directory 要求讨论[管线开发要求](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)。</span><span class="sxs-lookup"><span data-stu-id="a34ed-303">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
2.  <span data-ttu-id="a34ed-304">生成 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="a34ed-304">Build the Visual Studio solution.</span></span>  
  
3.  <span data-ttu-id="a34ed-305">检查应用程序和管线目录，以确保程序集已复制到正确的目录，并在错误的文件夹已安装的程序集的任何额外副本。</span><span class="sxs-lookup"><span data-stu-id="a34ed-305">Check the application and pipeline directories to ensure that the assemblies were copied to the correct directories and that no extra copies of assemblies were installed in the wrong folders.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a34ed-306">如果你并未更改**Copy Local**到**False**为`Calc1AddInView`项目中的引用`AddInCalcV1`项目中，加载程序上下文问题将阻止外接程序位于。</span><span class="sxs-lookup"><span data-stu-id="a34ed-306">If you did not change **Copy Local** to **False** for the `Calc1AddInView` project reference in the `AddInCalcV1` project, loader context problems will prevent the add-in from being located.</span></span>  
  
     <span data-ttu-id="a34ed-307">有关将部署到管道的信息，请参阅[管线开发要求](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)。</span><span class="sxs-lookup"><span data-stu-id="a34ed-307">For information about deploying to the pipeline, see [Pipeline Development Requirements](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
## <a name="running-the-host-application"></a><span data-ttu-id="a34ed-308">运行主机应用程序</span><span class="sxs-lookup"><span data-stu-id="a34ed-308">Running the Host Application</span></span>  
 <span data-ttu-id="a34ed-309">现在你就可以运行主机并与外接程序进行交互。</span><span class="sxs-lookup"><span data-stu-id="a34ed-309">You are now ready to run the host and interact with the add-in.</span></span>  
  
#### <a name="to-run-the-host-application"></a><span data-ttu-id="a34ed-310">若要运行主机应用程序</span><span class="sxs-lookup"><span data-stu-id="a34ed-310">To run the host application</span></span>  
  
1.  <span data-ttu-id="a34ed-311">在命令提示符处，转到应用程序目录并运行主机应用程序， `Calc1Host.exe`。</span><span class="sxs-lookup"><span data-stu-id="a34ed-311">At the command prompt, go to the application directory and run the host application, `Calc1Host.exe`.</span></span>  
  
2.  <span data-ttu-id="a34ed-312">主机查找所有可用外接其类型，并提示您选择外接程序。</span><span class="sxs-lookup"><span data-stu-id="a34ed-312">The host finds all available add-ins of its type and prompts you to select an add-in.</span></span> <span data-ttu-id="a34ed-313">输入**1**的唯一可用外接程序。</span><span class="sxs-lookup"><span data-stu-id="a34ed-313">Enter **1** for the only available add-in.</span></span>  
  
3.  <span data-ttu-id="a34ed-314">输入的公式为计算器，如**2 + 2**。</span><span class="sxs-lookup"><span data-stu-id="a34ed-314">Enter an equation for the calculator, such as **2 + 2**.</span></span> <span data-ttu-id="a34ed-315">必须有数字和运算符之间的空格。</span><span class="sxs-lookup"><span data-stu-id="a34ed-315">There must be spaces between the numbers and the operator.</span></span>  
  
4.  <span data-ttu-id="a34ed-316">类型**退出**按**Enter**键关闭应用程序。</span><span class="sxs-lookup"><span data-stu-id="a34ed-316">Type **exit** and press the **Enter** key to close the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a34ed-317">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a34ed-317">See Also</span></span>  
 [<span data-ttu-id="a34ed-318">演练： 启用主机更改为向后的兼容性</span><span class="sxs-lookup"><span data-stu-id="a34ed-318">Walkthrough: Enabling Backward Compatibility as Your Host Changes</span></span>](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
 [<span data-ttu-id="a34ed-319">主机和外接程序之间的演练： 传递集合</span><span class="sxs-lookup"><span data-stu-id="a34ed-319">Walkthrough: Passing Collections Between Hosts and Add-Ins</span></span>](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5)  
 [<span data-ttu-id="a34ed-320">管线开发要求</span><span class="sxs-lookup"><span data-stu-id="a34ed-320">Pipeline Development Requirements</span></span>](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)  
 [<span data-ttu-id="a34ed-321">协定、 视图和适配器</span><span class="sxs-lookup"><span data-stu-id="a34ed-321">Contracts, Views, and Adapters</span></span>](http://msdn.microsoft.com/en-us/a6460173-9507-4b87-8c07-d4ee245d715c)  
 [<span data-ttu-id="a34ed-322">Pipeline Development</span><span class="sxs-lookup"><span data-stu-id="a34ed-322">Pipeline Development</span></span>](../../../docs/framework/add-ins/pipeline-development.md)
