---
title: 4209 - TimeoutOpeningSqlConnection
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0e56518-9758-41dc-a760-50d1a10fba6e
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 86d971a2e5f1257281c453e7eb0c2dc1755098d8
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="11549-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="11549-102">4209 - TimeoutOpeningSqlConnection</span></span>
## <a name="properties"></a><span data-ttu-id="11549-103">属性</span><span class="sxs-lookup"><span data-stu-id="11549-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="11549-104">ID</span><span class="sxs-lookup"><span data-stu-id="11549-104">ID</span></span>|<span data-ttu-id="11549-105">4209</span><span class="sxs-lookup"><span data-stu-id="11549-105">4209</span></span>|  
|<span data-ttu-id="11549-106">关键字</span><span class="sxs-lookup"><span data-stu-id="11549-106">Keywords</span></span>|<span data-ttu-id="11549-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="11549-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="11549-108">级别</span><span class="sxs-lookup"><span data-stu-id="11549-108">Level</span></span>|<span data-ttu-id="11549-109">错误</span><span class="sxs-lookup"><span data-stu-id="11549-109">Error</span></span>|  
|<span data-ttu-id="11549-110">通道</span><span class="sxs-lookup"><span data-stu-id="11549-110">Channel</span></span>|<span data-ttu-id="11549-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="11549-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="11549-112">描述</span><span class="sxs-lookup"><span data-stu-id="11549-112">Description</span></span>  
 <span data-ttu-id="11549-113">指示在尝试打开 SQL 连接时遇到了超时。</span><span class="sxs-lookup"><span data-stu-id="11549-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="11549-114">消息</span><span class="sxs-lookup"><span data-stu-id="11549-114">Message</span></span>  
 <span data-ttu-id="11549-115">尝试打开 SQL 连接时超时。</span><span class="sxs-lookup"><span data-stu-id="11549-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="11549-116">操作在分配的超时 %1 内没有完成。</span><span class="sxs-lookup"><span data-stu-id="11549-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="11549-117">分配给此操作的时间可能是更长超时的一部分。</span><span class="sxs-lookup"><span data-stu-id="11549-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="11549-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="11549-118">Details</span></span>  
  
|<span data-ttu-id="11549-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="11549-119">Data Item Name</span></span>|<span data-ttu-id="11549-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="11549-120">Data Item Type</span></span>|<span data-ttu-id="11549-121">描述</span><span class="sxs-lookup"><span data-stu-id="11549-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="11549-122">超时</span><span class="sxs-lookup"><span data-stu-id="11549-122">Timeout</span></span>|<span data-ttu-id="11549-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="11549-123">xs:string</span></span>|<span data-ttu-id="11549-124">用于打开 SQL 连接的超时值。</span><span class="sxs-lookup"><span data-stu-id="11549-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="11549-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="11549-125">AppDomain</span></span>|<span data-ttu-id="11549-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="11549-126">xs:string</span></span>|<span data-ttu-id="11549-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="11549-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
