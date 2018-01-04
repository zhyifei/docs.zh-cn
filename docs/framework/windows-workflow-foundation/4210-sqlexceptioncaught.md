---
title: 4210 - SqlExceptionCaught
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0ce8af3-eb4c-48c8-b3d9-dd2f94b5574b
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fbcb566574e38e3c4688c16bd29a33ff7048bfa4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="4210---sqlexceptioncaught"></a><span data-ttu-id="d8807-102">4210 - SqlExceptionCaught</span><span class="sxs-lookup"><span data-stu-id="d8807-102">4210 - SqlExceptionCaught</span></span>
## <a name="properties"></a><span data-ttu-id="d8807-103">属性</span><span class="sxs-lookup"><span data-stu-id="d8807-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d8807-104">ID</span><span class="sxs-lookup"><span data-stu-id="d8807-104">ID</span></span>|<span data-ttu-id="d8807-105">4210</span><span class="sxs-lookup"><span data-stu-id="d8807-105">4210</span></span>|  
|<span data-ttu-id="d8807-106">关键字</span><span class="sxs-lookup"><span data-stu-id="d8807-106">Keywords</span></span>|<span data-ttu-id="d8807-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="d8807-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="d8807-108">级别</span><span class="sxs-lookup"><span data-stu-id="d8807-108">Level</span></span>|<span data-ttu-id="d8807-109">警告</span><span class="sxs-lookup"><span data-stu-id="d8807-109">Warning</span></span>|  
|<span data-ttu-id="d8807-110">通道</span><span class="sxs-lookup"><span data-stu-id="d8807-110">Channel</span></span>|<span data-ttu-id="d8807-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="d8807-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d8807-112">描述</span><span class="sxs-lookup"><span data-stu-id="d8807-112">Description</span></span>  
 <span data-ttu-id="d8807-113">指示捕获了 SQL 异常。</span><span class="sxs-lookup"><span data-stu-id="d8807-113">Indicates a SQL exception was caught.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d8807-114">消息</span><span class="sxs-lookup"><span data-stu-id="d8807-114">Message</span></span>  
 <span data-ttu-id="d8807-115">已捕获 SQL 异常编号为 %1 的消息 %2。</span><span class="sxs-lookup"><span data-stu-id="d8807-115">Caught SQL Exception number %1 message %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d8807-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="d8807-116">Details</span></span>  
  
|<span data-ttu-id="d8807-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="d8807-117">Data Item Name</span></span>|<span data-ttu-id="d8807-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="d8807-118">Data Item Type</span></span>|<span data-ttu-id="d8807-119">描述</span><span class="sxs-lookup"><span data-stu-id="d8807-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d8807-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="d8807-120">ErrorNumber</span></span>|<span data-ttu-id="d8807-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8807-121">xs:string</span></span>|<span data-ttu-id="d8807-122">SQL 错误号。</span><span class="sxs-lookup"><span data-stu-id="d8807-122">The SQL error number.</span></span>|  
|<span data-ttu-id="d8807-123">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="d8807-123">ExceptionMessage</span></span>|<span data-ttu-id="d8807-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8807-124">xs:string</span></span>|<span data-ttu-id="d8807-125">来自 SQL 异常的消息。</span><span class="sxs-lookup"><span data-stu-id="d8807-125">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="d8807-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d8807-126">AppDomain</span></span>|<span data-ttu-id="d8807-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d8807-127">xs:string</span></span>|<span data-ttu-id="d8807-128">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="d8807-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
