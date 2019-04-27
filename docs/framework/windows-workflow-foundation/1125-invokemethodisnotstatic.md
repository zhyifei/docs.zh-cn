---
title: 1125 - InvokeMethodIsNotStatic
ms.date: 03/30/2017
ms.assetid: ea2b3827-63da-497b-b2c3-d5cebefe57a1
ms.openlocfilehash: 692c5e56dac0a69ab5705acd284f048391145641
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61924251"
---
# <a name="1125---invokemethodisnotstatic"></a><span data-ttu-id="93163-102">1125 - InvokeMethodIsNotStatic</span><span class="sxs-lookup"><span data-stu-id="93163-102">1125 - InvokeMethodIsNotStatic</span></span>
## <a name="properties"></a><span data-ttu-id="93163-103">属性</span><span class="sxs-lookup"><span data-stu-id="93163-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="93163-104">Id</span><span class="sxs-lookup"><span data-stu-id="93163-104">ID</span></span>|<span data-ttu-id="93163-105">1125</span><span class="sxs-lookup"><span data-stu-id="93163-105">1125</span></span>|  
|<span data-ttu-id="93163-106">关键字</span><span class="sxs-lookup"><span data-stu-id="93163-106">Keywords</span></span>|<span data-ttu-id="93163-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="93163-107">WFRuntime</span></span>|  
|<span data-ttu-id="93163-108">级别</span><span class="sxs-lookup"><span data-stu-id="93163-108">Level</span></span>|<span data-ttu-id="93163-109">信息</span><span class="sxs-lookup"><span data-stu-id="93163-109">Information</span></span>|  
|<span data-ttu-id="93163-110">通道</span><span class="sxs-lookup"><span data-stu-id="93163-110">Channel</span></span>|<span data-ttu-id="93163-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="93163-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="93163-112">描述</span><span class="sxs-lookup"><span data-stu-id="93163-112">Description</span></span>  
 <span data-ttu-id="93163-113">在 CacheMetadata 步骤中，InvokeMethod 活动指示要调用的方法是非静态的。</span><span class="sxs-lookup"><span data-stu-id="93163-113">During CacheMetadata step, InvokeMethod activity indicates the method to be invoked is not static.</span></span>  
  
## <a name="message"></a><span data-ttu-id="93163-114">消息</span><span class="sxs-lookup"><span data-stu-id="93163-114">Message</span></span>  
 <span data-ttu-id="93163-115">InvokeMethod“%1”- 方法非静态。</span><span class="sxs-lookup"><span data-stu-id="93163-115">InvokeMethod '%1' - method is not Static.</span></span>  
  
## <a name="details"></a><span data-ttu-id="93163-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="93163-116">Details</span></span>  
  
|<span data-ttu-id="93163-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="93163-117">Data Item Name</span></span>|<span data-ttu-id="93163-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="93163-118">Data Item Type</span></span>|<span data-ttu-id="93163-119">描述</span><span class="sxs-lookup"><span data-stu-id="93163-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="93163-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="93163-120">InvokeMethod</span></span>|<span data-ttu-id="93163-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="93163-121">xs:string</span></span>|<span data-ttu-id="93163-122">InvokeMethod 活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="93163-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="93163-123">应用程序域</span><span class="sxs-lookup"><span data-stu-id="93163-123">AppDomain</span></span>|<span data-ttu-id="93163-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="93163-124">xs:string</span></span>|<span data-ttu-id="93163-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="93163-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
