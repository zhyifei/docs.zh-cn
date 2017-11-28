---
title: 2576 - TryCatchExceptionFromTry
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 47e48973-b17c-4a16-8338-c84b54aa0a6e
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f038b3d728020980382f3d5a9f63420e945665d4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="2576---trycatchexceptionfromtry"></a><span data-ttu-id="d2f39-102">2576 - TryCatchExceptionFromTry</span><span class="sxs-lookup"><span data-stu-id="d2f39-102">2576 - TryCatchExceptionFromTry</span></span>
## <a name="properties"></a><span data-ttu-id="d2f39-103">属性</span><span class="sxs-lookup"><span data-stu-id="d2f39-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d2f39-104">ID</span><span class="sxs-lookup"><span data-stu-id="d2f39-104">ID</span></span>|<span data-ttu-id="d2f39-105">2576</span><span class="sxs-lookup"><span data-stu-id="d2f39-105">2576</span></span>|  
|<span data-ttu-id="d2f39-106">关键字</span><span class="sxs-lookup"><span data-stu-id="d2f39-106">Keywords</span></span>|<span data-ttu-id="d2f39-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="d2f39-107">WFActivities</span></span>|  
|<span data-ttu-id="d2f39-108">级别</span><span class="sxs-lookup"><span data-stu-id="d2f39-108">Level</span></span>|<span data-ttu-id="d2f39-109">信息</span><span class="sxs-lookup"><span data-stu-id="d2f39-109">Information</span></span>|  
|<span data-ttu-id="d2f39-110">通道</span><span class="sxs-lookup"><span data-stu-id="d2f39-110">Channel</span></span>|<span data-ttu-id="d2f39-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="d2f39-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="d2f39-112">描述</span><span class="sxs-lookup"><span data-stu-id="d2f39-112">Description</span></span>  
 <span data-ttu-id="d2f39-113">指示 TryCatch 活动捕获了异常。</span><span class="sxs-lookup"><span data-stu-id="d2f39-113">Indicates the TryCatch activity has caught an exception.</span></span>  
  
## <a name="message"></a><span data-ttu-id="d2f39-114">消息</span><span class="sxs-lookup"><span data-stu-id="d2f39-114">Message</span></span>  
 <span data-ttu-id="d2f39-115">TryCatch 活动“%1”捕获了“%2”类型的异常。</span><span class="sxs-lookup"><span data-stu-id="d2f39-115">The TryCatch activity '%1' has caught an exception of type '%2'.</span></span>  
  
## <a name="details"></a><span data-ttu-id="d2f39-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="d2f39-116">Details</span></span>  
  
|<span data-ttu-id="d2f39-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="d2f39-117">Data Item Name</span></span>|<span data-ttu-id="d2f39-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="d2f39-118">Data Item Type</span></span>|<span data-ttu-id="d2f39-119">描述</span><span class="sxs-lookup"><span data-stu-id="d2f39-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="d2f39-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d2f39-120">DisplayName</span></span>|<span data-ttu-id="d2f39-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="d2f39-121">xs:string</span></span>|<span data-ttu-id="d2f39-122">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="d2f39-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="d2f39-123">例外</span><span class="sxs-lookup"><span data-stu-id="d2f39-123">Exception</span></span>|<span data-ttu-id="d2f39-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="d2f39-124">xs:string</span></span>|<span data-ttu-id="d2f39-125">异常的类型名称。</span><span class="sxs-lookup"><span data-stu-id="d2f39-125">The type name of the exception.</span></span>|  
|<span data-ttu-id="d2f39-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="d2f39-126">AppDomain</span></span>|<span data-ttu-id="d2f39-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="d2f39-127">xs:string</span></span>|<span data-ttu-id="d2f39-128">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="d2f39-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
