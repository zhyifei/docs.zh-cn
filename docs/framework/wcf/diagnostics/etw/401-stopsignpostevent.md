---
title: 401- StopSignPostEvent
ms.date: 03/30/2017
ms.assetid: e033d03a-510d-4300-aa65-ef02cb4807f2
ms.openlocfilehash: 1776252c362feb3c3ebc04651603944040ceee7b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61999747"
---
# <a name="401--stopsignpostevent"></a><span data-ttu-id="69481-102">401- StopSignPostEvent</span><span class="sxs-lookup"><span data-stu-id="69481-102">401- StopSignPostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="69481-103">属性</span><span class="sxs-lookup"><span data-stu-id="69481-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="69481-104">Id</span><span class="sxs-lookup"><span data-stu-id="69481-104">ID</span></span>|<span data-ttu-id="69481-105">401</span><span class="sxs-lookup"><span data-stu-id="69481-105">401</span></span>|  
|<span data-ttu-id="69481-106">关键字</span><span class="sxs-lookup"><span data-stu-id="69481-106">Keywords</span></span>|<span data-ttu-id="69481-107">疑难解答</span><span class="sxs-lookup"><span data-stu-id="69481-107">Troubleshooting</span></span>|  
|<span data-ttu-id="69481-108">级别</span><span class="sxs-lookup"><span data-stu-id="69481-108">Level</span></span>|<span data-ttu-id="69481-109">信息</span><span class="sxs-lookup"><span data-stu-id="69481-109">Information</span></span>|  
|<span data-ttu-id="69481-110">通道</span><span class="sxs-lookup"><span data-stu-id="69481-110">Channel</span></span>|<span data-ttu-id="69481-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="69481-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="69481-112">描述</span><span class="sxs-lookup"><span data-stu-id="69481-112">Description</span></span>  
 <span data-ttu-id="69481-113">此事件标记端对端活动的结束，</span><span class="sxs-lookup"><span data-stu-id="69481-113">This event marks the end of an end-to-end activity.</span></span> <span data-ttu-id="69481-114">它包含活动的名称。</span><span class="sxs-lookup"><span data-stu-id="69481-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="69481-115">消息</span><span class="sxs-lookup"><span data-stu-id="69481-115">Message</span></span>  
 <span data-ttu-id="69481-116">活动边界。</span><span class="sxs-lookup"><span data-stu-id="69481-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="69481-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="69481-117">Details</span></span>  
  
|<span data-ttu-id="69481-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="69481-118">Data Item Name</span></span>|<span data-ttu-id="69481-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="69481-119">Data Item Type</span></span>|<span data-ttu-id="69481-120">描述</span><span class="sxs-lookup"><span data-stu-id="69481-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="69481-121">扩展数据</span><span class="sxs-lookup"><span data-stu-id="69481-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="69481-122">活动的名称。</span><span class="sxs-lookup"><span data-stu-id="69481-122">The name of the activity.</span></span>|  
|<span data-ttu-id="69481-123">应用程序域</span><span class="sxs-lookup"><span data-stu-id="69481-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="69481-124">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="69481-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
