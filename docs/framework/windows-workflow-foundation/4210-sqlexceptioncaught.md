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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7857bb865bb8eea8fc9d1d56c1b6e69c33f7165d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="4210---sqlexceptioncaught"></a><span data-ttu-id="9325d-102">4210 - SqlExceptionCaught</span><span class="sxs-lookup"><span data-stu-id="9325d-102">4210 - SqlExceptionCaught</span></span>
## <a name="properties"></a><span data-ttu-id="9325d-103">属性</span><span class="sxs-lookup"><span data-stu-id="9325d-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="9325d-104">ID</span><span class="sxs-lookup"><span data-stu-id="9325d-104">ID</span></span>|<span data-ttu-id="9325d-105">4210</span><span class="sxs-lookup"><span data-stu-id="9325d-105">4210</span></span>|  
|<span data-ttu-id="9325d-106">关键字</span><span class="sxs-lookup"><span data-stu-id="9325d-106">Keywords</span></span>|<span data-ttu-id="9325d-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="9325d-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="9325d-108">级别</span><span class="sxs-lookup"><span data-stu-id="9325d-108">Level</span></span>|<span data-ttu-id="9325d-109">警告</span><span class="sxs-lookup"><span data-stu-id="9325d-109">Warning</span></span>|  
|<span data-ttu-id="9325d-110">通道</span><span class="sxs-lookup"><span data-stu-id="9325d-110">Channel</span></span>|<span data-ttu-id="9325d-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="9325d-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="9325d-112">描述</span><span class="sxs-lookup"><span data-stu-id="9325d-112">Description</span></span>  
 <span data-ttu-id="9325d-113">指示捕获了 SQL 异常。</span><span class="sxs-lookup"><span data-stu-id="9325d-113">Indicates a SQL exception was caught.</span></span>  
  
## <a name="message"></a><span data-ttu-id="9325d-114">消息</span><span class="sxs-lookup"><span data-stu-id="9325d-114">Message</span></span>  
 <span data-ttu-id="9325d-115">已捕获 SQL 异常编号为 %1 的消息 %2。</span><span class="sxs-lookup"><span data-stu-id="9325d-115">Caught SQL Exception number %1 message %2.</span></span>  
  
## <a name="details"></a><span data-ttu-id="9325d-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="9325d-116">Details</span></span>  
  
|<span data-ttu-id="9325d-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="9325d-117">Data Item Name</span></span>|<span data-ttu-id="9325d-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="9325d-118">Data Item Type</span></span>|<span data-ttu-id="9325d-119">描述</span><span class="sxs-lookup"><span data-stu-id="9325d-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="9325d-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="9325d-120">ErrorNumber</span></span>|<span data-ttu-id="9325d-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="9325d-121">xs:string</span></span>|<span data-ttu-id="9325d-122">SQL 错误号。</span><span class="sxs-lookup"><span data-stu-id="9325d-122">The SQL error number.</span></span>|  
|<span data-ttu-id="9325d-123">ExceptionMessage</span><span class="sxs-lookup"><span data-stu-id="9325d-123">ExceptionMessage</span></span>|<span data-ttu-id="9325d-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="9325d-124">xs:string</span></span>|<span data-ttu-id="9325d-125">来自 SQL 异常的消息。</span><span class="sxs-lookup"><span data-stu-id="9325d-125">The message from the SQL exception.</span></span>|  
|<span data-ttu-id="9325d-126">AppDomain</span><span class="sxs-lookup"><span data-stu-id="9325d-126">AppDomain</span></span>|<span data-ttu-id="9325d-127">xs:string</span><span class="sxs-lookup"><span data-stu-id="9325d-127">xs:string</span></span>|<span data-ttu-id="9325d-128">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="9325d-128">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
