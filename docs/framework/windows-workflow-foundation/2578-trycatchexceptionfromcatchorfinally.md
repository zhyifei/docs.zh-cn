---
title: 2578 - TryCatchExceptionFromCatchOrFinally
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4803fee6-b8d8-4937-9907-d5c5fd5299db
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ab39fbc05c4661dd5af37297540eafd67990eb58
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="2578---trycatchexceptionfromcatchorfinally"></a><span data-ttu-id="3e1cc-102">2578 - TryCatchExceptionFromCatchOrFinally</span><span class="sxs-lookup"><span data-stu-id="3e1cc-102">2578 - TryCatchExceptionFromCatchOrFinally</span></span>
## <a name="properties"></a><span data-ttu-id="3e1cc-103">属性</span><span class="sxs-lookup"><span data-stu-id="3e1cc-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3e1cc-104">ID</span><span class="sxs-lookup"><span data-stu-id="3e1cc-104">ID</span></span>|<span data-ttu-id="3e1cc-105">2578</span><span class="sxs-lookup"><span data-stu-id="3e1cc-105">2578</span></span>|  
|<span data-ttu-id="3e1cc-106">关键字</span><span class="sxs-lookup"><span data-stu-id="3e1cc-106">Keywords</span></span>|<span data-ttu-id="3e1cc-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="3e1cc-107">WFActivities</span></span>|  
|<span data-ttu-id="3e1cc-108">级别</span><span class="sxs-lookup"><span data-stu-id="3e1cc-108">Level</span></span>|<span data-ttu-id="3e1cc-109">警告</span><span class="sxs-lookup"><span data-stu-id="3e1cc-109">Warning</span></span>|  
|<span data-ttu-id="3e1cc-110">通道</span><span class="sxs-lookup"><span data-stu-id="3e1cc-110">Channel</span></span>|<span data-ttu-id="3e1cc-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="3e1cc-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="3e1cc-112">描述</span><span class="sxs-lookup"><span data-stu-id="3e1cc-112">Description</span></span>  
 <span data-ttu-id="3e1cc-113">指示 Catch 或 Finally 活动引发了异常。</span><span class="sxs-lookup"><span data-stu-id="3e1cc-113">Indicates a Catch or Finally activity has thrown an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="3e1cc-114">消息</span><span class="sxs-lookup"><span data-stu-id="3e1cc-114">Message</span></span>  
 <span data-ttu-id="3e1cc-115">与 TryCatch 活动“%1”关联的 Catch 或 Finally 活动引发了异常。</span><span class="sxs-lookup"><span data-stu-id="3e1cc-115">A Catch or Finally activity that is associated with the TryCatch activity '%1' has thrown an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="3e1cc-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="3e1cc-116">Details</span></span>  
  
|<span data-ttu-id="3e1cc-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="3e1cc-117">Data Item Name</span></span>|<span data-ttu-id="3e1cc-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="3e1cc-118">Data Item Type</span></span>|<span data-ttu-id="3e1cc-119">描述</span><span class="sxs-lookup"><span data-stu-id="3e1cc-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="3e1cc-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="3e1cc-120">DisplayName</span></span>|<span data-ttu-id="3e1cc-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e1cc-121">xs:string</span></span>|<span data-ttu-id="3e1cc-122">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="3e1cc-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="3e1cc-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="3e1cc-123">AppDomain</span></span>|<span data-ttu-id="3e1cc-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="3e1cc-124">xs:string</span></span>|<span data-ttu-id="3e1cc-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="3e1cc-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
