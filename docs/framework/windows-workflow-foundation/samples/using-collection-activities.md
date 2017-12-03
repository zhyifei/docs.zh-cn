---
title: "使用集合活动"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e1977cf8-1695-4071-b946-7046fe39601e
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: be7615441f29046fc1a469e3cace86267fc6c031
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="using-collection-activities"></a><span data-ttu-id="5c7f6-102">使用集合活动</span><span class="sxs-lookup"><span data-stu-id="5c7f6-102">Using Collection Activities</span></span>
<span data-ttu-id="5c7f6-103">此示例演示如何将集合活动（<xref:System.Activities.Statements.AddToCollection%601>、<xref:System.Activities.Statements.ClearCollection%601>、<xref:System.Activities.Statements.ExistsInCollection%601> 和 <xref:System.Activities.Statements.RemoveFromCollection%601>）与实现 <xref:System.Collections.ICollection> 接口的类一起使用，以及如何创建一个自定义活动，该活动循环访问集合以输出集合中每个元素的内容。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-103">This sample demonstrates how to use the collection activities (<xref:System.Activities.Statements.AddToCollection%601>, <xref:System.Activities.Statements.ClearCollection%601>, <xref:System.Activities.Statements.ExistsInCollection%601>, and <xref:System.Activities.Statements.RemoveFromCollection%601>) with a class that implements the <xref:System.Collections.ICollection> interface and how to create a custom activity that iterates over a collection to print out the contents of each element in the collection.</span></span> <span data-ttu-id="5c7f6-104">命名为 `PrintCollection` 的自定义活动向控制台输出名为 `Numbers` 的集合的项成员。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-104">The custom activity, which is named `PrintCollection`, prints to the console the item members of a collection named `Numbers`.</span></span>  
  
 <span data-ttu-id="5c7f6-105">下表描述了可提供工作流的集合操作的四个活动。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-105">The following table describes the four activities that provide collection manipulation for workflows.</span></span>  
  
|<span data-ttu-id="5c7f6-106">活动名称</span><span class="sxs-lookup"><span data-stu-id="5c7f6-106">Activity name</span></span>|<span data-ttu-id="5c7f6-107">描述</span><span class="sxs-lookup"><span data-stu-id="5c7f6-107">Description</span></span>|  
|-------------------|-----------------|  
|<xref:System.Activities.Statements.AddToCollection%601>|<span data-ttu-id="5c7f6-108">向集合中添加项。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-108">Adds an item to a collection.</span></span>|  
|<xref:System.Activities.Statements.ClearCollection%601>|<span data-ttu-id="5c7f6-109">清除集合中的所有项。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-109">Clears all items in a collection</span></span>|  
|<xref:System.Activities.Statements.ExistsInCollection%601>|<span data-ttu-id="5c7f6-110">如果集合中存在指定项，则返回 `true`。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-110">Returns `true` if specified item exists in collection.</span></span>|  
|<xref:System.Activities.Statements.RemoveFromCollection%601>|<span data-ttu-id="5c7f6-111">从集合中移除项。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-111">Removes an item from a collection.</span></span>|  
  
 <span data-ttu-id="5c7f6-112">此示例包含两个解决方案，一个位于 CodedWorkflow 目录下，另一个位于 DesignerWorkflow 目录下。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-112">The sample consists of two solutions, one under the CodedWorkflow directory and the other under the DesignerWorkflow directory.</span></span> <span data-ttu-id="5c7f6-113">它们演示了出于同一个目的使用活动的两种不同方式。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-113">They demonstrate two different ways of using the activities for the same purposes.</span></span>  
  
|<span data-ttu-id="5c7f6-114">解决方案</span><span class="sxs-lookup"><span data-stu-id="5c7f6-114">Solution</span></span>|<span data-ttu-id="5c7f6-115">描述</span><span class="sxs-lookup"><span data-stu-id="5c7f6-115">Description</span></span>|<span data-ttu-id="5c7f6-116">主要文件</span><span class="sxs-lookup"><span data-stu-id="5c7f6-116">Main Files</span></span>|  
|-|-|-|  
|<span data-ttu-id="5c7f6-117">CodedWorkflow</span><span class="sxs-lookup"><span data-stu-id="5c7f6-117">CodedWorkflow</span></span>|<span data-ttu-id="5c7f6-118">示例客户端应用程序，它演示如何以编程方式调用集合活动。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-118">Sample client application that demonstrates how to invoke the collection activities programmatically.</span></span>|<span data-ttu-id="5c7f6-119">**PrintCollection.cs**： 用于向控制台输出集合中的每个项的帮助器活动。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-119">**PrintCollection.cs**: helper activity to print out to the console every item in a collection.</span></span><br /><br /> <span data-ttu-id="5c7f6-120">**Program.cs**： 以编程方式生成一个顺序活动包含一系列集合活动，并执行它。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-120">**Program.cs**: programmatically builds a sequence activity that contains a series of collection activities, and executes it.</span></span>|  
|<span data-ttu-id="5c7f6-121">DesignerWorkflow</span><span class="sxs-lookup"><span data-stu-id="5c7f6-121">DesignerWorkflow</span></span>|<span data-ttu-id="5c7f6-122">示例客户端应用程序，它演示如何在工作流设计器中以声明方式使用集合活动。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-122">Sample client application that demonstrates how to use the collection activities declaratively in the workflow designer.</span></span>|<span data-ttu-id="5c7f6-123">**CollectionWorkflow.xaml**： 使用集合活动的设计器以声明方式创建工作流。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-123">**CollectionWorkflow.xaml**: a workflow created declaratively with the designer that uses the collection activities.</span></span><br /><br /> <span data-ttu-id="5c7f6-124">**PrintCollection.cs**： 用于向控制台输出集合中的每个项的帮助器活动。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-124">**PrintCollection.cs**: helper activity to print out to the console every item in a collection.</span></span><br /><br /> <span data-ttu-id="5c7f6-125">**Program.cs**： 调用在 CollectionWorkflow.xaml 中描述的工作流。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-125">**Program.cs**: invokes the workflow described in CollectionWorkflow.xaml.</span></span>|  
  
 <span data-ttu-id="5c7f6-126">在此演示中，使用一个名为 `Numbers` 的自定义活动在控制台上输出 `PrintCollection` 集合的项成员。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-126">In the demonstration, the item members of collection `Numbers` are printed on the console using a custom-defined activity called `PrintCollection`.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="5c7f6-127">使用此示例</span><span class="sxs-lookup"><span data-stu-id="5c7f6-127">To use this sample</span></span>  
  
1.  <span data-ttu-id="5c7f6-128">使用 [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] 打开 Collection.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-128">Using [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], open the Collection.sln solution file.</span></span>  
  
2.  <span data-ttu-id="5c7f6-129">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-129">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="5c7f6-130">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-130">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5c7f6-131">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5c7f6-132">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="5c7f6-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5c7f6-133">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="5c7f6-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5c7f6-134">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="5c7f6-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Collection`