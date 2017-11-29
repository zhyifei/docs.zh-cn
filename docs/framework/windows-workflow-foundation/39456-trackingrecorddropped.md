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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 3e663cced42252112e1948f4907bc8c81ef941f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="39456---trackingrecorddropped"></a><span data-ttu-id="d1d9e-102">39456 - TrackingRecordDropped</span><span class="sxs-lookup"><span data-stu-id="d1d9e-102">39456 - TrackingRecordDropped</span></span>
## <a name="properties"></a><span data-ttu-id="d1d9e-103">属性</span><span class="sxs-lookup"><span data-stu-id="d1d9e-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d1d9e-104">ID</span><span class="sxs-lookup"><span data-stu-id="d1d9e-104">ID</span></span>|<span data-ttu-id="d1d9e-105">39456</span><span class="sxs-lookup"><span data-stu-id="d1d9e-105">39456</span></span>|  
|<span data-ttu-id="d1d9e-106">关键字</span><span class="sxs-lookup"><span data-stu-id="d1d9e-106">Keywords</span></span>|<span data-ttu-id="d1d9e-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="d1d9e-107">WFTracking</span></span>|  
|<span data-ttu-id="d1d9e-108">级别</span><span class="sxs-lookup"><span data-stu-id="d1d9e-108">Level</span></span>|<span data-ttu-id="d1d9e-109">警告</span><span class="sxs-lookup"><span data-stu-id="d1d9e-109">Warning</span></span>|  
|<span data-ttu-id="d1d9e-110">通道</span><span class="sxs-lookup"><span data-stu-id="d1d9e-110">Channel</span></span>|<span data-ttu-id="d1d9e-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="d1d9e-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d1d9e-112">描述</span><span class="sxs-lookup"><span data-stu-id="d1d9e-112">Description</span></span>  
 <span data-ttu-id="d1d9e-113">指示一个跟踪记录已被丢弃，因为其大小超过 ETW 提供程序会话允许的最大大小。</span><span class="sxs-lookup"><span data-stu-id="d1d9e-113">Indicates a tracking record has been dropped because its size exceeds maximum allowed by the ETW session provider.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d1d9e-114">消息</span><span class="sxs-lookup"><span data-stu-id="d1d9e-114">Message</span></span>  
 <span data-ttu-id="d1d9e-115">跟踪记录 %1 的大小超出了 ETW 会话对提供程序 %2 允许的最大值</span><span class="sxs-lookup"><span data-stu-id="d1d9e-115">Size of tracking record %1 exceeds maximum allowed by the ETW session for provider %2</span></span>  
  
## <a name="details"></a><span data-ttu-id="d1d9e-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="d1d9e-116">Details</span></span>  
  
|<span data-ttu-id="d1d9e-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="d1d9e-117">Data Item Name</span></span>|<span data-ttu-id="d1d9e-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="d1d9e-118">Data Item Type</span></span>|<span data-ttu-id="d1d9e-119">描述</span><span class="sxs-lookup"><span data-stu-id="d1d9e-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d1d9e-120">例外</span><span class="sxs-lookup"><span data-stu-id="d1d9e-120">Exception</span></span>|<span data-ttu-id="d1d9e-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d1d9e-121">xs:string</span></span>|<span data-ttu-id="d1d9e-122">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="d1d9e-122">The exception details for the exception</span></span>|  
|<span data-ttu-id="d1d9e-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d1d9e-123">AppDomain</span></span>|<span data-ttu-id="d1d9e-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d1d9e-124">xs:string</span></span>|<span data-ttu-id="d1d9e-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="d1d9e-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
