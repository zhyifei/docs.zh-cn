---
title: 1132 - InvokeMethodDoesNotUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: 436b3767-4460-46b0-9ea3-fc2963260c11
ms.openlocfilehash: 64701d4c38c042e8273129be19f9caeb2c442abf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924210"
---
# <a name="1132---invokemethoddoesnotuseasyncpattern"></a><span data-ttu-id="384fa-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="384fa-102">1132 - InvokeMethodDoesNotUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="384fa-103">属性</span><span class="sxs-lookup"><span data-stu-id="384fa-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="384fa-104">Id</span><span class="sxs-lookup"><span data-stu-id="384fa-104">ID</span></span>|<span data-ttu-id="384fa-105">1132</span><span class="sxs-lookup"><span data-stu-id="384fa-105">1132</span></span>|  
|<span data-ttu-id="384fa-106">关键字</span><span class="sxs-lookup"><span data-stu-id="384fa-106">Keywords</span></span>|<span data-ttu-id="384fa-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="384fa-107">WFRuntime</span></span>|  
|<span data-ttu-id="384fa-108">级别</span><span class="sxs-lookup"><span data-stu-id="384fa-108">Level</span></span>|<span data-ttu-id="384fa-109">信息</span><span class="sxs-lookup"><span data-stu-id="384fa-109">Information</span></span>|  
|<span data-ttu-id="384fa-110">通道</span><span class="sxs-lookup"><span data-stu-id="384fa-110">Channel</span></span>|<span data-ttu-id="384fa-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="384fa-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="384fa-112">描述</span><span class="sxs-lookup"><span data-stu-id="384fa-112">Description</span></span>  
 <span data-ttu-id="384fa-113">在 CacheMetadata 步骤中，InvokeMethod 活动指示它在调用方法时未使用异步模式。</span><span class="sxs-lookup"><span data-stu-id="384fa-113">During CacheMetadata step, InvokeMethod activity indicates that it is not using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="384fa-114">消息</span><span class="sxs-lookup"><span data-stu-id="384fa-114">Message</span></span>  
 <span data-ttu-id="384fa-115">InvokeMethod“%1”- 方法不使用异步模式。</span><span class="sxs-lookup"><span data-stu-id="384fa-115">InvokeMethod '%1' - method does not use asynchronous pattern.</span></span>  
  
## <a name="details"></a><span data-ttu-id="384fa-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="384fa-116">Details</span></span>  
  
|<span data-ttu-id="384fa-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="384fa-117">Data Item Name</span></span>|<span data-ttu-id="384fa-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="384fa-118">Data Item Type</span></span>|<span data-ttu-id="384fa-119">描述</span><span class="sxs-lookup"><span data-stu-id="384fa-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="384fa-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="384fa-120">InvokeMethod</span></span>|<span data-ttu-id="384fa-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="384fa-121">xs:string</span></span>|<span data-ttu-id="384fa-122">InvokeMethod 活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="384fa-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="384fa-123">应用程序域</span><span class="sxs-lookup"><span data-stu-id="384fa-123">AppDomain</span></span>|<span data-ttu-id="384fa-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="384fa-124">xs:string</span></span>|<span data-ttu-id="384fa-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="384fa-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
