---
title: "在查询中使用批注"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3a6edccba458bfd3629cab851c5d818a69d26173
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="using-annotation-in-queries"></a><span data-ttu-id="1b010-102">在查询中使用批注</span><span class="sxs-lookup"><span data-stu-id="1b010-102">Using Annotation in Queries</span></span>
<span data-ttu-id="1b010-103">通过批注，可以使用可在生成时后配置的某个值任意标记跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="1b010-103">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="1b010-104">例如，你可能希望多个跟踪记录各多个工作流标记使用"Mail Server"= ="Mail Server1"。</span><span class="sxs-lookup"><span data-stu-id="1b010-104">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="1b010-105">这样便于在以后查询跟踪记录时查找带有此标记的所有记录。</span><span class="sxs-lookup"><span data-stu-id="1b010-105">This makes it easy to find all records with this tag when querying tracking records later.</span></span>  
  
## <a name="adding-annotations"></a><span data-ttu-id="1b010-106">添加批注</span><span class="sxs-lookup"><span data-stu-id="1b010-106">Adding Annotations</span></span>  
 <span data-ttu-id="1b010-107">可将批注添加到跟踪查询中，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="1b010-107">An annotation can be added to a tracking query as shown in the following example.</span></span>  
  
```xml  
<activityStateQuery activityName="SendEmailActivity">  
  <states>  
    <state name="Closed"/>  
  </states>  
  <annotations>  
    <annotation name="MailServer" value="Mail Server1"/>  
  </annotations>  
</activityStateQuery>  
```  
  
> [!NOTE]
>  <span data-ttu-id="1b010-108">可以使用这些跟踪查询元素创建跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="1b010-108">These tracking query elements can be used to create a tracking profile.</span></span> <span data-ttu-id="1b010-109">可以通过配置或使用代码来创建跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="1b010-109">A tracking profile can be created either in configuration or using code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b010-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1b010-110">See Also</span></span>  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>  
 <xref:System.Activities.Tracking.TrackingProfile>  
 [<span data-ttu-id="1b010-111">\<参与者 ></span><span class="sxs-lookup"><span data-stu-id="1b010-111">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)  
 [<span data-ttu-id="1b010-112">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="1b010-112">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [<span data-ttu-id="1b010-113">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="1b010-113">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
