---
title: 演练：创建可扩展的应用程序
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d2aaeaffaf3abbe1e8efcdb57d40e6ae60f89b5
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44197576"
---
# <a name="walkthrough-creating-an-extensible-application"></a><span data-ttu-id="524fc-102">演练：创建可扩展的应用程序</span><span class="sxs-lookup"><span data-stu-id="524fc-102">Walkthrough: Creating an Extensible Application</span></span>
<span data-ttu-id="524fc-103">本演练介绍如何创建用于执行简单的计算器功能的外接程序的管道。</span><span class="sxs-lookup"><span data-stu-id="524fc-103">This walkthrough describes how to create a pipeline for an add-in that performs simple calculator functions.</span></span> <span data-ttu-id="524fc-104">它并不演示实际方案中;相反，它演示了一个管道，以及如何外接程序可以提供主机服务的基本功能。</span><span class="sxs-lookup"><span data-stu-id="524fc-104">It does not demonstrate a real-world scenario; rather, it demonstrates the basic functionality of a pipeline and how an add-in can provide services for a host.</span></span>  
  
 <span data-ttu-id="524fc-105">本演练介绍了以下任务：</span><span class="sxs-lookup"><span data-stu-id="524fc-105">This walkthrough describes the following tasks:</span></span>  
  
-   <span data-ttu-id="524fc-106">创建一个 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="524fc-106">Creating a Visual Studio solution.</span></span>  
  
-   <span data-ttu-id="524fc-107">正在创建管线目录结构。</span><span class="sxs-lookup"><span data-stu-id="524fc-107">Creating the pipeline directory structure.</span></span>  
  
-   <span data-ttu-id="524fc-108">正在创建的协定和视图。</span><span class="sxs-lookup"><span data-stu-id="524fc-108">Creating the contract and views.</span></span>  
  
-   <span data-ttu-id="524fc-109">创建外接程序端适配器。</span><span class="sxs-lookup"><span data-stu-id="524fc-109">Creating the add-in-side adapter.</span></span>  
  
-   <span data-ttu-id="524fc-110">创建主机端适配器。</span><span class="sxs-lookup"><span data-stu-id="524fc-110">Creating the host-side adapter.</span></span>  
  
-   <span data-ttu-id="524fc-111">创建主机。</span><span class="sxs-lookup"><span data-stu-id="524fc-111">Creating the host.</span></span>  
  
-   <span data-ttu-id="524fc-112">创建外接程序。</span><span class="sxs-lookup"><span data-stu-id="524fc-112">Creating the add-in.</span></span>  
  
-   <span data-ttu-id="524fc-113">部署管道。</span><span class="sxs-lookup"><span data-stu-id="524fc-113">Deploying the pipeline.</span></span>  
  
