---
title: 4210 - SqlExceptionCaught
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f0ce8af3-eb4c-48c8-b3d9-dd2f94b5574b
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a3fb3c780b80172db8770e717f517b97608fcb7c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="4210---sqlexceptioncaught"></a><span data-ttu-id="cd46a-102">4210 - SqlExceptionCaught</span><span class="sxs-lookup"><span data-stu-id="cd46a-102">4210 - SqlExceptionCaught</span></span>
## <a name="properties"></a><span data-ttu-id="cd46a-103">属性</span><span class="sxs-lookup"><span data-stu-id="cd46a-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cd46a-104">ID</span><span class="sxs-lookup"><span data-stu-id="cd46a-104">ID</span></span>|<span data-ttu-id="cd46a-105">4210</span><span class="sxs-lookup"><span data-stu-id="cd46a-105">4210</span></span>|  
|<span data-ttu-id="cd46a-106">关键字</span><span class="sxs-lookup"><span data-stu-id="cd46a-106">Keywords</span></span>|<span data-ttu-id="cd46a-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="cd46a-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="cd46a-108">级别</span><span class="sxs-lookup"><span data-stu-id="cd46a-108">Level</span></span>|<span data-ttu-id="cd46a-109">警告</span><span class="sxs-lookup"><span data-stu-id="cd46a-109">Warning</span></span>|  
|<span data-ttu-id="cd46a-110">通道</span><span class="sxs-lookup"><span data-stu-id="cd46a-110">Channel</span></span>|<span data-ttu-id="cd46a-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="cd46a-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="cd46a-112">描述</span><span class="sxs-lookup"><span data-stu-id="cd46a-112">Description</span></span>  
 <span data-ttu-id="cd46a-113">指示捕获了 SQL 异常。</span><span class="sxs-lookup"><span data-stu-id="cd46a-113">Indicates a SQL exception was caught.</span></span>  
  
## <a name="message"></a><span data-ttu-id="cd46a-114">消息</span><span class="sxs-lookup"><span data-stu-id="cd46a-114">Message</span></span>  
 <span data-ttu-id="cd46a-115">已捕获 SQL 异常编号为 %1 的消息 %2。</span><span class="sxs-lookup"><span data-stu-id="cd46a-115">Caught SQL Exception number %1 message %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="cd46a-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="cd46a-116">Details</span></span>  
  
|<span data-ttu-id="cd46a-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="cd46a-117">Data Item Name</span></span>|<span data-ttu-id="cd46a-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="cd46a-118">Data Item Type</span></span>|<span data-ttu-id="cd46a-119">描述</span><span class="sxs-lookup"><span data-stu-id="cd46a-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="cd46a-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="cd46a-120">ErrorNumber</span></span>|<span data-ttu-id="cd46a-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="cd46a-121">xs:string</span></span>|<span data-ttu-id="cd46a-122">SQL 错误号。</span><span class="sxs-lookup"><span data-stu-id="cd46a-122">The SQL error number.</span></span>|  
|<span data-ttu-id="cd46a-123">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="cd46a-123">ExceptionMessage</span></span>|<span data-ttu-id="cd46a-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="cd46a-124">xs:string</span></span>|<span data-ttu-id="cd46a-125">来自 SQL 异常的消息。</span><span class="sxs-lookup"><span data-stu-id="cd46a-125">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="cd46a-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="cd46a-126">AppDomain</span></span>|<span data-ttu-id="cd46a-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="cd46a-127">xs:string</span></span>|<span data-ttu-id="cd46a-128">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="cd46a-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
