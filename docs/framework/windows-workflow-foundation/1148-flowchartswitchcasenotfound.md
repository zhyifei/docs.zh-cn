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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f95ea8aa8c3d6b012fb50a45b5a37c118928e048
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="1148---flowchartswitchcasenotfound"></a><span data-ttu-id="d23ee-102">1148 - FlowchartSwitchCaseNotFound</span><span class="sxs-lookup"><span data-stu-id="d23ee-102">1148 - FlowchartSwitchCaseNotFound</span></span>
## <a name="properties"></a><span data-ttu-id="d23ee-103">属性</span><span class="sxs-lookup"><span data-stu-id="d23ee-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d23ee-104">ID</span><span class="sxs-lookup"><span data-stu-id="d23ee-104">ID</span></span>|<span data-ttu-id="d23ee-105">1148</span><span class="sxs-lookup"><span data-stu-id="d23ee-105">1148</span></span>|  
|<span data-ttu-id="d23ee-106">关键字</span><span class="sxs-lookup"><span data-stu-id="d23ee-106">Keywords</span></span>|<span data-ttu-id="d23ee-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="d23ee-107">WFActivities</span></span>|  
|<span data-ttu-id="d23ee-108">级别</span><span class="sxs-lookup"><span data-stu-id="d23ee-108">Level</span></span>|<span data-ttu-id="d23ee-109">信息</span><span class="sxs-lookup"><span data-stu-id="d23ee-109">Information</span></span>|  
|<span data-ttu-id="d23ee-110">通道</span><span class="sxs-lookup"><span data-stu-id="d23ee-110">Channel</span></span>|<span data-ttu-id="d23ee-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="d23ee-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d23ee-112">描述</span><span class="sxs-lookup"><span data-stu-id="d23ee-112">Description</span></span>  
 <span data-ttu-id="d23ee-113">指示在 Flowchart 开关中找不到匹配大小写，也找不到默认大小写。</span><span class="sxs-lookup"><span data-stu-id="d23ee-113">Indicates that neither a matching case or a default case in a Flowchart switch could be found.</span></span> <span data-ttu-id="d23ee-114">Flowchart 执行将结束。</span><span class="sxs-lookup"><span data-stu-id="d23ee-114">Flowchart execution will end.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d23ee-115">消息</span><span class="sxs-lookup"><span data-stu-id="d23ee-115">Message</span></span>  
 <span data-ttu-id="d23ee-116">Flowchart“%1”/FlowSwitch - 找不到 Case 活动，也找不到与 Expression 结果匹配的 Default Case。</span><span class="sxs-lookup"><span data-stu-id="d23ee-116">Flowchart '%1'/FlowSwitch - could find neither a Case activity nor a Default Case matching the Expression result.</span></span> <span data-ttu-id="d23ee-117">Flowchart 执行将结束。</span><span class="sxs-lookup"><span data-stu-id="d23ee-117">Flowchart execution will end.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d23ee-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="d23ee-118">Details</span></span>  
  
|<span data-ttu-id="d23ee-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="d23ee-119">Data Item Name</span></span>|<span data-ttu-id="d23ee-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="d23ee-120">Data Item Type</span></span>|<span data-ttu-id="d23ee-121">描述</span><span class="sxs-lookup"><span data-stu-id="d23ee-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d23ee-122">FlowChart</span><span class="sxs-lookup"><span data-stu-id="d23ee-122">FlowChart</span></span>|<span data-ttu-id="d23ee-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="d23ee-123">xs:string</span></span>|<span data-ttu-id="d23ee-124">FlowChart 的显示名称。</span><span class="sxs-lookup"><span data-stu-id="d23ee-124">The display name of the FlowChart.</span></span>|  
|<span data-ttu-id="d23ee-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d23ee-125">AppDomain</span></span>|<span data-ttu-id="d23ee-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="d23ee-126">xs:string</span></span>|<span data-ttu-id="d23ee-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="d23ee-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