-   <span data-ttu-id="524fc-114">运行主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="524fc-114">Running the host application.</span></span>  
  
 <span data-ttu-id="524fc-115">此管道传递仅可序列化类型 (<xref:System.Double>和<xref:System.String>)、 主机和外接程序之间。</span><span class="sxs-lookup"><span data-stu-id="524fc-115">This pipeline passes only serializable types (<xref:System.Double> and <xref:System.String>), between the host and the add-in.</span></span> <span data-ttu-id="524fc-116">有关演示如何将传递复杂数据类型的集合的示例，请参阅[演练： 将集合传递之间主机和外接程序](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)。</span><span class="sxs-lookup"><span data-stu-id="524fc-116">For an example that shows how to pass collections of complex data types, see [Walkthrough: Passing Collections Between Hosts and Add-Ins](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5).</span></span>  
  
 <span data-ttu-id="524fc-117">此管道的协定定义四个算术操作的对象模型： 添加、 减、 乘和除。</span><span class="sxs-lookup"><span data-stu-id="524fc-117">The contract for this pipeline defines an object model of four arithmetic operations: add, subtract, multiply, and divide.</span></span> <span data-ttu-id="524fc-118">主机外接程序提供的公式来计算 2 + 2，如和外接程序将结果返回到主机。</span><span class="sxs-lookup"><span data-stu-id="524fc-118">The host provides the add-in with an equation to calculate, such as 2 + 2, and the add-in returns the result to the host.</span></span>  
  
 <span data-ttu-id="524fc-119">第 2 版的计算器外接程序提供更多的计算的可能性，并演示了版本控制。</span><span class="sxs-lookup"><span data-stu-id="524fc-119">Version 2 of the calculator add-in provides more calculating possibilities and demonstrates versioning.</span></span> <span data-ttu-id="524fc-120">中所述[演练： 为主机所做的更改启用向后兼容性](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)。</span><span class="sxs-lookup"><span data-stu-id="524fc-120">It is described in [Walkthrough: Enabling Backward Compatibility as Your Host Changes](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="524fc-121">系统必备</span><span class="sxs-lookup"><span data-stu-id="524fc-121">Prerequisites</span></span>  
 <span data-ttu-id="524fc-122">若要完成本演练，你需要具备以下条件：</span><span class="sxs-lookup"><span data-stu-id="524fc-122">You need the following to complete this walkthrough:</span></span>  
  
-   <span data-ttu-id="524fc-123">Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="524fc-123">Visual Studio.</span></span>  
  
## <a name="creating-a-visual-studio-solution"></a><span data-ttu-id="524fc-124">创建一个 Visual Studio 解决方案</span><span class="sxs-lookup"><span data-stu-id="524fc-124">Creating a Visual Studio Solution</span></span>  
 <span data-ttu-id="524fc-125">使用 Visual Studio 中一种解决方案来包含管线段的项目。</span><span class="sxs-lookup"><span data-stu-id="524fc-125">Use a solution in Visual Studio to contain the projects of your pipeline segments.</span></span>  
  
#### <a name="to-create-the-pipeline-solution"></a><span data-ttu-id="524fc-126">若要创建管道解决方案</span><span class="sxs-lookup"><span data-stu-id="524fc-126">To create the pipeline solution</span></span>  
  
1.  <span data-ttu-id="524fc-127">在 Visual Studio 中，创建一个名为的新项目`Calc1Contract`。</span><span class="sxs-lookup"><span data-stu-id="524fc-127">In Visual Studio, create a new project named `Calc1Contract`.</span></span> <span data-ttu-id="524fc-128">使该项目基于**类库**模板。</span><span class="sxs-lookup"><span data-stu-id="524fc-128">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="524fc-129">将解决方案命名`CalculatorV1`。</span><span class="sxs-lookup"><span data-stu-id="524fc-129">Name the solution `CalculatorV1`.</span></span>  
  
## <a name="creating-the-pipeline-directory-structure"></a><span data-ttu-id="524fc-130">创建管线目录结构</span><span class="sxs-lookup"><span data-stu-id="524fc-130">Creating the Pipeline Directory Structure</span></span>  
 <span data-ttu-id="524fc-131">外接程序模型要求要置于指定的目录结构中的管道段程序集。</span><span class="sxs-lookup"><span data-stu-id="524fc-131">The add-in model requires the pipeline segment assemblies to be placed in a specified directory structure.</span></span> <span data-ttu-id="524fc-132">管道结构的详细信息，请参阅[管线开发要求](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)。</span><span class="sxs-lookup"><span data-stu-id="524fc-132">For more information about the pipeline structure, see [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
#### <a name="to-create-the-pipeline-directory-structure"></a><span data-ttu-id="524fc-133">若要创建管线目录结构</span><span class="sxs-lookup"><span data-stu-id="524fc-133">To create the pipeline directory structure</span></span>  
  
1.  <span data-ttu-id="524fc-134">在您的计算机上的任意位置创建一个应用程序文件夹。</span><span class="sxs-lookup"><span data-stu-id="524fc-134">Create an application folder anywhere on your computer.</span></span>  
  
2.  <span data-ttu-id="524fc-135">在该文件夹中，创建以下结构：</span><span class="sxs-lookup"><span data-stu-id="524fc-135">In that folder, create the following structure:</span></span>  
  
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
  
     <span data-ttu-id="524fc-136">不需要将管道文件夹结构放在你的应用程序文件夹;此处这样做是仅为方便起见。</span><span class="sxs-lookup"><span data-stu-id="524fc-136">It is not necessary to put the pipeline folder structure in your application folder; it is done here only for convenience.</span></span> <span data-ttu-id="524fc-137">在相应的步骤，本演练介绍如何更改代码，如果管道文件夹结构是在不同的位置。</span><span class="sxs-lookup"><span data-stu-id="524fc-137">At the appropriate step, the walkthrough explains how to change the code if the pipeline folder structure is in a different location.</span></span> <span data-ttu-id="524fc-138">请参阅中的管道目录要求的讨论[管线开发要求](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)。</span><span class="sxs-lookup"><span data-stu-id="524fc-138">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="524fc-139">`CalcV2`不在本演练中使用文件夹; 它是占位符[演练： 为主机所做的更改启用向后兼容性](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)。</span><span class="sxs-lookup"><span data-stu-id="524fc-139">The `CalcV2` folder is not used in this walkthrough; it is a placeholder for [Walkthrough: Enabling Backward Compatibility as Your Host Changes](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848).</span></span>  
  
## <a name="creating-the-contract-and-views"></a><span data-ttu-id="524fc-140">创建的协定和视图</span><span class="sxs-lookup"><span data-stu-id="524fc-140">Creating the Contract and Views</span></span>  
 <span data-ttu-id="524fc-141">此管道的协定段定义`ICalc1Contract`接口，它定义了四个方法： `add`， `subtract`， `multiply`，和`divide`。</span><span class="sxs-lookup"><span data-stu-id="524fc-141">The contract segment for this pipeline defines the `ICalc1Contract` interface, which defines four methods: `add`, `subtract`, `multiply`, and `divide`.</span></span>  
  
#### <a name="to-create-the-contract"></a><span data-ttu-id="524fc-142">若要创建协定</span><span class="sxs-lookup"><span data-stu-id="524fc-142">To create the contract</span></span>  
  
1.  <span data-ttu-id="524fc-143">在 Visual Studio 解决方案中名为`CalculatorV1`，打开`Calc1Contract`项目。</span><span class="sxs-lookup"><span data-stu-id="524fc-143">In the Visual Studio solution named `CalculatorV1`, open the `Calc1Contract` project.</span></span>  
  
2.  <span data-ttu-id="524fc-144">在中**解决方案资源管理器**，将引用添加到以下程序集到`Calc1Contract`项目：</span><span class="sxs-lookup"><span data-stu-id="524fc-144">In **Solution Explorer**, add references to the following assemblies to the `Calc1Contract` project:</span></span>  
  
     <span data-ttu-id="524fc-145">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="524fc-145">System.AddIn.Contract.dll</span></span>  
  
     <span data-ttu-id="524fc-146">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="524fc-146">System.AddIn.dll</span></span>  
  
3.  <span data-ttu-id="524fc-147">在中**解决方案资源管理器**，排除添加到新的默认类**类库**项目。</span><span class="sxs-lookup"><span data-stu-id="524fc-147">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects.</span></span>  
  
4.  <span data-ttu-id="524fc-148">在中**解决方案资源管理器**，将新项添加到项目中，使用**接口**模板。</span><span class="sxs-lookup"><span data-stu-id="524fc-148">In **Solution Explorer**, add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="524fc-149">在中**添加新项**对话框中，名称接口`ICalc1Contract`。</span><span class="sxs-lookup"><span data-stu-id="524fc-149">In the **Add New Item** dialog box, name the interface `ICalc1Contract`.</span></span>  
  
5.  <span data-ttu-id="524fc-150">在接口文件中，添加对命名空间引用<xref:System.AddIn.Contract>和<xref:System.AddIn.Pipeline>。</span><span class="sxs-lookup"><span data-stu-id="524fc-150">In the interface file, add namespace references to <xref:System.AddIn.Contract> and <xref:System.AddIn.Pipeline>.</span></span>  
  
6.  <span data-ttu-id="524fc-151">使用以下代码来完成此协定段。</span><span class="sxs-lookup"><span data-stu-id="524fc-151">Use the following code to complete this contract segment.</span></span> <span data-ttu-id="524fc-152">请注意，此接口必须具有<xref:System.AddIn.Pipeline.AddInContractAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="524fc-152">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInContractAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1Contract#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Contract/cs/ICalc1Contract.cs#1)]
     [!code-vb[AddInP1Contract#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Contract/vb/ICalc1Contract.vb#1)]  
  
7.  <span data-ttu-id="524fc-153">（可选） 构建的 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="524fc-153">Optionally, build the Visual Studio solution.</span></span> <span data-ttu-id="524fc-154">无法运行该解决方案，直到最后的过程，但之后的每个过程可确保每个项目都进行生成更正。</span><span class="sxs-lookup"><span data-stu-id="524fc-154">The solution cannot be run until the final procedure, but building it after each procedure ensures that each project is correct.</span></span>  
  
 <span data-ttu-id="524fc-155">由于外接程序视图和主机视图的外接程序通常具有相同的代码，尤其是在外接程序的第一个版本，可以轻松地在同一时间创建视图。</span><span class="sxs-lookup"><span data-stu-id="524fc-155">Because the add-in view and the host view of the add-in usually have the same code, especially in the first version of an add-in, you can easily create the views at the same time.</span></span> <span data-ttu-id="524fc-156">它们只有一个方面不同： 外接程序视图需要<xref:System.AddIn.Pipeline.AddInBaseAttribute>属性，而宿主视图的外接程序不需要任何属性。</span><span class="sxs-lookup"><span data-stu-id="524fc-156">They differ by only one factor: the add-in view requires the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute, while the host view of the add-in does not require any attributes.</span></span>  
  
#### <a name="to-create-the-add-in-view"></a><span data-ttu-id="524fc-157">若要创建外接程序视图</span><span class="sxs-lookup"><span data-stu-id="524fc-157">To create the add-in view</span></span>  
  
1.  <span data-ttu-id="524fc-158">添加一个名为的新项目`Calc1AddInView`到`CalculatorV1`解决方案。</span><span class="sxs-lookup"><span data-stu-id="524fc-158">Add a new project named `Calc1AddInView` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="524fc-159">使该项目基于**类库**模板。</span><span class="sxs-lookup"><span data-stu-id="524fc-159">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="524fc-160">在中**解决方案资源管理器**，添加对到 System.AddIn.dll`Calc1AddInView`项目。</span><span class="sxs-lookup"><span data-stu-id="524fc-160">In **Solution Explorer**, add a reference to System.AddIn.dll to the `Calc1AddInView` project.</span></span>  
  
3.  <span data-ttu-id="524fc-161">在中**解决方案资源管理器**，排除添加到新的默认类**类库**项目，并将新项添加到项目中，使用**接口**模板。</span><span class="sxs-lookup"><span data-stu-id="524fc-161">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="524fc-162">在中**添加新项**对话框中，名称接口`ICalculator`。</span><span class="sxs-lookup"><span data-stu-id="524fc-162">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
4.  <span data-ttu-id="524fc-163">在接口文件中，添加对的命名空间引用<xref:System.AddIn.Pipeline>。</span><span class="sxs-lookup"><span data-stu-id="524fc-163">In the interface file, add a namespace reference to <xref:System.AddIn.Pipeline>.</span></span>  
  
5.  <span data-ttu-id="524fc-164">使用以下代码来完成该外接程序视图。</span><span class="sxs-lookup"><span data-stu-id="524fc-164">Use the following code to complete this add-in view.</span></span> <span data-ttu-id="524fc-165">请注意，此接口必须具有<xref:System.AddIn.Pipeline.AddInBaseAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="524fc-165">Note that this interface must have the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute.</span></span>  
  
     [!code-csharp[AddInP1AddInViews#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInViews/cs/Calc1AddInView.cs#1)]
     [!code-vb[AddInP1AddInViews#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInViews/vb/Calc1AddInView.vb#1)]  
  
6.  <span data-ttu-id="524fc-166">（可选） 构建的 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="524fc-166">Optionally, build the Visual Studio solution.</span></span>  
  
#### <a name="to-create-the-host-view-of-the-add-in"></a><span data-ttu-id="524fc-167">若要创建的外接程序的宿主视图</span><span class="sxs-lookup"><span data-stu-id="524fc-167">To create the host view of the add-in</span></span>  
  
1.  <span data-ttu-id="524fc-168">添加一个名为的新项目`Calc1HVA`到`CalculatorV1`解决方案。</span><span class="sxs-lookup"><span data-stu-id="524fc-168">Add a new project named `Calc1HVA` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="524fc-169">使该项目基于**类库**模板。</span><span class="sxs-lookup"><span data-stu-id="524fc-169">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="524fc-170">在中**解决方案资源管理器**，排除添加到新的默认类**类库**项目，并将新项添加到项目中，使用**接口**模板。</span><span class="sxs-lookup"><span data-stu-id="524fc-170">In **Solution Explorer**, exclude the default class that is added to new **Class Library** projects, and add a new item to the project, using the **Interface** template.</span></span> <span data-ttu-id="524fc-171">在中**添加新项**对话框中，名称接口`ICalculator`。</span><span class="sxs-lookup"><span data-stu-id="524fc-171">In the **Add New Item** dialog box, name the interface `ICalculator`.</span></span>  
  
3.  <span data-ttu-id="524fc-172">在接口文件中，使用以下代码以完成外接程序的宿主视图。</span><span class="sxs-lookup"><span data-stu-id="524fc-172">In the interface file, use the following code to complete the host view of the add-in.</span></span>  
  
     [!code-csharp[AddInP1HVA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HVA/cs/calc1hva.cs#1)]
     [!code-vb[AddInP1HVA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HVA/vb/Calc1HVA.vb#1)]  
  
4.  <span data-ttu-id="524fc-173">（可选） 构建的 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="524fc-173">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in-side-adapter"></a><span data-ttu-id="524fc-174">创建接程序端适配器</span><span class="sxs-lookup"><span data-stu-id="524fc-174">Creating the Add-in-side Adapter</span></span>  
 <span data-ttu-id="524fc-175">此接程序端适配器由一个视图到约定适配器组成。</span><span class="sxs-lookup"><span data-stu-id="524fc-175">This add-in-side adapter consists of one view-to-contract adapter.</span></span> <span data-ttu-id="524fc-176">此管道段将类型从外接程序视图转换为约定。</span><span class="sxs-lookup"><span data-stu-id="524fc-176">This pipeline segment converts the types from the add-in view to the contract.</span></span>  
  
 <span data-ttu-id="524fc-177">在此管道中外, 接程序提供一个服务到主机，和类型从外接程序流到主机。</span><span class="sxs-lookup"><span data-stu-id="524fc-177">In this pipeline, the add-in provides a service to the host, and the types flow from the add-in to the host.</span></span> <span data-ttu-id="524fc-178">由于没有类型流向从宿主向外接程序，您无需包括此管道的外接程序端上的约定到视图适配器。</span><span class="sxs-lookup"><span data-stu-id="524fc-178">Because no types flow from the host to the add-in, you do not have to include a contract-to-view adapter on the add-in side of this pipeline.</span></span>  
  
#### <a name="to-create-the-add-in-side-adapter"></a><span data-ttu-id="524fc-179">若要创建外接程序端适配器</span><span class="sxs-lookup"><span data-stu-id="524fc-179">To create the add-in-side adapter</span></span>  
  
1.  <span data-ttu-id="524fc-180">添加一个名为的新项目`Calc1AddInSideAdapter`到`CalculatorV1`解决方案。</span><span class="sxs-lookup"><span data-stu-id="524fc-180">Add a new project named `Calc1AddInSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="524fc-181">使该项目基于**类库**模板。</span><span class="sxs-lookup"><span data-stu-id="524fc-181">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="524fc-182">在中**解决方案资源管理器**，将引用添加到以下程序集到`Calc1AddInSideAdapter`项目：</span><span class="sxs-lookup"><span data-stu-id="524fc-182">In **Solution Explorer**, add references to the following assemblies to the `Calc1AddInSideAdapter` project:</span></span>  
  
     <span data-ttu-id="524fc-183">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="524fc-183">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="524fc-184">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="524fc-184">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="524fc-185">添加相邻的管线段的项目到项目引用：</span><span class="sxs-lookup"><span data-stu-id="524fc-185">Add project references to the projects for the adjacent pipeline segments:</span></span>  
  
     `Calc1AddInView`  
  
     `Calc1Contract`  
  
4.  <span data-ttu-id="524fc-186">选择每个项目引用，然后在**属性**设置**Copy Local**到**False**。</span><span class="sxs-lookup"><span data-stu-id="524fc-186">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="524fc-187">在 Visual Basic 中，使用**引用**选项卡**项目属性**若要设置**复制本地**到**False**为两个项目的引用。</span><span class="sxs-lookup"><span data-stu-id="524fc-187">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="524fc-188">重命名项目的默认类`CalculatorViewToContractAddInSideAdapter`。</span><span class="sxs-lookup"><span data-stu-id="524fc-188">Rename the project's default class `CalculatorViewToContractAddInSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="524fc-189">在类文件中，添加对命名空间引用<xref:System.AddIn.Pipeline>。</span><span class="sxs-lookup"><span data-stu-id="524fc-189">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="524fc-190">在类文件中，添加相邻的段的命名空间引用：`CalcAddInViews`和`CalculatorContracts`。</span><span class="sxs-lookup"><span data-stu-id="524fc-190">In the class file, add namespace references for the adjacent segments: `CalcAddInViews` and `CalculatorContracts`.</span></span> <span data-ttu-id="524fc-191">(在 Visual Basic 中的这些命名空间引用`Calc1AddInView.CalcAddInViews`和`Calc1Contract.CalculatorContracts`，除非是关闭 Visual Basic 项目中的默认命名空间。)</span><span class="sxs-lookup"><span data-stu-id="524fc-191">(In Visual Basic, these namespace references are `Calc1AddInView.CalcAddInViews` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="524fc-192">将应用<xref:System.AddIn.Pipeline.AddInAdapterAttribute>属性为`CalculatorViewToContractAddInSideAdapter`类，它标识为外接程序端适配器。</span><span class="sxs-lookup"><span data-stu-id="524fc-192">Apply the <xref:System.AddIn.Pipeline.AddInAdapterAttribute> attribute to the `CalculatorViewToContractAddInSideAdapter` class, to identify it as the add-in-side adapter.</span></span>  
  
9. <span data-ttu-id="524fc-193">请`CalculatorViewToContractAddInSideAdapter`类继承<xref:System.AddIn.Pipeline.ContractBase>，它提供的默认实现<xref:System.AddIn.Contract.IContract>接口，并实现协定接口，将管道`ICalc1Contract`。</span><span class="sxs-lookup"><span data-stu-id="524fc-193">Make the `CalculatorViewToContractAddInSideAdapter` class inherit <xref:System.AddIn.Pipeline.ContractBase>, which provides a default implementation of the <xref:System.AddIn.Contract.IContract> interface, and implement the contract interface for the pipeline, `ICalc1Contract`.</span></span>  
  
10. <span data-ttu-id="524fc-194">添加公共构造函数接受`ICalculator`，将其缓存在私有字段中，并调用基类构造函数。</span><span class="sxs-lookup"><span data-stu-id="524fc-194">Add a public constructor that accepts an `ICalculator`, caches it in a private field, and calls the base class constructor.</span></span>  
  
11. <span data-ttu-id="524fc-195">若要实现的成员`ICalc1Contract`，只需调用的对应成员`ICalculator`实例传递给构造函数中，并返回结果。</span><span class="sxs-lookup"><span data-stu-id="524fc-195">To implement the members of `ICalc1Contract`, simply call the corresponding members of the `ICalculator` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="524fc-196">这可适应视图 (`ICalculator`) 到协定 (`ICalc1Contract`)。</span><span class="sxs-lookup"><span data-stu-id="524fc-196">This adapts the view (`ICalculator`) to the contract (`ICalc1Contract`).</span></span>  
  
     <span data-ttu-id="524fc-197">下面的代码显示了已完成-的外接程序端适配器。</span><span class="sxs-lookup"><span data-stu-id="524fc-197">The following code shows the completed add-in-side adapter.</span></span>  
  
     [!code-csharp[AddInP1AddInSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInSideAdapters/cs/Calc1ViewToContractAddInSideAdapter.cs#1)]
     [!code-vb[AddInP1AddInSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInSideAdapters/vb/Calc1ViewToContractAddInSideAdapter.vb#1)]  
  
12. <span data-ttu-id="524fc-198">（可选） 构建的 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="524fc-198">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host-side-adapter"></a><span data-ttu-id="524fc-199">创建主机端适配器</span><span class="sxs-lookup"><span data-stu-id="524fc-199">Creating the Host-side Adapter</span></span>  
 <span data-ttu-id="524fc-200">此宿主端适配器由一个约定到视图适配器组成。</span><span class="sxs-lookup"><span data-stu-id="524fc-200">This host-side adapter consists of one contract-to-view adapter.</span></span> <span data-ttu-id="524fc-201">此段调整到外接程序的宿主视图的约定。</span><span class="sxs-lookup"><span data-stu-id="524fc-201">This segment adapts the contract to the host view of the add-in.</span></span>  
  
 <span data-ttu-id="524fc-202">在此管道中外, 接程序提供了一项服务对主机和类型流从外接程序向主机。</span><span class="sxs-lookup"><span data-stu-id="524fc-202">In this pipeline, the add-in provides a service to the host and the types flow from the add-in to the host.</span></span> <span data-ttu-id="524fc-203">由于没有类型流向从宿主向外接程序，您无需包括视图到约定适配器。</span><span class="sxs-lookup"><span data-stu-id="524fc-203">Because no types flow from the host to the add-in, you do not have to include a view-to-contract adapter.</span></span>  
  
 <span data-ttu-id="524fc-204">若要实现生存期管理，请使用<xref:System.AddIn.Pipeline.ContractHandle>要附加到该协定的生存期标记对象。</span><span class="sxs-lookup"><span data-stu-id="524fc-204">To implement lifetime management, use a <xref:System.AddIn.Pipeline.ContractHandle> object to attach a lifetime token to the contract.</span></span> <span data-ttu-id="524fc-205">为了使生命期管理工作，必须保留对此句柄的引用。</span><span class="sxs-lookup"><span data-stu-id="524fc-205">You must keep a reference to this handle in order for lifetime management to work.</span></span> <span data-ttu-id="524fc-206">应用令牌后，无需任何其他编程需要，因为它们不再使用，并使它们可用于垃圾回收时外, 接程序系统可以释放的对象。</span><span class="sxs-lookup"><span data-stu-id="524fc-206">After the token is applied, no additional programming is required because the add-in system can dispose of objects when they are no longer being used and make them available for garbage collection.</span></span> <span data-ttu-id="524fc-207">有关详细信息，请参阅[生存期管理](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5)。</span><span class="sxs-lookup"><span data-stu-id="524fc-207">For more information, see [Lifetime Management](https://msdn.microsoft.com/library/57a9c87e-394c-4fef-89f2-aa4223a2aeb5).</span></span>  
  
#### <a name="to-create-the-host-side-adapter"></a><span data-ttu-id="524fc-208">若要创建的主机端适配器</span><span class="sxs-lookup"><span data-stu-id="524fc-208">To create the host-side adapter</span></span>  
  
1.  <span data-ttu-id="524fc-209">添加一个名为的新项目`Calc1HostSideAdapter`到`CalculatorV1`解决方案。</span><span class="sxs-lookup"><span data-stu-id="524fc-209">Add a new project named `Calc1HostSideAdapter` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="524fc-210">使该项目基于**类库**模板。</span><span class="sxs-lookup"><span data-stu-id="524fc-210">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="524fc-211">在中**解决方案资源管理器**，将引用添加到以下程序集到`Calc1HostSideAdapter`项目：</span><span class="sxs-lookup"><span data-stu-id="524fc-211">In **Solution Explorer**, add references to the following assemblies to the `Calc1HostSideAdapter` project:</span></span>  
  
     <span data-ttu-id="524fc-212">System.AddIn.dll</span><span class="sxs-lookup"><span data-stu-id="524fc-212">System.AddIn.dll</span></span>  
  
     <span data-ttu-id="524fc-213">System.AddIn.Contract.dll</span><span class="sxs-lookup"><span data-stu-id="524fc-213">System.AddIn.Contract.dll</span></span>  
  
3.  <span data-ttu-id="524fc-214">添加相邻的段的项目到项目引用：</span><span class="sxs-lookup"><span data-stu-id="524fc-214">Add project references to the projects for the adjacent segments:</span></span>  
  
     `Calc1Contract`  
  
     `Calc1HVA`  
  
4.  <span data-ttu-id="524fc-215">选择每个项目引用，然后在**属性**设置**Copy Local**到**False**。</span><span class="sxs-lookup"><span data-stu-id="524fc-215">Select each project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="524fc-216">在 Visual Basic 中，使用**引用**选项卡**项目属性**若要设置**复制本地**到**False**为两个项目的引用。</span><span class="sxs-lookup"><span data-stu-id="524fc-216">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the two project references.</span></span>  
  
5.  <span data-ttu-id="524fc-217">重命名项目的默认类`CalculatorContractToViewHostSideAdapter`。</span><span class="sxs-lookup"><span data-stu-id="524fc-217">Rename the project's default class `CalculatorContractToViewHostSideAdapter`.</span></span>  
  
6.  <span data-ttu-id="524fc-218">在类文件中，添加对命名空间引用<xref:System.AddIn.Pipeline>。</span><span class="sxs-lookup"><span data-stu-id="524fc-218">In the class file, add namespace references to <xref:System.AddIn.Pipeline>.</span></span>  
  
7.  <span data-ttu-id="524fc-219">在类文件中，添加相邻的段的命名空间引用：`CalcHVAs`和`CalculatorContracts`。</span><span class="sxs-lookup"><span data-stu-id="524fc-219">In the class file, add namespace references for the adjacent segments: `CalcHVAs` and `CalculatorContracts`.</span></span> <span data-ttu-id="524fc-220">(在 Visual Basic 中的这些命名空间引用`Calc1HVA.CalcHVAs`和`Calc1Contract.CalculatorContracts`，除非是关闭 Visual Basic 项目中的默认命名空间。)</span><span class="sxs-lookup"><span data-stu-id="524fc-220">(In Visual Basic, these namespace references are `Calc1HVA.CalcHVAs` and `Calc1Contract.CalculatorContracts`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="524fc-221">将应用<xref:System.AddIn.Pipeline.HostAdapterAttribute>属性为`CalculatorContractToViewHostSideAdapter`类，以将标识为主机端适配器段。</span><span class="sxs-lookup"><span data-stu-id="524fc-221">Apply the <xref:System.AddIn.Pipeline.HostAdapterAttribute> attribute to the `CalculatorContractToViewHostSideAdapter` class, to identify it as the host-side adapter segment.</span></span>  
  
9. <span data-ttu-id="524fc-222">请`CalculatorContractToViewHostSideAdapter`类实现表示外接程序的宿主视图的接口： `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator`在 Visual Basic 中)。</span><span class="sxs-lookup"><span data-stu-id="524fc-222">Make the `CalculatorContractToViewHostSideAdapter` class implement the interface that represents the host view of the add-in: `Calc1HVAs.ICalculator` (`Calc1HVA.CalcHVAs.ICalculator` in Visual Basic).</span></span>  
  
10. <span data-ttu-id="524fc-223">添加公共构造函数接受管道协定类型， `ICalc1Contract`。</span><span class="sxs-lookup"><span data-stu-id="524fc-223">Add a public constructor that accepts the pipeline contract type, `ICalc1Contract`.</span></span> <span data-ttu-id="524fc-224">构造函数必须缓存对该协定的引用。</span><span class="sxs-lookup"><span data-stu-id="524fc-224">The constructor must cache the reference to the contract.</span></span> <span data-ttu-id="524fc-225">它还必须创建并缓存新<xref:System.AddIn.Pipeline.ContractHandle>对于协定，若要管理的外接程序的生存期。</span><span class="sxs-lookup"><span data-stu-id="524fc-225">It must also create and cache a new <xref:System.AddIn.Pipeline.ContractHandle> for the contract, to manage the lifetime of the add-in.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="524fc-226"><xref:System.AddIn.Pipeline.ContractHandle>生命期管理至关重要。</span><span class="sxs-lookup"><span data-stu-id="524fc-226">The <xref:System.AddIn.Pipeline.ContractHandle> is critical to lifetime management.</span></span> <span data-ttu-id="524fc-227">如果您不能保持对引用<xref:System.AddIn.Pipeline.ContractHandle>对象，垃圾回收将回收，且当您的程序不需要管道将关闭。</span><span class="sxs-lookup"><span data-stu-id="524fc-227">If you fail to keep a reference to the <xref:System.AddIn.Pipeline.ContractHandle> object, garbage collection will reclaim it, and the pipeline will shut down when your program does not expect it.</span></span> <span data-ttu-id="524fc-228">这可能会导致难以进行诊断，如错误<xref:System.AppDomainUnloadedException>。</span><span class="sxs-lookup"><span data-stu-id="524fc-228">This can lead to errors that are difficult to diagnose, such as <xref:System.AppDomainUnloadedException>.</span></span> <span data-ttu-id="524fc-229">关闭是管道的生活中，一个正常阶段，因此没有生存期管理代码来检测这种情况是管道的错误的方法。</span><span class="sxs-lookup"><span data-stu-id="524fc-229">Shutdown is a normal stage in the life of a pipeline, so there is no way for the lifetime management code to detect that this condition is an error.</span></span>  
  
11. <span data-ttu-id="524fc-230">若要实现的成员`ICalculator`，只需调用的对应成员`ICalc1Contract`实例传递给构造函数中，并返回结果。</span><span class="sxs-lookup"><span data-stu-id="524fc-230">To implement the members of `ICalculator`, simply call the corresponding members of the `ICalc1Contract` instance that is passed to the constructor, and return the results.</span></span> <span data-ttu-id="524fc-231">这可适应协定 (`ICalc1Contract`) 到视图 (`ICalculator`)。</span><span class="sxs-lookup"><span data-stu-id="524fc-231">This adapts the contract (`ICalc1Contract`) to the view (`ICalculator`).</span></span>  
  
     <span data-ttu-id="524fc-232">下面的代码显示了已完成的宿主端适配器。</span><span class="sxs-lookup"><span data-stu-id="524fc-232">The following code shows the completed host-side adapter.</span></span>  
  
     [!code-csharp[AddInP1HostSideAdapters#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1HostSideAdapters/cs/Calc1ContractToViewHostSideAdapter.cs#1)]
     [!code-vb[AddInP1HostSideAdapters#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1HostSideAdapters/vb/Calc1ContractToViewHostSideAdapter.vb#1)]  
  
12. <span data-ttu-id="524fc-233">（可选） 构建的 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="524fc-233">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-host"></a><span data-ttu-id="524fc-234">创建主机</span><span class="sxs-lookup"><span data-stu-id="524fc-234">Creating the Host</span></span>  
 <span data-ttu-id="524fc-235">主机应用程序与外接程序通过外接程序的宿主视图进行交互。</span><span class="sxs-lookup"><span data-stu-id="524fc-235">A host application interacts with the add-in through the host view of the add-in.</span></span> <span data-ttu-id="524fc-236">它使用外接程序发现和激活方法提供<xref:System.AddIn.Hosting.AddInStore>和<xref:System.AddIn.Hosting.AddInToken>类来执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="524fc-236">It uses add-in discovery and activation methods provided by the <xref:System.AddIn.Hosting.AddInStore> and <xref:System.AddIn.Hosting.AddInToken> classes to do the following:</span></span>  
  
-   <span data-ttu-id="524fc-237">更新管道和外接程序信息的缓存。</span><span class="sxs-lookup"><span data-stu-id="524fc-237">Update the cache of pipeline and add-in information.</span></span>  
  
-   <span data-ttu-id="524fc-238">查找宿主视图类型的加载项`ICalculator`，指定的管道根目录下。</span><span class="sxs-lookup"><span data-stu-id="524fc-238">Find add-ins of the host view type, `ICalculator`, under the specified pipeline root directory.</span></span>  
  
-   <span data-ttu-id="524fc-239">提示用户指定的外接程序才能使用。</span><span class="sxs-lookup"><span data-stu-id="524fc-239">Prompt the user to specify which add-in to use.</span></span>  
  
-   <span data-ttu-id="524fc-240">激活的所选外接程序中具有指定的安全信任级别的新应用程序域。</span><span class="sxs-lookup"><span data-stu-id="524fc-240">Activate the selected add-in in a new application domain with a specified security trust level.</span></span>  
  
-   <span data-ttu-id="524fc-241">运行自定义`RunCalculator`方法，其调用指定的外接程序的宿主视图的外接程序的方法。</span><span class="sxs-lookup"><span data-stu-id="524fc-241">Run the custom `RunCalculator` method, which calls the add-in's methods as specified by the host view of the add-in.</span></span>  
  
#### <a name="to-create-the-host"></a><span data-ttu-id="524fc-242">若要创建的主机</span><span class="sxs-lookup"><span data-stu-id="524fc-242">To create the host</span></span>  
  
1.  <span data-ttu-id="524fc-243">添加一个名为的新项目`Calc1Host`到`CalculatorV1`解决方案。</span><span class="sxs-lookup"><span data-stu-id="524fc-243">Add a new project named `Calc1Host` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="524fc-244">使该项目基于**控制台应用程序**模板。</span><span class="sxs-lookup"><span data-stu-id="524fc-244">Base it on the **Console Application** template.</span></span>  
  
2.  <span data-ttu-id="524fc-245">在中**解决方案资源管理器**，添加到 System.AddIn.dll 程序集的引用`Calc1Host`项目。</span><span class="sxs-lookup"><span data-stu-id="524fc-245">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the `Calc1Host` project.</span></span>  
  
3.  <span data-ttu-id="524fc-246">添加到项目引用`Calc1HVA`项目。</span><span class="sxs-lookup"><span data-stu-id="524fc-246">Add a project reference to the `Calc1HVA` project.</span></span> <span data-ttu-id="524fc-247">选择该项目引用，然后在**属性**设置**Copy Local**到**False**。</span><span class="sxs-lookup"><span data-stu-id="524fc-247">Select the project reference, and in **Properties** set **Copy Local** to **False**.</span></span> <span data-ttu-id="524fc-248">在 Visual Basic 中，使用**引用**选项卡**项目属性**若要设置**复制本地**到**False**。</span><span class="sxs-lookup"><span data-stu-id="524fc-248">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False**.</span></span>  
  
4.  <span data-ttu-id="524fc-249">重命名类文件 （在 Visual Basic 中的模块） `MathHost1`。</span><span class="sxs-lookup"><span data-stu-id="524fc-249">Rename the class file (module in Visual Basic) `MathHost1`.</span></span>  
  
5.  <span data-ttu-id="524fc-250">在 Visual Basic 中，使用**应用程序**选项卡**项目属性**对话框来设置**启动对象**到**Sub Main**。</span><span class="sxs-lookup"><span data-stu-id="524fc-250">In Visual Basic, use the **Application** tab of the **Project Properties** dialog box to set **Startup object** to **Sub Main**.</span></span>  
  
6.  <span data-ttu-id="524fc-251">在类或模块文件中，添加对的命名空间引用<xref:System.AddIn.Hosting>。</span><span class="sxs-lookup"><span data-stu-id="524fc-251">In the class or module file, add a namespace reference to <xref:System.AddIn.Hosting>.</span></span>  
  
7.  <span data-ttu-id="524fc-252">在类或模块文件中，添加外接程序的宿主视图的命名空间引用： `CalcHVAs`。</span><span class="sxs-lookup"><span data-stu-id="524fc-252">In the class or module file, add a namespace reference for the host view of the add-in: `CalcHVAs`.</span></span> <span data-ttu-id="524fc-253">(在 Visual Basic 中为此命名空间引用`Calc1HVA.CalcHVAs`，除非是关闭 Visual Basic 项目中的默认命名空间。)</span><span class="sxs-lookup"><span data-stu-id="524fc-253">(In Visual Basic, this namespace reference is `Calc1HVA.CalcHVAs`, unless you have turned off the default namespaces in your Visual Basic projects.)</span></span>  
  
8.  <span data-ttu-id="524fc-254">在中**解决方案资源管理器**，选择的解决方案和从**项目**菜单中，选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="524fc-254">In **Solution Explorer**, select the solution and from the **Project** menu choose **Properties**.</span></span> <span data-ttu-id="524fc-255">在中**解决方案属性页**对话框中，将**单启动项目**为此主机应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="524fc-255">In the **Solution Property Pages** dialog box, set the **Single Startup Project** to be this host application project.</span></span>  
  
9. <span data-ttu-id="524fc-256">在类或模块文件中，使用<xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType>方法来更新缓存。</span><span class="sxs-lookup"><span data-stu-id="524fc-256">In the class or module file, use the <xref:System.AddIn.Hosting.AddInStore.Update%2A?displayProperty=nameWithType> method to update the cache.</span></span> <span data-ttu-id="524fc-257">使用<xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType>方法以获取一系列令牌，并使用<xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType>方法，以激活外接程序。</span><span class="sxs-lookup"><span data-stu-id="524fc-257">Use the <xref:System.AddIn.Hosting.AddInStore.FindAddIn%2A?displayProperty=nameWithType> method to get a collection of tokens, and use the <xref:System.AddIn.Hosting.AddInToken.Activate%2A?displayProperty=nameWithType> method to activate an add-in.</span></span>  
  
     <span data-ttu-id="524fc-258">下面的代码显示了完整的宿主应用程序。</span><span class="sxs-lookup"><span data-stu-id="524fc-258">The following code shows the completed host application.</span></span>  
  
     [!code-csharp[AddInP1Host#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1Host/cs/MathHost1.cs#1)]
     [!code-vb[AddInP1Host#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1Host/vb/MathHost1.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="524fc-259">此代码假定管道文件夹结构位于应用程序文件夹。</span><span class="sxs-lookup"><span data-stu-id="524fc-259">This code assumes that the pipeline folder structure is located in the application folder.</span></span> <span data-ttu-id="524fc-260">如果它位于其他位置，更改的设置的代码行`addInRoot`变量，以使该变量包含管线目录结构的路径。</span><span class="sxs-lookup"><span data-stu-id="524fc-260">If you located it elsewhere, change the line of code that sets the `addInRoot` variable, so that the variable contains the path to your pipeline directory structure.</span></span>  
  
     <span data-ttu-id="524fc-261">该代码使用`ChooseCalculator`方法来列出标记，并提示用户选择外接程序。</span><span class="sxs-lookup"><span data-stu-id="524fc-261">The code uses a `ChooseCalculator` method to list the tokens and to prompt the user to choose an add-in.</span></span> <span data-ttu-id="524fc-262">`RunCalculator`方法提示用户提供简单的数学表达式中，将使用的表达式分析`Parser`类，并显示返回的结果外接程序。</span><span class="sxs-lookup"><span data-stu-id="524fc-262">The `RunCalculator` method prompts the user for simple math expressions, parses the expressions using the `Parser` class, and displays the results returned by the add-in.</span></span>  
  
10. <span data-ttu-id="524fc-263">（可选） 构建的 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="524fc-263">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="creating-the-add-in"></a><span data-ttu-id="524fc-264">创建的外接程序</span><span class="sxs-lookup"><span data-stu-id="524fc-264">Creating the Add-In</span></span>  
 <span data-ttu-id="524fc-265">外接程序实现外接程序视图所指定的方法。</span><span class="sxs-lookup"><span data-stu-id="524fc-265">An add-in implements the methods specified by the add-in view.</span></span> <span data-ttu-id="524fc-266">该外接程序实现`Add`， `Subtract`， `Multiply`，和`Divide`操作并将结果返回到主机。</span><span class="sxs-lookup"><span data-stu-id="524fc-266">This add-in implements the `Add`, `Subtract`, `Multiply`, and `Divide` operations and returns the results to the host.</span></span>  
  
#### <a name="to-create-the-add-in"></a><span data-ttu-id="524fc-267">若要创建外接程序</span><span class="sxs-lookup"><span data-stu-id="524fc-267">To create the add-in</span></span>  
  
1.  <span data-ttu-id="524fc-268">添加一个名为的新项目`AddInCalcV1`到`CalculatorV1`解决方案。</span><span class="sxs-lookup"><span data-stu-id="524fc-268">Add a new project named `AddInCalcV1` to the `CalculatorV1` solution.</span></span> <span data-ttu-id="524fc-269">使该项目基于**类库**模板。</span><span class="sxs-lookup"><span data-stu-id="524fc-269">Base it on the **Class Library** template.</span></span>  
  
2.  <span data-ttu-id="524fc-270">在中**解决方案资源管理器**，向项目添加 System.AddIn.dll 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="524fc-270">In **Solution Explorer**, add a reference to the System.AddIn.dll assembly to the project.</span></span>  
  
3.  <span data-ttu-id="524fc-271">添加到项目引用`Calc1AddInView`项目。</span><span class="sxs-lookup"><span data-stu-id="524fc-271">Add a project reference to the `Calc1AddInView` project.</span></span> <span data-ttu-id="524fc-272">选择该项目引用，然后在**属性**，请设置**Copy Local**到**False**。</span><span class="sxs-lookup"><span data-stu-id="524fc-272">Select the project reference, and in **Properties**, set **Copy Local** to **False**.</span></span> <span data-ttu-id="524fc-273">在 Visual Basic 中，使用**引用**选项卡**项目属性**若要设置**复制本地**到**False**项目引用。</span><span class="sxs-lookup"><span data-stu-id="524fc-273">In Visual Basic, use the **References** tab of **Project Properties** to set **Copy Local** to **False** for the project reference.</span></span>  
  
4.  <span data-ttu-id="524fc-274">将类重命名`AddInCalcV1`。</span><span class="sxs-lookup"><span data-stu-id="524fc-274">Rename the class `AddInCalcV1`.</span></span>  
  
5.  <span data-ttu-id="524fc-275">在类文件添加到的命名空间引用<xref:System.AddIn>和外接程序视图段： `CalcAddInViews` (`Calc1AddInView.CalcAddInViews`在 Visual Basic 中)。</span><span class="sxs-lookup"><span data-stu-id="524fc-275">In the class file, add a namespace reference to <xref:System.AddIn> and the add-in view segment: `CalcAddInViews` (`Calc1AddInView.CalcAddInViews` in Visual Basic).</span></span>  
  
6.  <span data-ttu-id="524fc-276">将应用<xref:System.AddIn.AddInAttribute>属性为`AddInCalcV1`类中，以将类标识为外接程序。</span><span class="sxs-lookup"><span data-stu-id="524fc-276">Apply the <xref:System.AddIn.AddInAttribute> attribute to the `AddInCalcV1` class, to identify the class as an add-in.</span></span>  
  
7.  <span data-ttu-id="524fc-277">请`AddInCalcV1`类实现该接口表示外接程序视图： `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator`在 Visual Basic 中)。</span><span class="sxs-lookup"><span data-stu-id="524fc-277">Make the `AddInCalcV1` class implement the interface that represents the add-in view: `CalcAddInViews.ICalculator` (`Calc1AddInView.CalcAddInViews.ICalculator` in Visual Basic).</span></span>  
  
8.  <span data-ttu-id="524fc-278">实现的成员`ICalculator`通过返回相应的计算结果。</span><span class="sxs-lookup"><span data-stu-id="524fc-278">Implement the members of `ICalculator` by returning the results of the appropriate calculations.</span></span>  
  
     <span data-ttu-id="524fc-279">下面的代码显示了已完成加载项。</span><span class="sxs-lookup"><span data-stu-id="524fc-279">The following code shows the completed add-in.</span></span>  
  
     [!code-csharp[AddInP1AddInCalcV1#1](../../../samples/snippets/csharp/VS_Snippets_CLR/AddInP1AddInCalcV1/cs/AddInCalcV1.cs#1)]
     [!code-vb[AddInP1AddInCalcV1#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/AddInP1AddInCalcV1/vb/AddInCalcV1.vb#1)]  
  
9. <span data-ttu-id="524fc-280">（可选） 构建的 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="524fc-280">Optionally, build the Visual Studio solution.</span></span>  
  
## <a name="deploying-the-pipeline"></a><span data-ttu-id="524fc-281">部署管道</span><span class="sxs-lookup"><span data-stu-id="524fc-281">Deploying the Pipeline</span></span>  
 <span data-ttu-id="524fc-282">现在您就可以构建并部署到所需的管线目录结构的外接程序段。</span><span class="sxs-lookup"><span data-stu-id="524fc-282">You are now ready to build and deploy the add-in segments to the required pipeline directory structure.</span></span>  
  
#### <a name="to-deploy-the-segments-to-the-pipeline"></a><span data-ttu-id="524fc-283">若要将段部署到管道</span><span class="sxs-lookup"><span data-stu-id="524fc-283">To deploy the segments to the pipeline</span></span>  
  
1.  <span data-ttu-id="524fc-284">对于解决方案中每个项目，使用**构建**选项卡**项目属性**(**编译**选项卡，在 Visual Basic 中的) 设置的值**输出路径** (**生成输出路径**在 Visual Basic 中)。</span><span class="sxs-lookup"><span data-stu-id="524fc-284">For each project in the solution, use the **Build** tab of **Project Properties** (the **Compile** tab in Visual Basic) to set the value of the **Output path** (the **Build output path** in Visual Basic).</span></span> <span data-ttu-id="524fc-285">如果名为你的应用程序文件夹`MyApp`，例如，你的项目将生成到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="524fc-285">If you named your application folder `MyApp`, for example, your projects would build into the following folders:</span></span>  
  
    |<span data-ttu-id="524fc-286">项目</span><span class="sxs-lookup"><span data-stu-id="524fc-286">Project</span></span>|<span data-ttu-id="524fc-287">路径</span><span class="sxs-lookup"><span data-stu-id="524fc-287">Path</span></span>|  
    |-------------|----------|  
    |<span data-ttu-id="524fc-288">AddInCalcV1</span><span class="sxs-lookup"><span data-stu-id="524fc-288">AddInCalcV1</span></span>|<span data-ttu-id="524fc-289">MyApp\Pipeline\AddIns\CalcV1</span><span class="sxs-lookup"><span data-stu-id="524fc-289">MyApp\Pipeline\AddIns\CalcV1</span></span>|  
    |<span data-ttu-id="524fc-290">Calc1AddInSideAdapter</span><span class="sxs-lookup"><span data-stu-id="524fc-290">Calc1AddInSideAdapter</span></span>|<span data-ttu-id="524fc-291">MyApp\Pipeline\AddInSideAdapters</span><span class="sxs-lookup"><span data-stu-id="524fc-291">MyApp\Pipeline\AddInSideAdapters</span></span>|  
    |<span data-ttu-id="524fc-292">Calc1AddInView</span><span class="sxs-lookup"><span data-stu-id="524fc-292">Calc1AddInView</span></span>|<span data-ttu-id="524fc-293">MyApp\Pipeline\AddInViews</span><span class="sxs-lookup"><span data-stu-id="524fc-293">MyApp\Pipeline\AddInViews</span></span>|  
    |<span data-ttu-id="524fc-294">Calc1Contract</span><span class="sxs-lookup"><span data-stu-id="524fc-294">Calc1Contract</span></span>|<span data-ttu-id="524fc-295">MyApp\Pipeline\Contracts</span><span class="sxs-lookup"><span data-stu-id="524fc-295">MyApp\Pipeline\Contracts</span></span>|  
    |<span data-ttu-id="524fc-296">Calc1Host</span><span class="sxs-lookup"><span data-stu-id="524fc-296">Calc1Host</span></span>|<span data-ttu-id="524fc-297">MyApp</span><span class="sxs-lookup"><span data-stu-id="524fc-297">MyApp</span></span>|  
    |<span data-ttu-id="524fc-298">Calc1HostSideAdapter</span><span class="sxs-lookup"><span data-stu-id="524fc-298">Calc1HostSideAdapter</span></span>|<span data-ttu-id="524fc-299">MyApp\Pipeline\HostSideAdapters</span><span class="sxs-lookup"><span data-stu-id="524fc-299">MyApp\Pipeline\HostSideAdapters</span></span>|  
    |<span data-ttu-id="524fc-300">Calc1HVA</span><span class="sxs-lookup"><span data-stu-id="524fc-300">Calc1HVA</span></span>|<span data-ttu-id="524fc-301">MyApp</span><span class="sxs-lookup"><span data-stu-id="524fc-301">MyApp</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="524fc-302">如果您决定将您的管道文件夹结构中应用程序文件夹之外的位置，则必须修改相应地在表中所示的路径。</span><span class="sxs-lookup"><span data-stu-id="524fc-302">If you decided to put your pipeline folder structure in a location other than your application folder, you must modify the paths shown in the table accordingly.</span></span> <span data-ttu-id="524fc-303">请参阅中的管道目录要求的讨论[管线开发要求](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)。</span><span class="sxs-lookup"><span data-stu-id="524fc-303">See the discussion of pipeline directory requirements in [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
2.  <span data-ttu-id="524fc-304">生成 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="524fc-304">Build the Visual Studio solution.</span></span>  
  
3.  <span data-ttu-id="524fc-305">检查应用程序和管道目录，以确保程序集已复制到正确的目录，并在错误的文件夹已安装的程序集没有额外的副本。</span><span class="sxs-lookup"><span data-stu-id="524fc-305">Check the application and pipeline directories to ensure that the assemblies were copied to the correct directories and that no extra copies of assemblies were installed in the wrong folders.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="524fc-306">如果未更改**Copy Local**到**False**有关`Calc1AddInView`项目中的引用`AddInCalcV1`项目中，加载程序上下文的问题将使外接程序无法位于。</span><span class="sxs-lookup"><span data-stu-id="524fc-306">If you did not change **Copy Local** to **False** for the `Calc1AddInView` project reference in the `AddInCalcV1` project, loader context problems will prevent the add-in from being located.</span></span>  
  
     <span data-ttu-id="524fc-307">有关如何部署到管道的信息，请参阅[管线开发要求](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)。</span><span class="sxs-lookup"><span data-stu-id="524fc-307">For information about deploying to the pipeline, see [Pipeline Development Requirements](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
## <a name="running-the-host-application"></a><span data-ttu-id="524fc-308">运行主机应用程序</span><span class="sxs-lookup"><span data-stu-id="524fc-308">Running the Host Application</span></span>  
 <span data-ttu-id="524fc-309">现在您就可以运行宿主和外接程序与之交互。</span><span class="sxs-lookup"><span data-stu-id="524fc-309">You are now ready to run the host and interact with the add-in.</span></span>  
  
#### <a name="to-run-the-host-application"></a><span data-ttu-id="524fc-310">若要运行主机应用程序</span><span class="sxs-lookup"><span data-stu-id="524fc-310">To run the host application</span></span>  
  
1.  <span data-ttu-id="524fc-311">在命令提示符处，转到应用程序目录并运行主机应用程序， `Calc1Host.exe`。</span><span class="sxs-lookup"><span data-stu-id="524fc-311">At the command prompt, go to the application directory and run the host application, `Calc1Host.exe`.</span></span>  
  
2.  <span data-ttu-id="524fc-312">主机查找所有可用的插件的其类型，并提示您选择外接程序。</span><span class="sxs-lookup"><span data-stu-id="524fc-312">The host finds all available add-ins of its type and prompts you to select an add-in.</span></span> <span data-ttu-id="524fc-313">输入**1** for 仅可用外接程序。</span><span class="sxs-lookup"><span data-stu-id="524fc-313">Enter **1** for the only available add-in.</span></span>  
  
3.  <span data-ttu-id="524fc-314">为计算器，如输入等式**2 + 2**。</span><span class="sxs-lookup"><span data-stu-id="524fc-314">Enter an equation for the calculator, such as **2 + 2**.</span></span> <span data-ttu-id="524fc-315">必须有数字和运算符之间的空格。</span><span class="sxs-lookup"><span data-stu-id="524fc-315">There must be spaces between the numbers and the operator.</span></span>  
  
4.  <span data-ttu-id="524fc-316">类型**退出**然后按**Enter**键关闭该应用程序。</span><span class="sxs-lookup"><span data-stu-id="524fc-316">Type **exit** and press the **Enter** key to close the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="524fc-317">请参阅</span><span class="sxs-lookup"><span data-stu-id="524fc-317">See Also</span></span>  
 [<span data-ttu-id="524fc-318">演练： 启用向后的兼容性作为在宿主发生变化</span><span class="sxs-lookup"><span data-stu-id="524fc-318">Walkthrough: Enabling Backward Compatibility as Your Host Changes</span></span>](https://msdn.microsoft.com/library/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
 [<span data-ttu-id="524fc-319">演练： 在宿主和外接程序之间传递集合</span><span class="sxs-lookup"><span data-stu-id="524fc-319">Walkthrough: Passing Collections Between Hosts and Add-Ins</span></span>](https://msdn.microsoft.com/library/b532c604-548e-4fab-b11c-377257dd0ee5)  
 [<span data-ttu-id="524fc-320">管线开发要求</span><span class="sxs-lookup"><span data-stu-id="524fc-320">Pipeline Development Requirements</span></span>](https://msdn.microsoft.com/library/ef9fa986-e80b-43e1-868b-247f4c1d9da5)  
 [<span data-ttu-id="524fc-321">协定、 视图和适配器</span><span class="sxs-lookup"><span data-stu-id="524fc-321">Contracts, Views, and Adapters</span></span>](https://msdn.microsoft.com/library/a6460173-9507-4b87-8c07-d4ee245d715c)  
 [<span data-ttu-id="524fc-322">管道开发</span><span class="sxs-lookup"><span data-stu-id="524fc-322">Pipeline Development</span></span>](../../../docs/framework/add-ins/pipeline-development.md)
