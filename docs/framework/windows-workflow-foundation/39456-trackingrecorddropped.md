---
title: 39456 - TrackingRecordDropped
ms.date: 03/30/2017
ms.assetid: da13d5bc-1736-47a4-b3fd-064ca8040326
ms.openlocfilehash: f117c7759bab1759a7d614db275de88f8b37c331
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="39456---trackingrecorddropped"></a><span data-ttu-id="a758d-102">39456 - TrackingRecordDropped</span><span class="sxs-lookup"><span data-stu-id="a758d-102">39456 - TrackingRecordDropped</span></span>
## <a name="properties"></a><span data-ttu-id="a758d-103">属性</span><span class="sxs-lookup"><span data-stu-id="a758d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a758d-104">ID</span><span class="sxs-lookup"><span data-stu-id="a758d-104">ID</span></span>|<span data-ttu-id="a758d-105">39456</span><span class="sxs-lookup"><span data-stu-id="a758d-105">39456</span></span>|  
|<span data-ttu-id="a758d-106">关键字</span><span class="sxs-lookup"><span data-stu-id="a758d-106">Keywords</span></span>|<span data-ttu-id="a758d-107">WFTracking</span><span class="sxs-lookup"><span data-stu-id="a758d-107">WFTracking</span></span>|  
|<span data-ttu-id="a758d-108">级别</span><span class="sxs-lookup"><span data-stu-id="a758d-108">Level</span></span>|<span data-ttu-id="a758d-109">警告</span><span class="sxs-lookup"><span data-stu-id="a758d-109">Warning</span></span>|  
|<span data-ttu-id="a758d-110">通道</span><span class="sxs-lookup"><span data-stu-id="a758d-110">Channel</span></span>|<span data-ttu-id="a758d-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="a758d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="a758d-112">描述</span><span class="sxs-lookup"><span data-stu-id="a758d-112">Description</span></span>  
 <span data-ttu-id="a758d-113">指示一个跟踪记录已被丢弃，因为其大小超过 ETW 提供程序会话允许的最大大小。</span><span class="sxs-lookup"><span data-stu-id="a758d-113">Indicates a tracking record has been dropped because its size exceeds maximum allowed by the ETW session provider.</span></span>  
  
## <a name="message"></a><span data-ttu-id="a758d-114">消息</span><span class="sxs-lookup"><span data-stu-id="a758d-114">Message</span></span>  
 <span data-ttu-id="a758d-115">跟踪记录 %1 的大小超出了 ETW 会话对提供程序 %2 允许的最大值</span><span class="sxs-lookup"><span data-stu-id="a758d-115">Size of tracking record %1 exceeds maximum allowed by the ETW session for provider %2</span></span>  
  
## <a name="details"></a><span data-ttu-id="a758d-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="a758d-116">Details</span></span>  
  
|<span data-ttu-id="a758d-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="a758d-117">Data Item Name</span></span>|<span data-ttu-id="a758d-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="a758d-118">Data Item Type</span></span>|<span data-ttu-id="a758d-119">描述</span><span class="sxs-lookup"><span data-stu-id="a758d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="a758d-120">例外</span><span class="sxs-lookup"><span data-stu-id="a758d-120">Exception</span></span>|<span data-ttu-id="a758d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="a758d-121">xs:string</span></span>|<span data-ttu-id="a758d-122">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="a758d-122">The exception details for the exception</span></span>|  
|<span data-ttu-id="a758d-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="a758d-123">AppDomain</span></span>|<span data-ttu-id="a758d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="a758d-124">xs:string</span></span>|<span data-ttu-id="a758d-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="a758d-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
