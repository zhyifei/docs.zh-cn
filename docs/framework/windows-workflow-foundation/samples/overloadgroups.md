---
title: OverloadGroups
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1d547d2-f5fb-4de3-a959-ee6139a4f1ad
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 1c866d337b6e02fa18241b6fafd9d4e5a397ef69
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="overloadgroups"></a><span data-ttu-id="23cb0-102">OverloadGroups</span><span class="sxs-lookup"><span data-stu-id="23cb0-102">OverloadGroups</span></span>
<span data-ttu-id="23cb0-103">此示例包含 `CreateLocation` 活动，它具有两个有趣的特征：</span><span class="sxs-lookup"><span data-stu-id="23cb0-103">This sample consists of an activity (`CreateLocation`), which has two interesting characteristics:</span></span>  
  
1.  <span data-ttu-id="23cb0-104">它具有一些必需的参数和一些可选的参数。</span><span class="sxs-lookup"><span data-stu-id="23cb0-104">It has some required arguments and some optional ones.</span></span>  
  
2.  <span data-ttu-id="23cb0-105">它允许用户选择提供两个不同参数集中的一个。</span><span class="sxs-lookup"><span data-stu-id="23cb0-105">It allows the user to choose to provide one of two different sets of arguments.</span></span>  
  
 <span data-ttu-id="23cb0-106">使用以下两项功能可以实现上述行为：</span><span class="sxs-lookup"><span data-stu-id="23cb0-106">These behaviors are accomplished by using these two features:</span></span>  
  
-   <span data-ttu-id="23cb0-107">`[isRequired]` 验证是否已为某个特定活动的属性赋值，如果没有，则它将引发异常。</span><span class="sxs-lookup"><span data-stu-id="23cb0-107">`[isRequired]` validates that a property of a specific activity is assign, and if not, it throws an exception.</span></span>  
  
-   <span data-ttu-id="23cb0-108">`[OverloadGroup]` 汇集了一组参数，以便活动用户可在两个参数集中选择使用哪一个。</span><span class="sxs-lookup"><span data-stu-id="23cb0-108">`[OverloadGroup]` puts together a set of arguments, so that the user of the activity can choose between using one set or another.</span></span> <span data-ttu-id="23cb0-109">用户不能使用同一实例中不同重载组中的参数。</span><span class="sxs-lookup"><span data-stu-id="23cb0-109">The user cannot use arguments from different Overload Groups in the same instance.</span></span>  
  
 <span data-ttu-id="23cb0-110">在设置不同的工作流之后，调用 <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A>，它将返回<xref:System.Activities.Validation.ValidationResults> 的 <xref:System.Activities.Validation.Constraint> 集合。</span><span class="sxs-lookup"><span data-stu-id="23cb0-110">After setting up different workflows, call <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> which returns a <xref:System.Activities.Validation.ValidationResults> collection of <xref:System.Activities.Validation.Constraint>.</span></span> <span data-ttu-id="23cb0-111">将 <xref:System.Activities.Validation.Constraint> 对象输出到控制台。</span><span class="sxs-lookup"><span data-stu-id="23cb0-111">Print the <xref:System.Activities.Validation.Constraint> objects to the console.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="23cb0-112">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="23cb0-112">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="23cb0-113">打开**OverloadGroups.sln**示例中的解决方案[!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="23cb0-113">Open the **OverloadGroups.sln** sample solution in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="23cb0-114">生成和运行解决方案。</span><span class="sxs-lookup"><span data-stu-id="23cb0-114">Build and run the solution.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="23cb0-115">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="23cb0-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="23cb0-116">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="23cb0-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="23cb0-117">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="23cb0-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="23cb0-118">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="23cb0-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Validation\OverloadGroups`
