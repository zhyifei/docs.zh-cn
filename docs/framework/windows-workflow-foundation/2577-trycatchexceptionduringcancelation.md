---
title: 2577 - TryCatchExceptionDuringCancelation
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 35ee9f55-227f-4566-bcb4-4c7c75dea85b
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 2a4bc0d9ab45fe8e2f025c651fce137d6a4255bc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="2577---trycatchexceptionduringcancelation"></a><span data-ttu-id="36139-102">2577 - TryCatchExceptionDuringCancelation</span><span class="sxs-lookup"><span data-stu-id="36139-102">2577 - TryCatchExceptionDuringCancelation</span></span>
## <a name="properties"></a><span data-ttu-id="36139-103">属性</span><span class="sxs-lookup"><span data-stu-id="36139-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="36139-104">ID</span><span class="sxs-lookup"><span data-stu-id="36139-104">ID</span></span>|<span data-ttu-id="36139-105">2577</span><span class="sxs-lookup"><span data-stu-id="36139-105">2577</span></span>|  
|<span data-ttu-id="36139-106">关键字</span><span class="sxs-lookup"><span data-stu-id="36139-106">Keywords</span></span>|<span data-ttu-id="36139-107">WFActivities</span><span class="sxs-lookup"><span data-stu-id="36139-107">WFActivities</span></span>|  
|<span data-ttu-id="36139-108">级别</span><span class="sxs-lookup"><span data-stu-id="36139-108">Level</span></span>|<span data-ttu-id="36139-109">警告</span><span class="sxs-lookup"><span data-stu-id="36139-109">Warning</span></span>|  
|<span data-ttu-id="36139-110">通道</span><span class="sxs-lookup"><span data-stu-id="36139-110">Channel</span></span>|<span data-ttu-id="36139-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="36139-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="36139-112">描述</span><span class="sxs-lookup"><span data-stu-id="36139-112">Description</span></span>  
 <span data-ttu-id="36139-113">支持 TryCatch 活动的子活动在取消过程中引发了异常。</span><span class="sxs-lookup"><span data-stu-id="36139-113">Indicates a child activity of the TryCatch activity has thrown an exception during cancelation.</span></span>  
  
## <a name="message"></a><span data-ttu-id="36139-114">消息</span><span class="sxs-lookup"><span data-stu-id="36139-114">Message</span></span>  
 <span data-ttu-id="36139-115">TryCatch 活动“%1”的子活动在取消过程中引发了异常。</span><span class="sxs-lookup"><span data-stu-id="36139-115">A child activity of the TryCatch activity '%1' has thrown an exception during cancelation.</span></span>  
  
## <a name="details"></a><span data-ttu-id="36139-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="36139-116">Details</span></span>  
  
|<span data-ttu-id="36139-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="36139-117">Data Item Name</span></span>|<span data-ttu-id="36139-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="36139-118">Data Item Type</span></span>|<span data-ttu-id="36139-119">描述</span><span class="sxs-lookup"><span data-stu-id="36139-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="36139-120">DisplayName</span><span class="sxs-lookup"><span data-stu-id="36139-120">DisplayName</span></span>|<span data-ttu-id="36139-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="36139-121">xs:string</span></span>|<span data-ttu-id="36139-122">活动的显示名称。</span><span class="sxs-lookup"><span data-stu-id="36139-122">The display name of the activity.</span></span>|  
|<span data-ttu-id="36139-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="36139-123">AppDomain</span></span>|<span data-ttu-id="36139-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="36139-124">xs:string</span></span>|<span data-ttu-id="36139-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="36139-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
