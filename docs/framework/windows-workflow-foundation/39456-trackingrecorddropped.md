---
title: 39456 - TrackingRecordDropped
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: da13d5bc-1736-47a4-b3fd-064ca8040326
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 592d7c0a3725dcb50f7911a198c9dc9b7199a0a8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="39456---trackingrecorddropped"></a><span data-ttu-id="d0d64-102">39456 - TrackingRecordDropped</span><span class="sxs-lookup"><span data-stu-id="d0d64-102">39456 - TrackingRecordDropped</span></span>
## <a name="properties"></a><span data-ttu-id="d0d64-103">属性</span><span class="sxs-lookup"><span data-stu-id="d0d64-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d0d64-104">ID</span><span class="sxs-lookup"><span data-stu-id="d0d64-104">ID</span></span>|<span data-ttu-id="d0d64-105">39456</span><span class="sxs-lookup"><span data-stu-id="d0d64-105">39456</span></span>|  
|<span data-ttu-id="d0d64-106">关键字</span><span class="sxs-lookup"><span data-stu-id="d0d64-106">Keywords</span></span>|<span data-ttu-id="d0d64-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="d0d64-107">WFTracking</span></span>|  
|<span data-ttu-id="d0d64-108">级别</span><span class="sxs-lookup"><span data-stu-id="d0d64-108">Level</span></span>|<span data-ttu-id="d0d64-109">警告</span><span class="sxs-lookup"><span data-stu-id="d0d64-109">Warning</span></span>|  
|<span data-ttu-id="d0d64-110">通道</span><span class="sxs-lookup"><span data-stu-id="d0d64-110">Channel</span></span>|<span data-ttu-id="d0d64-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="d0d64-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d0d64-112">描述</span><span class="sxs-lookup"><span data-stu-id="d0d64-112">Description</span></span>  
 <span data-ttu-id="d0d64-113">指示一个跟踪记录已被丢弃，因为其大小超过 ETW 提供程序会话允许的最大大小。</span><span class="sxs-lookup"><span data-stu-id="d0d64-113">Indicates a tracking record has been dropped because its size exceeds maximum allowed by the ETW session provider.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d0d64-114">消息</span><span class="sxs-lookup"><span data-stu-id="d0d64-114">Message</span></span>  
 <span data-ttu-id="d0d64-115">跟踪记录 %1 的大小超出了 ETW 会话对提供程序 %2 允许的最大值</span><span class="sxs-lookup"><span data-stu-id="d0d64-115">Size of tracking record %1 exceeds maximum allowed by the ETW session for provider %2</span></span>  
  
## <a name="details"></a><span data-ttu-id="d0d64-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="d0d64-116">Details</span></span>  
  
|<span data-ttu-id="d0d64-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="d0d64-117">Data Item Name</span></span>|<span data-ttu-id="d0d64-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="d0d64-118">Data Item Type</span></span>|<span data-ttu-id="d0d64-119">描述</span><span class="sxs-lookup"><span data-stu-id="d0d64-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d0d64-120">例外</span><span class="sxs-lookup"><span data-stu-id="d0d64-120">Exception</span></span>|<span data-ttu-id="d0d64-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d0d64-121">xs:string</span></span>|<span data-ttu-id="d0d64-122">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="d0d64-122">The exception details for the exception</span></span>|  
|<span data-ttu-id="d0d64-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d0d64-123">AppDomain</span></span>|<span data-ttu-id="d0d64-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d0d64-124">xs:string</span></span>|<span data-ttu-id="d0d64-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="d0d64-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
