---
title: 设计和实现自定义活动
ms.date: 03/30/2017
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
ms.openlocfilehash: 2ed80b5cbb27c6647053ee9b8f4cd2bedb0c6cde
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513808"
---
# <a name="designing-and-implementing-custom-activities"></a><span data-ttu-id="91705-102">设计和实现自定义活动</span><span class="sxs-lookup"><span data-stu-id="91705-102">Designing and Implementing Custom Activities</span></span>
<span data-ttu-id="91705-103">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] 中自定义活动的创建途径有二：或是将系统提供的活动组装成组合活动，或是创建派生自 <xref:System.Activities.CodeActivity>、<xref:System.Activities.AsyncCodeActivity> 或 <xref:System.Activities.NativeActivity> 的新类型。</span><span class="sxs-lookup"><span data-stu-id="91705-103">Custom activities in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] are created by either assembling system-provided activities into composite activities or by creating new types that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, or <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="91705-104">本节介绍如何使用任一方法来创建自定义活动。</span><span class="sxs-lookup"><span data-stu-id="91705-104">This section describes how to create custom activities with either method.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="91705-105">自定义活动在工作流设计器中默认显示为一个包含活动名称的简单矩形。</span><span class="sxs-lookup"><span data-stu-id="91705-105">Custom activities by default display within the workflow designer as a simple rectangle with the activity’s name.</span></span> <span data-ttu-id="91705-106">若要在工作流设计器中为您的活动提供自定义可视化表示形式，还必须创建自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="91705-106">To provide a custom visual representation of your activity in the workflow designer you must also create a custom designer.</span></span> <span data-ttu-id="91705-107">有关详细信息，请参阅[使用自定义活动设计器和模板](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="91705-107">For more information, see [Using Custom Activity Designers and Templates](../../../docs/framework/windows-workflow-foundation/using-custom-activity-designers-and-templates.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="91705-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="91705-108">In This Section</span></span>  
 [<span data-ttu-id="91705-109">活动创建选项</span><span class="sxs-lookup"><span data-stu-id="91705-109">Activity Authoring Options</span></span>](../../../docs/framework/windows-workflow-foundation/activity-authoring-options-in-wf.md)  
 <span data-ttu-id="91705-110">讨论可在 [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]中使用的创作样式。</span><span class="sxs-lookup"><span data-stu-id="91705-110">Discusses the authoring styles available in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="91705-111">使用自定义活动</span><span class="sxs-lookup"><span data-stu-id="91705-111">Using a custom activity</span></span>](../../../docs/framework/windows-workflow-foundation/using-a-custom-activity.md)  
 <span data-ttu-id="91705-112">描述如何将自定义活动添加到工作流项目。</span><span class="sxs-lookup"><span data-stu-id="91705-112">Describes how to add a custom activity to a workflow project.</span></span>  
  
  [<span data-ttu-id="91705-113">创建异步活动</span><span class="sxs-lookup"><span data-stu-id="91705-113">Creating Asynchronous Activities</span></span>](../../../docs/framework/windows-workflow-foundation/creating-asynchronous-activities-in-wf.md)  
 <span data-ttu-id="91705-114">描述如何创建异步活动。</span><span class="sxs-lookup"><span data-stu-id="91705-114">Describes how to create asynchronous activities.</span></span>  
  
 [<span data-ttu-id="91705-115">配置活动验证</span><span class="sxs-lookup"><span data-stu-id="91705-115">Configuring Activity Validation</span></span>](../../../docs/framework/windows-workflow-foundation/configuring-activity-validation.md)  
 <span data-ttu-id="91705-116">描述如何使用活动验证在执行活动之前发现并报告活动配置中的错误。</span><span class="sxs-lookup"><span data-stu-id="91705-116">Describes how activity validation can be used to identify and report errors in an activity’s configuration prior to its execution.</span></span>  
  
 [<span data-ttu-id="91705-117">在运行时创建活动</span><span class="sxs-lookup"><span data-stu-id="91705-117">Creating an Activity at Runtime</span></span>](../../../docs/framework/windows-workflow-foundation/creating-an-activity-at-runtime-with-dynamicactivity.md)  
 <span data-ttu-id="91705-118">讨论如何使用 <xref:System.Activities.DynamicActivity> 在运行时创建活动。</span><span class="sxs-lookup"><span data-stu-id="91705-118">Discusses how to create activities at runtime using <xref:System.Activities.DynamicActivity>.</span></span>  
  
 [<span data-ttu-id="91705-119">工作流执行属性</span><span class="sxs-lookup"><span data-stu-id="91705-119">Workflow Execution Properties</span></span>](../../../docs/framework/windows-workflow-foundation/workflow-execution-properties.md)  
 <span data-ttu-id="91705-120">描述如何使用工作流执行属性将上下文特定属性添加到活动的环境中。</span><span class="sxs-lookup"><span data-stu-id="91705-120">Describes how to use workflow execution properties to add context specific properties to an activity’s environment</span></span>  
  
 [<span data-ttu-id="91705-121">使用活动委托</span><span class="sxs-lookup"><span data-stu-id="91705-121">Using Activity Delegates</span></span>](../../../docs/framework/windows-workflow-foundation/using-activity-delegates.md)  
 <span data-ttu-id="91705-122">讨论如何编写和使用包含活动代理的活动。</span><span class="sxs-lookup"><span data-stu-id="91705-122">Discusses how to author and use activities that contain activity delegates.</span></span>  
  
 [<span data-ttu-id="91705-123">活动本地化</span><span class="sxs-lookup"><span data-stu-id="91705-123">Activity Localization</span></span>](../../../docs/framework/windows-workflow-foundation/activity-localization.md)  
 <span data-ttu-id="91705-124">描述如何在活动中使用本地化的字符串资源。</span><span class="sxs-lookup"><span data-stu-id="91705-124">Describes how to use localization of string resources in activities.</span></span>  
  
 [<span data-ttu-id="91705-125">使用活动扩展</span><span class="sxs-lookup"><span data-stu-id="91705-125">Using Activity Extensions</span></span>](../../../docs/framework/windows-workflow-foundation/using-activity-extensions.md)  
 <span data-ttu-id="91705-126">描述如何编写和使用活动扩展。</span><span class="sxs-lookup"><span data-stu-id="91705-126">Describes how to author and use activity extensions.</span></span>  
  
 [<span data-ttu-id="91705-127">使用工作流中的 OData 源</span><span class="sxs-lookup"><span data-stu-id="91705-127">Consuming OData Feeds from a Workflow</span></span>](../../../docs/framework/windows-workflow-foundation/consuming-odata-feeds-from-a-workflow.md)  
 <span data-ttu-id="91705-128">描述从工作流中调用 WCF 数据服务的几种方法。</span><span class="sxs-lookup"><span data-stu-id="91705-128">Describes several methods for calling a WCF Data Service from a workflow.</span></span>  
  
 [<span data-ttu-id="91705-129">活动定义范围和可见性</span><span class="sxs-lookup"><span data-stu-id="91705-129">Activity Definition Scoping and Visibility</span></span>](../../../docs/framework/windows-workflow-foundation/activity-definition-scoping-and-visibility.md)  
 <span data-ttu-id="91705-130">描述用于定义数据范围和活动成员可见性的选项和规则。</span><span class="sxs-lookup"><span data-stu-id="91705-130">Describes the options and rules for defining data scoping and member visibility for activities.</span></span>
