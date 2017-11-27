---
title: 4206 - UnlockInstanceException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5a46dc5f-d517-4135-8905-25a42f01206b
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 349844edb44e547a666f10c8d210d120ebf5a39f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="4206---unlockinstanceexception"></a><span data-ttu-id="78d48-102">4206 - UnlockInstanceException</span><span class="sxs-lookup"><span data-stu-id="78d48-102">4206 - UnlockInstanceException</span></span>
## <a name="properties"></a><span data-ttu-id="78d48-103">属性</span><span class="sxs-lookup"><span data-stu-id="78d48-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="78d48-104">ID</span><span class="sxs-lookup"><span data-stu-id="78d48-104">ID</span></span>|<span data-ttu-id="78d48-105">4206</span><span class="sxs-lookup"><span data-stu-id="78d48-105">4206</span></span>|  
|<span data-ttu-id="78d48-106">关键字</span><span class="sxs-lookup"><span data-stu-id="78d48-106">Keywords</span></span>|<span data-ttu-id="78d48-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="78d48-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="78d48-108">级别</span><span class="sxs-lookup"><span data-stu-id="78d48-108">Level</span></span>|<span data-ttu-id="78d48-109">错误</span><span class="sxs-lookup"><span data-stu-id="78d48-109">Error</span></span>|  
|<span data-ttu-id="78d48-110">通道</span><span class="sxs-lookup"><span data-stu-id="78d48-110">Channel</span></span>|<span data-ttu-id="78d48-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="78d48-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="78d48-112">描述</span><span class="sxs-lookup"><span data-stu-id="78d48-112">Description</span></span>  
 <span data-ttu-id="78d48-113">指示在尝试解锁某一实例时遇到了异常。</span><span class="sxs-lookup"><span data-stu-id="78d48-113">Indicates an exception was encountered while trying to unlock an instance.</span></span>  
  
## <a name="message"></a><span data-ttu-id="78d48-114">消息</span><span class="sxs-lookup"><span data-stu-id="78d48-114">Message</span></span>  
 <span data-ttu-id="78d48-115">尝试解除实例锁定时遇到异常 %1。</span><span class="sxs-lookup"><span data-stu-id="78d48-115">Encountered exception %1 while attempting to unlock instance.</span></span>  
  
## <a name="details"></a><span data-ttu-id="78d48-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="78d48-116">Details</span></span>  
  
|<span data-ttu-id="78d48-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="78d48-117">Data Item Name</span></span>|<span data-ttu-id="78d48-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="78d48-118">Data Item Type</span></span>|<span data-ttu-id="78d48-119">描述</span><span class="sxs-lookup"><span data-stu-id="78d48-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="78d48-120">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="78d48-120">ExceptionMessage</span></span>|<span data-ttu-id="78d48-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="78d48-121">xs:string</span></span>|<span data-ttu-id="78d48-122">来自 SQL 异常的消息。</span><span class="sxs-lookup"><span data-stu-id="78d48-122">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="78d48-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="78d48-123">AppDomain</span></span>|<span data-ttu-id="78d48-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="78d48-124">xs:string</span></span>|<span data-ttu-id="78d48-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="78d48-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
