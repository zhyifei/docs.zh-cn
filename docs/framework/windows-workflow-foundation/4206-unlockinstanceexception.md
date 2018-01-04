---
title: 4206 - UnlockInstanceException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a46dc5f-d517-4135-8905-25a42f01206b
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ffe33e52a67578e42ad9d28adfa2067e8830ab73
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="4206---unlockinstanceexception"></a><span data-ttu-id="c1b9d-102">4206 - UnlockInstanceException</span><span class="sxs-lookup"><span data-stu-id="c1b9d-102">4206 - UnlockInstanceException</span></span>
## <a name="properties"></a><span data-ttu-id="c1b9d-103">属性</span><span class="sxs-lookup"><span data-stu-id="c1b9d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c1b9d-104">ID</span><span class="sxs-lookup"><span data-stu-id="c1b9d-104">ID</span></span>|<span data-ttu-id="c1b9d-105">4206</span><span class="sxs-lookup"><span data-stu-id="c1b9d-105">4206</span></span>|  
|<span data-ttu-id="c1b9d-106">关键字</span><span class="sxs-lookup"><span data-stu-id="c1b9d-106">Keywords</span></span>|<span data-ttu-id="c1b9d-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="c1b9d-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="c1b9d-108">级别</span><span class="sxs-lookup"><span data-stu-id="c1b9d-108">Level</span></span>|<span data-ttu-id="c1b9d-109">错误</span><span class="sxs-lookup"><span data-stu-id="c1b9d-109">Error</span></span>|  
|<span data-ttu-id="c1b9d-110">通道</span><span class="sxs-lookup"><span data-stu-id="c1b9d-110">Channel</span></span>|<span data-ttu-id="c1b9d-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="c1b9d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="c1b9d-112">描述</span><span class="sxs-lookup"><span data-stu-id="c1b9d-112">Description</span></span>  
 <span data-ttu-id="c1b9d-113">指示在尝试解锁某一实例时遇到了异常。</span><span class="sxs-lookup"><span data-stu-id="c1b9d-113">Indicates an exception was encountered while trying to unlock an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="c1b9d-114">消息</span><span class="sxs-lookup"><span data-stu-id="c1b9d-114">Message</span></span>  
 <span data-ttu-id="c1b9d-115">尝试解除实例锁定时遇到异常 %1。</span><span class="sxs-lookup"><span data-stu-id="c1b9d-115">Encountered exception %1 while attempting to unlock instance.</span></span>  
  
## <a name="details"></a><span data-ttu-id="c1b9d-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="c1b9d-116">Details</span></span>  
  
|<span data-ttu-id="c1b9d-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="c1b9d-117">Data Item Name</span></span>|<span data-ttu-id="c1b9d-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="c1b9d-118">Data Item Type</span></span>|<span data-ttu-id="c1b9d-119">描述</span><span class="sxs-lookup"><span data-stu-id="c1b9d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="c1b9d-120">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="c1b9d-120">ExceptionMessage</span></span>|<span data-ttu-id="c1b9d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1b9d-121">xs:string</span></span>|<span data-ttu-id="c1b9d-122">来自 SQL 异常的消息。</span><span class="sxs-lookup"><span data-stu-id="c1b9d-122">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="c1b9d-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="c1b9d-123">AppDomain</span></span>|<span data-ttu-id="c1b9d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="c1b9d-124">xs:string</span></span>|<span data-ttu-id="c1b9d-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="c1b9d-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
