---
title: 402 - StartSignpostEvent
ms.date: 03/30/2017
ms.assetid: 5e5be126-765d-4ac9-88e7-008e9ef4f0e5
ms.openlocfilehash: 6dfb3b187f58de2c9573c2d2f6d579e3557c3de8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33466595"
---
# <a name="402---startsignpostevent"></a><span data-ttu-id="e6fea-102">402 - StartSignpostEvent</span><span class="sxs-lookup"><span data-stu-id="e6fea-102">402 - StartSignpostEvent</span></span>
## <a name="properties"></a><span data-ttu-id="e6fea-103">属性</span><span class="sxs-lookup"><span data-stu-id="e6fea-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="e6fea-104">Id</span><span class="sxs-lookup"><span data-stu-id="e6fea-104">ID</span></span>|<span data-ttu-id="e6fea-105">402</span><span class="sxs-lookup"><span data-stu-id="e6fea-105">402</span></span>|  
|<span data-ttu-id="e6fea-106">关键字</span><span class="sxs-lookup"><span data-stu-id="e6fea-106">Keywords</span></span>|<span data-ttu-id="e6fea-107">疑难解答</span><span class="sxs-lookup"><span data-stu-id="e6fea-107">Troubleshooting</span></span>|  
|<span data-ttu-id="e6fea-108">级别</span><span class="sxs-lookup"><span data-stu-id="e6fea-108">Level</span></span>|<span data-ttu-id="e6fea-109">信息</span><span class="sxs-lookup"><span data-stu-id="e6fea-109">Information</span></span>|  
|<span data-ttu-id="e6fea-110">通道</span><span class="sxs-lookup"><span data-stu-id="e6fea-110">Channel</span></span>|<span data-ttu-id="e6fea-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="e6fea-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="e6fea-112">描述</span><span class="sxs-lookup"><span data-stu-id="e6fea-112">Description</span></span>  
 <span data-ttu-id="e6fea-113">此事件标记端对端活动的开始。</span><span class="sxs-lookup"><span data-stu-id="e6fea-113">This event marks the beginning of an end-to-end activity.</span></span> <span data-ttu-id="e6fea-114">它包含活动的名称。</span><span class="sxs-lookup"><span data-stu-id="e6fea-114">It contains the name of the activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="e6fea-115">消息</span><span class="sxs-lookup"><span data-stu-id="e6fea-115">Message</span></span>  
 <span data-ttu-id="e6fea-116">活动边界。</span><span class="sxs-lookup"><span data-stu-id="e6fea-116">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="e6fea-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="e6fea-117">Details</span></span>  
  
|<span data-ttu-id="e6fea-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="e6fea-118">Data Item Name</span></span>|<span data-ttu-id="e6fea-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="e6fea-119">Data Item Type</span></span>|<span data-ttu-id="e6fea-120">描述</span><span class="sxs-lookup"><span data-stu-id="e6fea-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="e6fea-121">扩展数据</span><span class="sxs-lookup"><span data-stu-id="e6fea-121">Extended Data</span></span>|`xs:string`|<span data-ttu-id="e6fea-122">活动的名称。</span><span class="sxs-lookup"><span data-stu-id="e6fea-122">The name of the activity.</span></span>|  
|<span data-ttu-id="e6fea-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="e6fea-123">AppDomain</span></span>|`xs:string`|<span data-ttu-id="e6fea-124">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="e6fea-124">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
