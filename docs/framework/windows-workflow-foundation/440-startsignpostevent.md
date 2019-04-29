---
title: 440 - StartSignpostEvent1
ms.date: 03/30/2017
ms.assetid: 27b551b5-ae76-49f8-bab8-6300009eb4c1
ms.openlocfilehash: 4b2b6b0fa9df4725edd4929512eb1d7534d933b1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774128"
---
# <a name="440---startsignpostevent1"></a><span data-ttu-id="6e196-102">440 - StartSignpostEvent1</span><span class="sxs-lookup"><span data-stu-id="6e196-102">440 - StartSignpostEvent1</span></span>
## <a name="properties"></a><span data-ttu-id="6e196-103">属性</span><span class="sxs-lookup"><span data-stu-id="6e196-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6e196-104">Id</span><span class="sxs-lookup"><span data-stu-id="6e196-104">ID</span></span>|<span data-ttu-id="6e196-105">440</span><span class="sxs-lookup"><span data-stu-id="6e196-105">440</span></span>|  
|<span data-ttu-id="6e196-106">关键字</span><span class="sxs-lookup"><span data-stu-id="6e196-106">Keywords</span></span>|<span data-ttu-id="6e196-107">疑难解答</span><span class="sxs-lookup"><span data-stu-id="6e196-107">Troubleshooting</span></span>|  
|<span data-ttu-id="6e196-108">级别</span><span class="sxs-lookup"><span data-stu-id="6e196-108">Level</span></span>|<span data-ttu-id="6e196-109">信息</span><span class="sxs-lookup"><span data-stu-id="6e196-109">Information</span></span>|  
|<span data-ttu-id="6e196-110">通道</span><span class="sxs-lookup"><span data-stu-id="6e196-110">Channel</span></span>|<span data-ttu-id="6e196-111">Microsoft-Windows-应用程序服务器-应用程序/分析</span><span class="sxs-lookup"><span data-stu-id="6e196-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="6e196-112">描述</span><span class="sxs-lookup"><span data-stu-id="6e196-112">Description</span></span>  
 <span data-ttu-id="6e196-113">在活动跟踪中，指示消息是否已开始跨越发送或接收中的活动边界。</span><span class="sxs-lookup"><span data-stu-id="6e196-113">In activity tracing, indicates a message has started crossing an activity boundary in send or receive.</span></span>  
  
## <a name="message"></a><span data-ttu-id="6e196-114">消息</span><span class="sxs-lookup"><span data-stu-id="6e196-114">Message</span></span>  
 <span data-ttu-id="6e196-115">活动边界。</span><span class="sxs-lookup"><span data-stu-id="6e196-115">Activity boundary.</span></span>  
  
## <a name="details"></a><span data-ttu-id="6e196-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="6e196-116">Details</span></span>  
  
|<span data-ttu-id="6e196-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="6e196-117">Data Item Name</span></span>|<span data-ttu-id="6e196-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="6e196-118">Data Item Type</span></span>|<span data-ttu-id="6e196-119">描述</span><span class="sxs-lookup"><span data-stu-id="6e196-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="6e196-120">ExtendedData</span><span class="sxs-lookup"><span data-stu-id="6e196-120">ExtendedData</span></span>|`xs:string`|<span data-ttu-id="6e196-121">活动的名称。</span><span class="sxs-lookup"><span data-stu-id="6e196-121">The name of the activity.</span></span>|  
|<span data-ttu-id="6e196-122">应用程序域</span><span class="sxs-lookup"><span data-stu-id="6e196-122">AppDomain</span></span>|`xs:string`|<span data-ttu-id="6e196-123">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="6e196-123">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
