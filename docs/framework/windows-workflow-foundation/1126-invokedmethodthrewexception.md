---
title: 1126 - InvokedMethodThrewException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d3cff1a-97e6-4b6c-be18-108c6881bfc0
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a1021d7d23b8e9c25684da567b769c24380a8a0a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="1126---invokedmethodthrewexception"></a><span data-ttu-id="9be8a-102">1126 - InvokedMethodThrewException</span><span class="sxs-lookup"><span data-stu-id="9be8a-102">1126 - InvokedMethodThrewException</span></span>
## <a name="properties"></a><span data-ttu-id="9be8a-103">属性</span><span class="sxs-lookup"><span data-stu-id="9be8a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9be8a-104">ID</span><span class="sxs-lookup"><span data-stu-id="9be8a-104">ID</span></span>|<span data-ttu-id="9be8a-105">1126</span><span class="sxs-lookup"><span data-stu-id="9be8a-105">1126</span></span>|  
|<span data-ttu-id="9be8a-106">关键字</span><span class="sxs-lookup"><span data-stu-id="9be8a-106">Keywords</span></span>|<span data-ttu-id="9be8a-107">WFRuntime</span><span class="sxs-lookup"><span data-stu-id="9be8a-107">WFRuntime</span></span>|  
|<span data-ttu-id="9be8a-108">级别</span><span class="sxs-lookup"><span data-stu-id="9be8a-108">Level</span></span>|<span data-ttu-id="9be8a-109">信息</span><span class="sxs-lookup"><span data-stu-id="9be8a-109">Information</span></span>|  
|<span data-ttu-id="9be8a-110">通道</span><span class="sxs-lookup"><span data-stu-id="9be8a-110">Channel</span></span>|<span data-ttu-id="9be8a-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="9be8a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9be8a-112">描述</span><span class="sxs-lookup"><span data-stu-id="9be8a-112">Description</span></span>  
 <span data-ttu-id="9be8a-113">指示 InvokeMethod 活动调用的方法引发了异常。</span><span class="sxs-lookup"><span data-stu-id="9be8a-113">Indicates an exception was thrown by the method called by the InvokeMethod activity.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9be8a-114">消息</span><span class="sxs-lookup"><span data-stu-id="9be8a-114">Message</span></span>  
 <span data-ttu-id="9be8a-115">在活动“%1”调用的方法中，引发了异常。</span><span class="sxs-lookup"><span data-stu-id="9be8a-115">An exception was thrown in the method called by the activity '%1'.</span></span> <span data-ttu-id="9be8a-116">%2</span><span class="sxs-lookup"><span data-stu-id="9be8a-116">%2</span></span>  
  
## <a name="details"></a><span data-ttu-id="9be8a-117">详细信息</span><span class="sxs-lookup"><span data-stu-id="9be8a-117">Details</span></span>  
  
|<span data-ttu-id="9be8a-118">数据项名称</span><span class="sxs-lookup"><span data-stu-id="9be8a-118">Data Item Name</span></span>|<span data-ttu-id="9be8a-119">数据项类型</span><span class="sxs-lookup"><span data-stu-id="9be8a-119">Data Item Type</span></span>|<span data-ttu-id="9be8a-120">描述</span><span class="sxs-lookup"><span data-stu-id="9be8a-120">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9be8a-121">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="9be8a-121">InvokeMethod</span></span>|<span data-ttu-id="9be8a-122">xs:string</span><span class="sxs-lookup"><span data-stu-id="9be8a-122">xs:string</span></span>|<span data-ttu-id="9be8a-123">InvokeMethod 活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="9be8a-123">The display name of the InvokeMethod activity.</span></span>|  
|<span data-ttu-id="9be8a-124">例外</span><span class="sxs-lookup"><span data-stu-id="9be8a-124">Exception</span></span>|<span data-ttu-id="9be8a-125">xs:string</span><span class="sxs-lookup"><span data-stu-id="9be8a-125">xs:string</span></span>|<span data-ttu-id="9be8a-126">异常的异常详细信息</span><span class="sxs-lookup"><span data-stu-id="9be8a-126">The exception details for the exception</span></span>|  
|<span data-ttu-id="9be8a-127">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9be8a-127">AppDomain</span></span>|<span data-ttu-id="9be8a-128">xs:string</span><span class="sxs-lookup"><span data-stu-id="9be8a-128">xs:string</span></span>|<span data-ttu-id="9be8a-129">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="9be8a-129">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
