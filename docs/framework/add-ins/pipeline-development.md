---
title: "管线开发"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- add-in pipeline [.NET Framework], segments
- activation path for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], activation path
- communication pipeline for add-ins [.NET Framework]
- add-in pipeline [.NET Framework], about
- add-ins [.NET Framework], pipeline development
ms.assetid: 932788f2-b87d-44cf-82f9-04492a8b2722
caps.latest.revision: "31"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4991fc65a48d620d30d09c44f1a30c2d1839071e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="pipeline-development"></a><span data-ttu-id="94b95-102">管线开发</span><span class="sxs-lookup"><span data-stu-id="94b95-102">Pipeline Development</span></span>
<span data-ttu-id="94b95-103">外接程序管线是主机应用程序和其外接程序必须使用才能相互之间进行通信的管道段的路径。</span><span class="sxs-lookup"><span data-stu-id="94b95-103">The add-in pipeline is the path of pipeline segments that the host application and its add-in must use to communicate with each other.</span></span>  
  
 <span data-ttu-id="94b95-104">下图显示的通信管道和其片段。</span><span class="sxs-lookup"><span data-stu-id="94b95-104">The following illustration shows the communication pipeline and its segments.</span></span>  
  
 <span data-ttu-id="94b95-105">![添加 &#45; 管道模型中。] (../../../docs/framework/add-ins/media/addin1.png "AddIn1")</span><span class="sxs-lookup"><span data-stu-id="94b95-105">![Add&#45;in pipeline model.](../../../docs/framework/add-ins/media/addin1.png "AddIn1")</span></span>  
<span data-ttu-id="94b95-106">外接程序管道</span><span class="sxs-lookup"><span data-stu-id="94b95-106">Add-in pipeline</span></span>  
  
 <span data-ttu-id="94b95-107">主机应用程序是管道的另一端外, 接程序在另一端。</span><span class="sxs-lookup"><span data-stu-id="94b95-107">The host application is at one end of the pipeline and the add-in is at the other end.</span></span> <span data-ttu-id="94b95-108">从每个结尾和向中间移动，主机应用程序和外接程序将具有一个定义它们都共享的对象模型的视图的抽象基类。</span><span class="sxs-lookup"><span data-stu-id="94b95-108">Starting from each end and moving toward the middle, both the host application and the add-in have an abstract base class that defines a view of the object model that they both share.</span></span> <span data-ttu-id="94b95-109">这些类型 （类） 构成了外接程序视图管道段和外接程序管线段的主机视图。</span><span class="sxs-lookup"><span data-stu-id="94b95-109">These types (classes) make up the add-in view pipeline segment and the host view of the add-in pipeline segment.</span></span> <span data-ttu-id="94b95-110">外接程序视图管道段通常包含多个抽象类，但外接程序继承自的类称为外接程序基准。</span><span class="sxs-lookup"><span data-stu-id="94b95-110">The add-in view pipeline segment often contains more than one abstract class but the class that the add-in inherits from is known as the add-in base.</span></span>  
  
 <span data-ttu-id="94b95-111">外接程序端适配器管道段和主机端适配器管线段转换其视图管道段和协定管道段之间的类型的流。</span><span class="sxs-lookup"><span data-stu-id="94b95-111">The add-in-side adapter pipeline segment and the host-side adapter pipeline segment convert the flow of types between their view pipeline segments and the contract pipeline segment.</span></span> <span data-ttu-id="94b95-112">中央管道段是派生自协定<xref:System.AddIn.Contract.IContract>接口。</span><span class="sxs-lookup"><span data-stu-id="94b95-112">The central segment of the pipeline is a contract that is derived from the <xref:System.AddIn.Contract.IContract> interface.</span></span> <span data-ttu-id="94b95-113">此协定定义主机应用程序和其外接程序将同时使用的方法。</span><span class="sxs-lookup"><span data-stu-id="94b95-113">This contract defines the methods that the host application and its add-in will both use.</span></span>  
  
 <span data-ttu-id="94b95-114">如果将主机和外接程序加载到单独的应用程序域中，则必须分隔主机应用程序从范围的外接程序的作用域的隔离边界。</span><span class="sxs-lookup"><span data-stu-id="94b95-114">If you load the host and the add-in into separate application domains, you have an isolation boundary that separates the scope of the host application from the scope of the add-in.</span></span> <span data-ttu-id="94b95-115">协定是在主机和外接程序应用程序域中加载的唯一程序集。</span><span class="sxs-lookup"><span data-stu-id="94b95-115">The contract is the only assembly that is loaded in both the host and add-in application domains.</span></span> <span data-ttu-id="94b95-116">主机和外接程序每个仅引用其视图协定方法。</span><span class="sxs-lookup"><span data-stu-id="94b95-116">The host and the add-in each refer only to their view of the contract methods.</span></span> <span data-ttu-id="94b95-117">因此，它们被隔开的从协定的抽象层。</span><span class="sxs-lookup"><span data-stu-id="94b95-117">Therefore, they are separated by a layer of abstraction from the contract.</span></span>  
  
 <span data-ttu-id="94b95-118">若要开发管道段，必须创建将包含它们的目录结构。</span><span class="sxs-lookup"><span data-stu-id="94b95-118">To develop pipeline segments, you must create a directory structure that will contain them.</span></span> <span data-ttu-id="94b95-119">有关开发要求和作用域准则的详细信息，请参阅[管线开发要求](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5)。</span><span class="sxs-lookup"><span data-stu-id="94b95-119">For more information about development requirements and scope guidelines, see [Pipeline Development Requirements](http://msdn.microsoft.com/en-us/ef9fa986-e80b-43e1-868b-247f4c1d9da5).</span></span>  
  
 <span data-ttu-id="94b95-120">下图显示构成的管道段的类型。</span><span class="sxs-lookup"><span data-stu-id="94b95-120">The following illustration shows the types that make up the pipeline segments.</span></span> <span data-ttu-id="94b95-121">在图中所示的类型的名称是任意的但主机和主机除外的所有类型都视图之外的外接程序中需要特性使构造信息存储的方法可以发现它们。</span><span class="sxs-lookup"><span data-stu-id="94b95-121">The names of the types shown in the illustration are arbitrary, but all types except for the host and the host view of the add-in require attributes so they can be discovered by methods that construct an information store.</span></span>  
  
 <span data-ttu-id="94b95-122">![添加 &#45; 在模型中具有必需特性的类型。] (../../../docs/framework/add-ins/media/addin-model.png "AddIn_Model")</span><span class="sxs-lookup"><span data-stu-id="94b95-122">![Add&#45;in model with required attributes on types.](../../../docs/framework/add-ins/media/addin-model.png "AddIn_Model")</span></span>  
<span data-ttu-id="94b95-123">类型与外接程序管线</span><span class="sxs-lookup"><span data-stu-id="94b95-123">Add-in pipeline with types</span></span>  
  
 <span data-ttu-id="94b95-124">下表描述了有关激活外接程序中的管道段。</span><span class="sxs-lookup"><span data-stu-id="94b95-124">The following table describes the pipeline segments for activating an add-in.</span></span> <span data-ttu-id="94b95-125">有关这些段的详细信息，请参阅[协定、 视图和适配器](http://msdn.microsoft.com/en-us/a6460173-9507-4b87-8c07-d4ee245d715c)。</span><span class="sxs-lookup"><span data-stu-id="94b95-125">For more information about these segments, see [Contracts, Views, and Adapters](http://msdn.microsoft.com/en-us/a6460173-9507-4b87-8c07-d4ee245d715c).</span></span>  
  
|<span data-ttu-id="94b95-126">管道段</span><span class="sxs-lookup"><span data-stu-id="94b95-126">Pipeline segment</span></span>|<span data-ttu-id="94b95-127">描述</span><span class="sxs-lookup"><span data-stu-id="94b95-127">Description</span></span>|  
|----------------------|-----------------|  
|<span data-ttu-id="94b95-128">Host</span><span class="sxs-lookup"><span data-stu-id="94b95-128">Host</span></span>|<span data-ttu-id="94b95-129">为应用程序集创建的外接程序的实例。</span><span class="sxs-lookup"><span data-stu-id="94b95-129">The application assembly that creates an instance of an add-in.</span></span>|  
|<span data-ttu-id="94b95-130">外接程序的主机视图</span><span class="sxs-lookup"><span data-stu-id="94b95-130">Host view of the add-in</span></span>|<span data-ttu-id="94b95-131">表示对象类型以及用于与外接程序进行通信的方法的主机应用程序的视图。</span><span class="sxs-lookup"><span data-stu-id="94b95-131">Represents the host application's view of the object types and methods used to communicate with the add-in.</span></span> <span data-ttu-id="94b95-132">主机视图是一个抽象基类或接口。</span><span class="sxs-lookup"><span data-stu-id="94b95-132">The host view is an abstract base class or interface.</span></span>|  
|<span data-ttu-id="94b95-133">主机端适配器</span><span class="sxs-lookup"><span data-stu-id="94b95-133">Host-side adapter</span></span>|<span data-ttu-id="94b95-134">采用与其他协定的方法与一个或多个类程序集。</span><span class="sxs-lookup"><span data-stu-id="94b95-134">An assembly with one or more classes that adapts methods to and from the contract.</span></span><br /><br /> <span data-ttu-id="94b95-135">通过标识此管道段<xref:System.AddIn.Pipeline.HostAdapterAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="94b95-135">This pipeline segment is identified by using the <xref:System.AddIn.Pipeline.HostAdapterAttribute> attribute.</span></span><br /><br /> <span data-ttu-id="94b95-136">不支持多模块程序集。</span><span class="sxs-lookup"><span data-stu-id="94b95-136">Multi-module assemblies are not supported.</span></span>|  
|<span data-ttu-id="94b95-137">协定</span><span class="sxs-lookup"><span data-stu-id="94b95-137">Contract</span></span>|<span data-ttu-id="94b95-138">派生自的接口<xref:System.AddIn.Contract.IContract>接口，并且定义主机和其外接程序之间的通信类型的协议。</span><span class="sxs-lookup"><span data-stu-id="94b95-138">An interface that is derived from the <xref:System.AddIn.Contract.IContract> interface and that defines the protocol for communicating types between the host and its add-in.</span></span><br /><br /> <span data-ttu-id="94b95-139">通过设置标识此管道段<xref:System.AddIn.Pipeline.AddInContractAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="94b95-139">This pipeline segment is identified by setting the <xref:System.AddIn.Pipeline.AddInContractAttribute> attribute.</span></span>|  
|<span data-ttu-id="94b95-140">的外接程序端适配器</span><span class="sxs-lookup"><span data-stu-id="94b95-140">Add-in-side adapter</span></span>|<span data-ttu-id="94b95-141">采用与其他协定的方法与一个或多个类程序集。</span><span class="sxs-lookup"><span data-stu-id="94b95-141">An assembly with one or more classes that adapts methods to and from the contract.</span></span><br /><br /> <span data-ttu-id="94b95-142">通过标识此管道段<xref:System.AddIn.Pipeline.AddInAdapterAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="94b95-142">This pipeline segment is identified by using the <xref:System.AddIn.Pipeline.AddInAdapterAttribute> attribute.</span></span><br /><br /> <span data-ttu-id="94b95-143">包含具有的类型的外接程序端适配器目录中的每个程序集<xref:System.AddIn.Pipeline.AddInAdapterAttribute>属性加载到外接程序的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="94b95-143">Each assembly in the add-in-side adapter directory that contains a type that has an <xref:System.AddIn.Pipeline.AddInAdapterAttribute> attribute is loaded into the add-in's application domain.</span></span><br /><br /> <span data-ttu-id="94b95-144">在其自己的应用程序域中将会加载外接程序端目录中的每个程序集。</span><span class="sxs-lookup"><span data-stu-id="94b95-144">Each assembly in the add-in-side directory is loaded in its own application domain.</span></span><br /><br /> <span data-ttu-id="94b95-145">不支持多模块程序集</span><span class="sxs-lookup"><span data-stu-id="94b95-145">Multi-module assemblies are not supported</span></span>|  
|<span data-ttu-id="94b95-146">外接程序视图</span><span class="sxs-lookup"><span data-stu-id="94b95-146">Add-in view</span></span>|<span data-ttu-id="94b95-147">表示外接程序的视图对象类型以及用于与主机通信的方法的程序集。</span><span class="sxs-lookup"><span data-stu-id="94b95-147">An assembly that represents the add-in's view of the object types and methods that are used to communicate with the host.</span></span> <span data-ttu-id="94b95-148">外接程序视图是一个抽象基类或接口。</span><span class="sxs-lookup"><span data-stu-id="94b95-148">The add-in view is an abstract base class or interface.</span></span><br /><br /> <span data-ttu-id="94b95-149">通过标识此管道段<xref:System.AddIn.Pipeline.AddInBaseAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="94b95-149">This pipeline segment is identified by using the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute.</span></span><br /><br /> <span data-ttu-id="94b95-150">包含具有的类型的 AddInViews 目录中的每个程序集<xref:System.AddIn.Pipeline.AddInBaseAttribute>属性加载到外接程序的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="94b95-150">Each assembly in the AddInViews directory that contains a type that has an <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute is loaded into the add-in's application domain.</span></span>|  
|<span data-ttu-id="94b95-151">外接程序</span><span class="sxs-lookup"><span data-stu-id="94b95-151">Add-in</span></span>|<span data-ttu-id="94b95-152">执行某项服务主机实例化的类型。</span><span class="sxs-lookup"><span data-stu-id="94b95-152">An instantiated type that performs a service for the host.</span></span>|  
  
## <a name="pipeline-activation-path"></a><span data-ttu-id="94b95-153">管道激活路径</span><span class="sxs-lookup"><span data-stu-id="94b95-153">Pipeline Activation Path</span></span>  
 <span data-ttu-id="94b95-154">当激活外接程序时下, 图显示类型的激活。</span><span class="sxs-lookup"><span data-stu-id="94b95-154">The following illustration shows the activation of types when an add-in is activated.</span></span> <span data-ttu-id="94b95-155">它还显示到主机，如计算或对象的集合的结果的传递的对象。</span><span class="sxs-lookup"><span data-stu-id="94b95-155">It also shows the passing of objects to the host, such as the results of a calculation or a collection of objects.</span></span> <span data-ttu-id="94b95-156">这是最典型的情形。</span><span class="sxs-lookup"><span data-stu-id="94b95-156">This is the most typical scenario.</span></span>  
  
 <span data-ttu-id="94b95-157">![添加 &#45; 具有激活路径的模型中。] (../../../docs/framework/add-ins/media/addin6.png "AddIn6")</span><span class="sxs-lookup"><span data-stu-id="94b95-157">![Add&#45;in model with activation path.](../../../docs/framework/add-ins/media/addin6.png "AddIn6")</span></span>  
<span data-ttu-id="94b95-158">从外接程序到宿主的激活路径</span><span class="sxs-lookup"><span data-stu-id="94b95-158">Activation path from the add-in to the host</span></span>  
  
 <span data-ttu-id="94b95-159">管道的激活路径发生，如下所示：</span><span class="sxs-lookup"><span data-stu-id="94b95-159">The activation path of the pipeline occurs as follows:</span></span>  
  
1.  <span data-ttu-id="94b95-160">主机应用程序激活外接程序与<xref:System.AddIn.Hosting.AddInToken.Activate%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="94b95-160">The host application activates the add-in with the <xref:System.AddIn.Hosting.AddInToken.Activate%2A> method.</span></span>  
  
2.  <span data-ttu-id="94b95-161">外接程序中外, 接程序视图、 外接程序端适配器和协定程序集加载到外接程序的应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="94b95-161">The add-in, add-in view, add-in-side adapter, and the contract assemblies are loaded into the add-in's application domain.</span></span>  
  
3.  <span data-ttu-id="94b95-162">使用外接程序视图创建外接程序端适配器的实例 (与类由标识<xref:System.AddIn.Pipeline.AddInBaseAttribute>属性) 作为其构造函数。</span><span class="sxs-lookup"><span data-stu-id="94b95-162">An instance of the add-in-side adapter is created using the add-in view (with the class identified by the <xref:System.AddIn.Pipeline.AddInBaseAttribute> attribute) as its constructor.</span></span> <span data-ttu-id="94b95-163">外接程序端适配器从协定继承。</span><span class="sxs-lookup"><span data-stu-id="94b95-163">The add-in-side adapter inherits from the contract.</span></span>  
  
4.  <span data-ttu-id="94b95-164">外接程序端适配器，将类型化为协定，跨 （可选） 隔离边界传递给主机端适配器的构造函数。</span><span class="sxs-lookup"><span data-stu-id="94b95-164">The add-in-side adapter, which is typed as the contract, is passed across the (optional) isolation boundary to the host-side adapter's constructor.</span></span>  
  
5.  <span data-ttu-id="94b95-165">外接程序、 宿主端适配器和协定程序集的主机视图加载到主机的应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="94b95-165">The host view of the add-in, host-side adapter, and the contract assemblies are loaded into the host's application domain.</span></span>  
  
6.  <span data-ttu-id="94b95-166">使用协定作为其构造函数创建的主机端适配器实例。</span><span class="sxs-lookup"><span data-stu-id="94b95-166">An instance of the host-side adapter is created using the contract as its constructor.</span></span> <span data-ttu-id="94b95-167">主机端适配器继承自的外接程序的主机视图。</span><span class="sxs-lookup"><span data-stu-id="94b95-167">The host-side adapter inherits from the host view of the add-in.</span></span>  
  
7.  <span data-ttu-id="94b95-168">主机有外接程序，这类型的主机的外接程序时，查看并可以继续调用其方法。</span><span class="sxs-lookup"><span data-stu-id="94b95-168">The host has the add-in, which is typed as the host view of the add-in, and can continue calling its methods.</span></span>  
  
## <a name="walkthroughs"></a><span data-ttu-id="94b95-169">演练</span><span class="sxs-lookup"><span data-stu-id="94b95-169">Walkthroughs</span></span>  
 <span data-ttu-id="94b95-170">有三个描述如何创建使用 Visual Studio 的管道的演练主题：</span><span class="sxs-lookup"><span data-stu-id="94b95-170">There are three walkthrough topics that describe how to create pipelines using Visual Studio:</span></span>  
  
-   [<span data-ttu-id="94b95-171">演练： 创建可扩展应用程序</span><span class="sxs-lookup"><span data-stu-id="94b95-171">Walkthrough: Creating an Extensible Application</span></span>](../../../docs/framework/add-ins/walkthrough-create-extensible-app.md)  
  
     <span data-ttu-id="94b95-172">描述一个计算器外接程序，执行加法、 减法、 乘法和除法计算的主机。</span><span class="sxs-lookup"><span data-stu-id="94b95-172">Describes a calculator add-in that performs addition, subtraction, multiplication, and divsion calculations for the host.</span></span>  
  
-   [<span data-ttu-id="94b95-173">演练： 启用主机更改为向后的兼容性</span><span class="sxs-lookup"><span data-stu-id="94b95-173">Walkthrough: Enabling Backward Compatibility as Your Host Changes</span></span>](http://msdn.microsoft.com/en-us/6fa15bb5-8f04-407d-bd7d-675dc043c848)  
  
     <span data-ttu-id="94b95-174">描述一个计算器外接程序使用增强的计算功能，以及如何维护与第一个计算器外接程序的兼容性。</span><span class="sxs-lookup"><span data-stu-id="94b95-174">Describes a calculator add-in with enhanced calculation capabilities, and how to maintain compatibility with the first calculator add-in.</span></span>  
  
-   [<span data-ttu-id="94b95-175">主机和外接程序之间的演练： 传递集合</span><span class="sxs-lookup"><span data-stu-id="94b95-175">Walkthrough: Passing Collections Between Hosts and Add-Ins</span></span>](http://msdn.microsoft.com/en-us/b532c604-548e-4fab-b11c-377257dd0ee5)  
  
     <span data-ttu-id="94b95-176">描述如何通过使用书店方案管道传递数据集合。</span><span class="sxs-lookup"><span data-stu-id="94b95-176">Describes how to pass data collections over the pipeline using a book store scenario.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94b95-177">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94b95-177">See Also</span></span>  
 [<span data-ttu-id="94b95-178">外接程序管线方案</span><span class="sxs-lookup"><span data-stu-id="94b95-178">Add-in Pipeline Scenarios</span></span>](http://msdn.microsoft.com/en-us/feb70e0b-8734-494c-aeaf-b567f014043e)  
 [<span data-ttu-id="94b95-179">外接程序和扩展性</span><span class="sxs-lookup"><span data-stu-id="94b95-179">Add-ins and Extensibility</span></span>](../../../docs/framework/add-ins/index.md)
