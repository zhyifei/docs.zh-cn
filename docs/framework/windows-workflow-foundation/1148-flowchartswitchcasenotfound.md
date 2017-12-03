---
title: 1148 - FlowchartSwitchCaseNotFound
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9ee7fcee-e040-4306-968e-ed840a1cb00c
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4fa173290b528be690b418622baaa2a12e4930cb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1148---flowchartswitchcasenotfound"></a><span data-ttu-id="0c2ef-102">1148 - FlowchartSwitchCaseNotFound</span><span class="sxs-lookup"><span data-stu-id="0c2ef-102">1148 - FlowchartSwitchCaseNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="0c2ef-103">属性</span><span class="sxs-lookup"><span data-stu-id="0c2ef-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0c2ef-104">ID</span><span class="sxs-lookup"><span data-stu-id="0c2ef-104">ID</span></span>|<span data-ttu-id="0c2ef-105">1148</span><span class="sxs-lookup"><span data-stu-id="0c2ef-105">1148</span></span>|  
|<span data-ttu-id="0c2ef-106">关键字</span><span class="sxs-lookup"><span data-stu-id="0c2ef-106">Keywords</span></span>|<span data-ttu-id="0c2ef-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="0c2ef-107">WFActivities</span></span>|  
|<span data-ttu-id="0c2ef-108">级别</span><span class="sxs-lookup"><span data-stu-id="0c2ef-108">Level</span></span>|<span data-ttu-id="0c2ef-109">信息</span><span class="sxs-lookup"><span data-stu-id="0c2ef-109">Information</span></span>|  
|<span data-ttu-id="0c2ef-110">通道</span><span class="sxs-lookup"><span data-stu-id="0c2ef-110">Channel</span></span>|<span data-ttu-id="0c2ef-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="0c2ef-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="0c2ef-112">描述</span><span class="sxs-lookup"><span data-stu-id="0c2ef-112">Description</span></span>  
 <span data-ttu-id="0c2ef-113">指示在 Flowchart 开关中找不到匹配大小写，也找不到默认大小写。</span><span class="sxs-lookup"><span data-stu-id="0c2ef-113">Indicates that neither a matching case or a default case in a Flowchart switch could be found.</span></span> <span data-ttu-id="0c2ef-114">Flowchart 执行将结束。</span><span class="sxs-lookup"><span data-stu-id="0c2ef-114">Flowchart execution will end.</span></span>  
  
## <a name="message"></a><span data-ttu-id="0c2ef-115">消息</span><span class="sxs-lookup"><span data-stu-id="0c2ef-115">Message</span></span>  
 <span data-ttu-id="0c2ef-116">Flowchart“%1”/FlowSwitch - 找不到 Case 活动，也找不到与 Expression 结果匹配的 Default Case。</span><span class="sxs-lookup"><span data-stu-id="0c2ef-116">Flowchart '%1'/FlowSwitch - could find neither a Case activity nor a Default Case matching the Expression result.</span></span> <span data-ttu-id="0c2ef-117">Flowchart 执行将结束。</span><span class="sxs-lookup"><span data-stu-id="0c2ef-117">Flowchart execution will end.</span></span>  
  
## <a name="details"></a><span data-ttu-id="0c2ef-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="0c2ef-118">Details</span></span>  
  
|<span data-ttu-id="0c2ef-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="0c2ef-119">Data Item Name</span></span>|<span data-ttu-id="0c2ef-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="0c2ef-120">Data Item Type</span></span>|<span data-ttu-id="0c2ef-121">描述</span><span class="sxs-lookup"><span data-stu-id="0c2ef-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="0c2ef-122">FlowChart</span><span class="sxs-lookup"><span data-stu-id="0c2ef-122">FlowChart</span></span>|<span data-ttu-id="0c2ef-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="0c2ef-123">xs:string</span></span>|<span data-ttu-id="0c2ef-124">FlowChart 的显示名称。</span><span class="sxs-lookup"><span data-stu-id="0c2ef-124">The display name of the FlowChart.</span></span>|  
|<span data-ttu-id="0c2ef-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="0c2ef-125">AppDomain</span></span>|<span data-ttu-id="0c2ef-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="0c2ef-126">xs:string</span></span>|<span data-ttu-id="0c2ef-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="0c2ef-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
