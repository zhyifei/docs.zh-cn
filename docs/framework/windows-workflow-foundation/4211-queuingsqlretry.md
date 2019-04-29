---
title: 4211 - QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: ede74eb642c5c2c79b90cf1458db424d9f83b087
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774239"
---
# <a name="4211---queuingsqlretry"></a><span data-ttu-id="30e4c-102">4211 - QueuingSqlRetry</span><span class="sxs-lookup"><span data-stu-id="30e4c-102">4211 - QueuingSqlRetry</span></span>
## <a name="properties"></a><span data-ttu-id="30e4c-103">属性</span><span class="sxs-lookup"><span data-stu-id="30e4c-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="30e4c-104">Id</span><span class="sxs-lookup"><span data-stu-id="30e4c-104">ID</span></span>|<span data-ttu-id="30e4c-105">4211</span><span class="sxs-lookup"><span data-stu-id="30e4c-105">4211</span></span>|  
|<span data-ttu-id="30e4c-106">关键字</span><span class="sxs-lookup"><span data-stu-id="30e4c-106">Keywords</span></span>|<span data-ttu-id="30e4c-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="30e4c-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="30e4c-108">级别</span><span class="sxs-lookup"><span data-stu-id="30e4c-108">Level</span></span>|<span data-ttu-id="30e4c-109">警告</span><span class="sxs-lookup"><span data-stu-id="30e4c-109">Warning</span></span>|  
|<span data-ttu-id="30e4c-110">通道</span><span class="sxs-lookup"><span data-stu-id="30e4c-110">Channel</span></span>|<span data-ttu-id="30e4c-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="30e4c-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="30e4c-112">描述</span><span class="sxs-lookup"><span data-stu-id="30e4c-112">Description</span></span>  
 <span data-ttu-id="30e4c-113">指示将 SQL 重试排队。</span><span class="sxs-lookup"><span data-stu-id="30e4c-113">Indicates queuing SQL retry.</span></span>  
  
## <a name="message"></a><span data-ttu-id="30e4c-114">消息</span><span class="sxs-lookup"><span data-stu-id="30e4c-114">Message</span></span>  
 <span data-ttu-id="30e4c-115">正在将 SQL 重试排队，延迟 %1 毫秒。</span><span class="sxs-lookup"><span data-stu-id="30e4c-115">Queuing SQL retry with delay %1 milliseconds.</span></span>  
  
## <a name="details"></a><span data-ttu-id="30e4c-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="30e4c-116">Details</span></span>  
  
|<span data-ttu-id="30e4c-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="30e4c-117">Data Item Name</span></span>|<span data-ttu-id="30e4c-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="30e4c-118">Data Item Type</span></span>|<span data-ttu-id="30e4c-119">描述</span><span class="sxs-lookup"><span data-stu-id="30e4c-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="30e4c-120">延迟</span><span class="sxs-lookup"><span data-stu-id="30e4c-120">Delay</span></span>|<span data-ttu-id="30e4c-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="30e4c-121">xs:string</span></span>|<span data-ttu-id="30e4c-122">两次重试之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="30e4c-122">The delay between retries.</span></span>|  
|<span data-ttu-id="30e4c-123">应用程序域</span><span class="sxs-lookup"><span data-stu-id="30e4c-123">AppDomain</span></span>|<span data-ttu-id="30e4c-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="30e4c-124">xs:string</span></span>|<span data-ttu-id="30e4c-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="30e4c-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
