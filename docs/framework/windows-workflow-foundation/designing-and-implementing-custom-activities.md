---
title: 设计和实现自定义活动
description: 本文提供了一些资源，用于在 Workflow Foundation 中创建自定义活动，方法是创建复合活动或创建新的活动类型。
ms.date: 03/30/2017
ms.assetid: 4e30e63d-6e33-4842-a7a4-ce807cef1fad
ms.openlocfilehash: 9c184bff9518bb5581f3bf4cd408db224736192b
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419988"
---
# <a name="designing-and-implementing-custom-activities"></a><span data-ttu-id="63ac7-103">设计和实现自定义活动</span><span class="sxs-lookup"><span data-stu-id="63ac7-103">Designing and Implementing Custom Activities</span></span>
<span data-ttu-id="63ac7-104">[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] 中自定义活动的创建途径有二：或是将系统提供的活动组装成组合活动，或是创建派生自 <xref:System.Activities.CodeActivity>、<xref:System.Activities.AsyncCodeActivity> 或 <xref:System.Activities.NativeActivity> 的新类型。</span><span class="sxs-lookup"><span data-stu-id="63ac7-104">Custom activities in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] are created by either assembling system-provided activities into composite activities or by creating new types that derive from <xref:System.Activities.CodeActivity>, <xref:System.Activities.AsyncCodeActivity>, or <xref:System.Activities.NativeActivity>.</span></span> <span data-ttu-id="63ac7-105">本节介绍如何使用任一方法来创建自定义活动。</span><span class="sxs-lookup"><span data-stu-id="63ac7-105">This section describes how to create custom activities with either method.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="63ac7-106">自定义活动在工作流设计器中默认显示为一个包含活动名称的简单矩形。</span><span class="sxs-lookup"><span data-stu-id="63ac7-106">Custom activities by default display within the workflow designer as a simple rectangle with the activity’s name.</span></span> <span data-ttu-id="63ac7-107">若要在工作流设计器中为您的活动提供自定义可视化表示形式，还必须创建自定义设计器。</span><span class="sxs-lookup"><span data-stu-id="63ac7-107">To provide a custom visual representation of your activity in the workflow designer you must also create a custom designer.</span></span> <span data-ttu-id="63ac7-108">有关详细信息，请参阅[使用自定义活动设计器和模板](using-custom-activity-designers-and-templates.md)。</span><span class="sxs-lookup"><span data-stu-id="63ac7-108">For more information, see [Using Custom Activity Designers and Templates](using-custom-activity-designers-and-templates.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="63ac7-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="63ac7-109">In This Section</span></span>  
 [<span data-ttu-id="63ac7-110">活动创建选项</span><span class="sxs-lookup"><span data-stu-id="63ac7-110">Activity Authoring Options</span></span>](activity-authoring-options-in-wf.md)  
 <span data-ttu-id="63ac7-111">讨论可在 [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)]中使用的创作样式。</span><span class="sxs-lookup"><span data-stu-id="63ac7-111">Discusses the authoring styles available in [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)].</span></span>  
  
 [<span data-ttu-id="63ac7-112">使用自定义活动</span><span class="sxs-lookup"><span data-stu-id="63ac7-112">Using a custom activity</span></span>](using-a-custom-activity.md)  
 <span data-ttu-id="63ac7-113">描述如何将自定义活动添加到工作流项目。</span><span class="sxs-lookup"><span data-stu-id="63ac7-113">Describes how to add a custom activity to a workflow project.</span></span>  
  
  [<span data-ttu-id="63ac7-114">创建异步活动</span><span class="sxs-lookup"><span data-stu-id="63ac7-114">Creating Asynchronous Activities</span></span>](creating-asynchronous-activities-in-wf.md)  
 <span data-ttu-id="63ac7-115">描述如何创建异步活动。</span><span class="sxs-lookup"><span data-stu-id="63ac7-115">Describes how to create asynchronous activities.</span></span>  
  
 [<span data-ttu-id="63ac7-116">配置活动验证</span><span class="sxs-lookup"><span data-stu-id="63ac7-116">Configuring Activity Validation</span></span>](configuring-activity-validation.md)  
 <span data-ttu-id="63ac7-117">描述如何使用活动验证在执行活动之前发现并报告活动配置中的错误。</span><span class="sxs-lookup"><span data-stu-id="63ac7-117">Describes how activity validation can be used to identify and report errors in an activity’s configuration prior to its execution.</span></span>  
  
 [<span data-ttu-id="63ac7-118">在运行时创建活动</span><span class="sxs-lookup"><span data-stu-id="63ac7-118">Creating an Activity at Runtime</span></span>](creating-an-activity-at-runtime-with-dynamicactivity.md)  
 <span data-ttu-id="63ac7-119">讨论如何使用 <xref:System.Activities.DynamicActivity> 在运行时创建活动。</span><span class="sxs-lookup"><span data-stu-id="63ac7-119">Discusses how to create activities at runtime using <xref:System.Activities.DynamicActivity>.</span></span>  
  
 [<span data-ttu-id="63ac7-120">工作流执行属性</span><span class="sxs-lookup"><span data-stu-id="63ac7-120">Workflow Execution Properties</span></span>](workflow-execution-properties.md)  
 <span data-ttu-id="63ac7-121">描述如何使用工作流执行属性将上下文特定属性添加到活动的环境中。</span><span class="sxs-lookup"><span data-stu-id="63ac7-121">Describes how to use workflow execution properties to add context specific properties to an activity’s environment</span></span>  
  
 [<span data-ttu-id="63ac7-122">使用活动委托</span><span class="sxs-lookup"><span data-stu-id="63ac7-122">Using Activity Delegates</span></span>](using-activity-delegates.md)  
 <span data-ttu-id="63ac7-123">讨论如何编写和使用包含活动代理的活动。</span><span class="sxs-lookup"><span data-stu-id="63ac7-123">Discusses how to author and use activities that contain activity delegates.</span></span>
  
 [<span data-ttu-id="63ac7-124">使用活动扩展</span><span class="sxs-lookup"><span data-stu-id="63ac7-124">Using Activity Extensions</span></span>](using-activity-extensions.md)  
 <span data-ttu-id="63ac7-125">描述如何编写和使用活动扩展。</span><span class="sxs-lookup"><span data-stu-id="63ac7-125">Describes how to author and use activity extensions.</span></span>  
  
 [<span data-ttu-id="63ac7-126">使用工作流中的 OData 源</span><span class="sxs-lookup"><span data-stu-id="63ac7-126">Consuming OData Feeds from a Workflow</span></span>](consuming-odata-feeds-from-a-workflow.md)  
 <span data-ttu-id="63ac7-127">描述从工作流中调用 WCF 数据服务的几种方法。</span><span class="sxs-lookup"><span data-stu-id="63ac7-127">Describes several methods for calling a WCF Data Service from a workflow.</span></span>  
  
 [<span data-ttu-id="63ac7-128">活动定义范围和可见性</span><span class="sxs-lookup"><span data-stu-id="63ac7-128">Activity Definition Scoping and Visibility</span></span>](activity-definition-scoping-and-visibility.md)  
 <span data-ttu-id="63ac7-129">描述用于定义数据范围和活动成员可见性的选项和规则。</span><span class="sxs-lookup"><span data-stu-id="63ac7-129">Describes the options and rules for defining data scoping and member visibility for activities.</span></span>
