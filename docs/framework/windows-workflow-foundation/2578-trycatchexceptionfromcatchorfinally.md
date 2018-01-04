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
ms.workload: dotnet
ms.openlocfilehash: 340f8fa140f44e4a85f9b19259dc0a9f49b9b08e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="2578---trycatchexceptionfromcatchorfinally"></a><span data-ttu-id="f4395-102">2578 - TryCatchExceptionFromCatchOrFinally</span><span class="sxs-lookup"><span data-stu-id="f4395-102">2578 - TryCatchExceptionFromCatchOrFinally</span></span>
## <a name="properties"></a><span data-ttu-id="f4395-103">属性</span><span class="sxs-lookup"><span data-stu-id="f4395-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f4395-104">ID</span><span class="sxs-lookup"><span data-stu-id="f4395-104">ID</span></span>|<span data-ttu-id="f4395-105">2578</span><span class="sxs-lookup"><span data-stu-id="f4395-105">2578</span></span>|  
|<span data-ttu-id="f4395-106">关键字</span><span class="sxs-lookup"><span data-stu-id="f4395-106">Keywords</span></span>|<span data-ttu-id="f4395-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="f4395-107">WFActivities</span></span>|  
|<span data-ttu-id="f4395-108">级别</span><span class="sxs-lookup"><span data-stu-id="f4395-108">Level</span></span>|<span data-ttu-id="f4395-109">警告</span><span class="sxs-lookup"><span data-stu-id="f4395-109">Warning</span></span>|  
|<span data-ttu-id="f4395-110">通道</span><span class="sxs-lookup"><span data-stu-id="f4395-110">Channel</span></span>|<span data-ttu-id="f4395-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="f4395-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="f4395-112">描述</span><span class="sxs-lookup"><span data-stu-id="f4395-112">Description</span></span>  
 <span data-ttu-id="f4395-113">指示 Catch 或 Finally 活动引发了异常。</span><span class="sxs-lookup"><span data-stu-id="f4395-113">Indicates a Catch or Finally activity has thrown an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="f4395-114">消息</span><span class="sxs-lookup"><span data-stu-id="f4395-114">Message</span></span>  
 <span data-ttu-id="f4395-115">与 TryCatch 活动“%1”关联的 Catch 或 Finally 活动引发了异常。</span><span class="sxs-lookup"><span data-stu-id="f4395-115">A Catch or Finally activity that is associated with the TryCatch activity '%1' has thrown an exception.</span></span>  
  
## <a name="details"></a><span data-ttu-id="f4395-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="f4395-116">Details</span></span>  
  
|<span data-ttu-id="f4395-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="f4395-117">Data Item Name</span></span>|<span data-ttu-id="f4395-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="f4395-118">Data Item Type</span></span>|<span data-ttu-id="f4395-119">描述</span><span class="sxs-lookup"><span data-stu-id="f4395-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="f4395-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="f4395-120">DisplayName</span></span>|<span data-ttu-id="f4395-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4395-121">xs:string</span></span>|<span data-ttu-id="f4395-122">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="f4395-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="f4395-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="f4395-123">AppDomain</span></span>|<span data-ttu-id="f4395-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="f4395-124">xs:string</span></span>|<span data-ttu-id="f4395-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="f4395-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
