---
title: 1131 - InvokeMethodUseAsyncPattern
ms.date: 03/30/2017
ms.assetid: eca50fa7-5276-4759-ad1c-e490b9bd1f82
ms.openlocfilehash: 150973935d12455aa671043a619fbd6fd7e77425
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009950"
---
# <a name="1131---invokemethoduseasyncpattern"></a><span data-ttu-id="4fa64-102">1131 - InvokeMethodUseAsyncPattern</span><span class="sxs-lookup"><span data-stu-id="4fa64-102">1131 - InvokeMethodUseAsyncPattern</span></span>
## <a name="properties"></a><span data-ttu-id="4fa64-103">属性</span><span class="sxs-lookup"><span data-stu-id="4fa64-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4fa64-104">Id</span><span class="sxs-lookup"><span data-stu-id="4fa64-104">ID</span></span>|<span data-ttu-id="4fa64-105">1131</span><span class="sxs-lookup"><span data-stu-id="4fa64-105">1131</span></span>|  
|<span data-ttu-id="4fa64-106">关键字</span><span class="sxs-lookup"><span data-stu-id="4fa64-106">Keywords</span></span>|<span data-ttu-id="4fa64-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="4fa64-107">WFRuntime</span></span>|  
|<span data-ttu-id="4fa64-108">级别</span><span class="sxs-lookup"><span data-stu-id="4fa64-108">Level</span></span>|<span data-ttu-id="4fa64-109">信息</span><span class="sxs-lookup"><span data-stu-id="4fa64-109">Information</span></span>|  
|<span data-ttu-id="4fa64-110">通道</span><span class="sxs-lookup"><span data-stu-id="4fa64-110">Channel</span></span>|<span data-ttu-id="4fa64-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="4fa64-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="4fa64-112">描述</span><span class="sxs-lookup"><span data-stu-id="4fa64-112">Description</span></span>  
 <span data-ttu-id="4fa64-113">在 CacheMetadata 步骤中，InvokeMethod 活动指示它在调用方法时使用异步模式。</span><span class="sxs-lookup"><span data-stu-id="4fa64-113">During CacheMetadata step, InvokeMethod activity indicates that it is using the async pattern when invoking the method.</span></span>  
  
## <a name="message"></a><span data-ttu-id="4fa64-114">消息</span><span class="sxs-lookup"><span data-stu-id="4fa64-114">Message</span></span>  
 <span data-ttu-id="4fa64-115">InvokeMethod“%1”- 方法使用“%2”和“%3”的异步模式。</span><span class="sxs-lookup"><span data-stu-id="4fa64-115">InvokeMethod '%1' - method uses asynchronous pattern of '%2' and '%3'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="4fa64-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="4fa64-116">Details</span></span>  
  
|<span data-ttu-id="4fa64-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="4fa64-117">Data Item Name</span></span>|<span data-ttu-id="4fa64-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="4fa64-118">Data Item Type</span></span>|<span data-ttu-id="4fa64-119">描述</span><span class="sxs-lookup"><span data-stu-id="4fa64-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="4fa64-120">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="4fa64-120">InvokeMethod</span></span>|<span data-ttu-id="4fa64-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="4fa64-121">xs:string</span></span>|<span data-ttu-id="4fa64-122">InvokeMethod 活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="4fa64-122">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="4fa64-123">BeginMethod</span><span class="sxs-lookup"><span data-stu-id="4fa64-123">BeginMethod</span></span>|<span data-ttu-id="4fa64-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="4fa64-124">xs:string</span></span>|<span data-ttu-id="4fa64-125">begin 方法的名称。</span><span class="sxs-lookup"><span data-stu-id="4fa64-125">The name of the begin method.</span></span>|  
|<span data-ttu-id="4fa64-126">EndMethod</span><span class="sxs-lookup"><span data-stu-id="4fa64-126">EndMethod</span></span>|<span data-ttu-id="4fa64-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="4fa64-127">xs:string</span></span>|<span data-ttu-id="4fa64-128">end 方法的名称。</span><span class="sxs-lookup"><span data-stu-id="4fa64-128">The name of the end method.</span></span>|  
|<span data-ttu-id="4fa64-129">应用程序域</span><span class="sxs-lookup"><span data-stu-id="4fa64-129">AppDomain</span></span>|<span data-ttu-id="4fa64-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="4fa64-130">xs:string</span></span>|<span data-ttu-id="4fa64-131">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="4fa64-131">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
