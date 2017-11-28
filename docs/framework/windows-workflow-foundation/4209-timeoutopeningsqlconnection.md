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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f87e99585ccbdf3b89653f026860e7b66dc6c9b6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="4209---timeoutopeningsqlconnection"></a><span data-ttu-id="4a0d1-102">4209 - TimeoutOpeningSqlConnection</span><span class="sxs-lookup"><span data-stu-id="4a0d1-102">4209 - TimeoutOpeningSqlConnection</span></span>
## <a name="properties"></a><span data-ttu-id="4a0d1-103">属性</span><span class="sxs-lookup"><span data-stu-id="4a0d1-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4a0d1-104">ID</span><span class="sxs-lookup"><span data-stu-id="4a0d1-104">ID</span></span>|<span data-ttu-id="4a0d1-105">4209</span><span class="sxs-lookup"><span data-stu-id="4a0d1-105">4209</span></span>|  
|<span data-ttu-id="4a0d1-106">关键字</span><span class="sxs-lookup"><span data-stu-id="4a0d1-106">Keywords</span></span>|<span data-ttu-id="4a0d1-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="4a0d1-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="4a0d1-108">级别</span><span class="sxs-lookup"><span data-stu-id="4a0d1-108">Level</span></span>|<span data-ttu-id="4a0d1-109">错误</span><span class="sxs-lookup"><span data-stu-id="4a0d1-109">Error</span></span>|  
|<span data-ttu-id="4a0d1-110">通道</span><span class="sxs-lookup"><span data-stu-id="4a0d1-110">Channel</span></span>|<span data-ttu-id="4a0d1-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="4a0d1-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4a0d1-112">描述</span><span class="sxs-lookup"><span data-stu-id="4a0d1-112">Description</span></span>  
 <span data-ttu-id="4a0d1-113">指示在尝试打开 SQL 连接时遇到了超时。</span><span class="sxs-lookup"><span data-stu-id="4a0d1-113">Indicates a timeout was encountered when trying to open a SQL connection.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4a0d1-114">消息</span><span class="sxs-lookup"><span data-stu-id="4a0d1-114">Message</span></span>  
 <span data-ttu-id="4a0d1-115">尝试打开 SQL 连接时超时。</span><span class="sxs-lookup"><span data-stu-id="4a0d1-115">Timeout trying to open a SQL connection.</span></span> <span data-ttu-id="4a0d1-116">操作在分配的超时 %1 内没有完成。</span><span class="sxs-lookup"><span data-stu-id="4a0d1-116">The operation did not complete within the allotted timeout of %1.</span></span> <span data-ttu-id="4a0d1-117">分配给此操作的时间可能是更长超时的一部分。</span><span class="sxs-lookup"><span data-stu-id="4a0d1-117">The time allotted to this operation may have been a portion of a longer timeout.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4a0d1-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="4a0d1-118">Details</span></span>  
  
|<span data-ttu-id="4a0d1-119">数据项名称</span><span class="sxs-lookup"><span data-stu-id="4a0d1-119">Data Item Name</span></span>|<span data-ttu-id="4a0d1-120">数据项类型</span><span class="sxs-lookup"><span data-stu-id="4a0d1-120">Data Item Type</span></span>|<span data-ttu-id="4a0d1-121">描述</span><span class="sxs-lookup"><span data-stu-id="4a0d1-121">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4a0d1-122">超时</span><span class="sxs-lookup"><span data-stu-id="4a0d1-122">Timeout</span></span>|<span data-ttu-id="4a0d1-123">xs:string</span><span class="sxs-lookup"><span data-stu-id="4a0d1-123">xs:string</span></span>|<span data-ttu-id="4a0d1-124">用于打开 SQL 连接的超时值。</span><span class="sxs-lookup"><span data-stu-id="4a0d1-124">The timeout value for opening the SQL connection.</span></span>|  
|<span data-ttu-id="4a0d1-125">AppDomain</span><span class="sxs-lookup"><span data-stu-id="4a0d1-125">AppDomain</span></span>|<span data-ttu-id="4a0d1-126">xs:string</span><span class="sxs-lookup"><span data-stu-id="4a0d1-126">xs:string</span></span>|<span data-ttu-id="4a0d1-127">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="4a0d1-127">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
