---
title: 1125 - InvokeMethodIsNotStatic
ms.date: 03/30/2017
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
ms.openlocfilehash: 692c5e56dac0a69ab5705acd284f048391145641
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33511938"
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="13b95-102">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="13b95-102">1125 - InvokeMethodIsNotStatic</span></span>
## <a name="properties"></a><span data-ttu-id="13b95-103">属性</span><span class="sxs-lookup"><span data-stu-id="13b95-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="13b95-104">ID</span><span class="sxs-lookup"><span data-stu-id="13b95-104">ID</span></span>|<span data-ttu-id="13b95-105">1125</span><span class="sxs-lookup"><span data-stu-id="13b95-105">1125</span></span>|  
|<span data-ttu-id="13b95-106">关键字</span><span class="sxs-lookup"><span data-stu-id="13b95-106">Keywords</span></span>|<span data-ttu-id="13b95-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="13b95-107">WFRuntime</span></span>|  
|<span data-ttu-id="13b95-108">级别</span><span class="sxs-lookup"><span data-stu-id="13b95-108">Level</span></span>|<span data-ttu-id="13b95-109">信息</span><span class="sxs-lookup"><span data-stu-id="13b95-109">Information</span></span>|  
|<span data-ttu-id="13b95-110">通道</span><span class="sxs-lookup"><span data-stu-id="13b95-110">Channel</span></span>|<span data-ttu-id="13b95-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="13b95-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="13b95-112">描述</span><span class="sxs-lookup"><span data-stu-id="13b95-112">Description</span></span>  
 <span data-ttu-id="13b95-113">在 CacheMetadata 步骤中，InvokeMethod 活动指示要调用的方法是非静态的。</span><span class="sxs-lookup"><span data-stu-id="13b95-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="13b95-114">消息</span><span class="sxs-lookup"><span data-stu-id="13b95-114">Message</span></span>  
 <span data-ttu-id="13b95-115">InvokeMethod“%1”- 方法非静态。</span><span class="sxs-lookup"><span data-stu-id="13b95-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="13b95-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="13b95-116">Details</span></span>  
  
|<span data-ttu-id="13b95-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="13b95-117">Data Item Name</span></span>|<span data-ttu-id="13b95-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="13b95-118">Data Item Type</span></span>|<span data-ttu-id="13b95-119">描述</span><span class="sxs-lookup"><span data-stu-id="13b95-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="13b95-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="13b95-120">InvokeMethod</span></span>|<span data-ttu-id="13b95-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="13b95-121">xs:string</span></span>|<span data-ttu-id="13b95-122">InvokeMethod 活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="13b95-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="13b95-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="13b95-123">AppDomain</span></span>|<span data-ttu-id="13b95-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="13b95-124">xs:string</span></span>|<span data-ttu-id="13b95-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="13b95-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
