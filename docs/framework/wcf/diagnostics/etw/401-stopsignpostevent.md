---
title: 401- StopSignPostEvent
ms.date: 03/30/2017
ms.assetid: e033d03a-510d-4300-aa65-ef02cb4807f2
ms.openlocfilehash: 1776252c362feb3c3ebc04651603944040ceee7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33474163"
---
# <a name="401--stopsignpostevent"></a><span data-ttu-id="07334-102">401- StopSignPostEvent</span><span class="sxs-lookup"><span data-stu-id="07334-102">401- StopSignPostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="07334-103">属性</span><span class="sxs-lookup"><span data-stu-id="07334-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="07334-104">ID</span><span class="sxs-lookup"><span data-stu-id="07334-104">ID</span></span>|<span data-ttu-id="07334-105">401</span><span class="sxs-lookup"><span data-stu-id="07334-105">401</span></span>|  
|<span data-ttu-id="07334-106">关键字</span><span class="sxs-lookup"><span data-stu-id="07334-106">Keywords</span></span>|<span data-ttu-id="07334-107">疑难解答</span><span class="sxs-lookup"><span data-stu-id="07334-107">Troubleshooting</span></span>|  
|<span data-ttu-id="07334-108">级别</span><span class="sxs-lookup"><span data-stu-id="07334-108">Level</span></span>|<span data-ttu-id="07334-109">信息</span><span class="sxs-lookup"><span data-stu-id="07334-109">Information</span></span>|  
|<span data-ttu-id="07334-110">通道</span><span class="sxs-lookup"><span data-stu-id="07334-110">Channel</span></span>|<span data-ttu-id="07334-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="07334-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="07334-112">描述</span><span class="sxs-lookup"><span data-stu-id="07334-112">Description</span></span>  
 <span data-ttu-id="07334-113">此事件标记端对端活动的结束，</span><span class="sxs-lookup"><span data-stu-id="07334-113">This event marks the end of an end-to-end activity.</span></span> <span data-ttu-id="07334-114">它包含活动的名称。</span><span class="sxs-lookup"><span data-stu-id="07334-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="07334-115">消息</span><span class="sxs-lookup"><span data-stu-id="07334-115">Message</span></span>  
 <span data-ttu-id="07334-116">活动边界。</span><span class="sxs-lookup"><span data-stu-id="07334-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="07334-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="07334-117">Details</span></span>  
  
|<span data-ttu-id="07334-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="07334-118">Data Item Name</span></span>|<span data-ttu-id="07334-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="07334-119">Data Item Type</span></span>|<span data-ttu-id="07334-120">描述</span><span class="sxs-lookup"><span data-stu-id="07334-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="07334-121">扩展数据</span><span class="sxs-lookup"><span data-stu-id="07334-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="07334-122">活动的名称。</span><span class="sxs-lookup"><span data-stu-id="07334-122">The name of the activity.</span></span>|  
|<span data-ttu-id="07334-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="07334-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="07334-124">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="07334-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
