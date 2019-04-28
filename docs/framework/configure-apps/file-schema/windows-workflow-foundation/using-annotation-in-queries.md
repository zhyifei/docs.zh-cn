---
title: 在查询中使用批注
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 50855b30-d5fe-49a9-89d3-3f1bfd670958
ms.openlocfilehash: fd2d98852ca44e3485ddcf4be29d505b39011698
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61614422"
---
# <a name="using-annotation-in-queries"></a><span data-ttu-id="6c92d-102">在查询中使用批注</span><span class="sxs-lookup"><span data-stu-id="6c92d-102">Using Annotation in Queries</span></span>
<span data-ttu-id="6c92d-103">通过批注，可以使用可在生成时后配置的某个值任意标记跟踪记录。</span><span class="sxs-lookup"><span data-stu-id="6c92d-103">Annotations allow you to arbitrarily tag tracking records with a value that can be configured after build time.</span></span> <span data-ttu-id="6c92d-104">例如，可能会在多个工作流使用"邮件服务器"来标记希望多个跟踪记录 = ="Mail Server1"。</span><span class="sxs-lookup"><span data-stu-id="6c92d-104">For example, you might want several tracking records across several workflows to be tagged with "Mail Server" == "Mail Server1".</span></span> <span data-ttu-id="6c92d-105">这样便于在以后查询跟踪记录时查找带有此标记的所有记录。</span><span class="sxs-lookup"><span data-stu-id="6c92d-105">This makes it easy to find all records with this tag when querying tracking records later.</span></span>  
  
## <a name="adding-annotations"></a><span data-ttu-id="6c92d-106">添加批注</span><span class="sxs-lookup"><span data-stu-id="6c92d-106">Adding Annotations</span></span>  
 <span data-ttu-id="6c92d-107">可将批注添加到跟踪查询中，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="6c92d-107">An annotation can be added to a tracking query as shown in the following example.</span></span>  
  
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
>  <span data-ttu-id="6c92d-108">可以使用这些跟踪查询元素创建跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="6c92d-108">These tracking query elements can be used to create a tracking profile.</span></span> <span data-ttu-id="6c92d-109">可以通过配置或使用代码来创建跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="6c92d-109">A tracking profile can be created either in configuration or using code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c92d-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c92d-110">See also</span></span>

- <xref:System.ServiceModel.Activities.Tracking.Configuration.ProfileWorkflowElement>
- <xref:System.Activities.Tracking.TrackingProfile>
- [<span data-ttu-id="6c92d-111">\<participants></span><span class="sxs-lookup"><span data-stu-id="6c92d-111">\<participants></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/participants.md)
- [<span data-ttu-id="6c92d-112">工作流跟踪</span><span class="sxs-lookup"><span data-stu-id="6c92d-112">Workflow Tracking and Tracing</span></span>](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [<span data-ttu-id="6c92d-113">跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="6c92d-113">Tracking Profiles</span></span>](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
