---
title: 4208 - RetryingSqlCommandDueToSqlError
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8e6483a-a6e4-4bbf-82ec-cd8b6e711aad
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b3bfe7547fafb17503c972646d344263117d9d86
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="fe8e9-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="fe8e9-102">4208 - RetryingSqlCommandDueToSqlError</span></span>
## <a name="properties"></a><span data-ttu-id="fe8e9-103">属性</span><span class="sxs-lookup"><span data-stu-id="fe8e9-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fe8e9-104">ID</span><span class="sxs-lookup"><span data-stu-id="fe8e9-104">ID</span></span>|<span data-ttu-id="fe8e9-105">4208</span><span class="sxs-lookup"><span data-stu-id="fe8e9-105">4208</span></span>|  
|<span data-ttu-id="fe8e9-106">关键字</span><span class="sxs-lookup"><span data-stu-id="fe8e9-106">Keywords</span></span>|<span data-ttu-id="fe8e9-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="fe8e9-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="fe8e9-108">级别</span><span class="sxs-lookup"><span data-stu-id="fe8e9-108">Level</span></span>|<span data-ttu-id="fe8e9-109">信息</span><span class="sxs-lookup"><span data-stu-id="fe8e9-109">Information</span></span>|  
|<span data-ttu-id="fe8e9-110">通道</span><span class="sxs-lookup"><span data-stu-id="fe8e9-110">Channel</span></span>|<span data-ttu-id="fe8e9-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="fe8e9-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="fe8e9-112">描述</span><span class="sxs-lookup"><span data-stu-id="fe8e9-112">Description</span></span>  
 <span data-ttu-id="fe8e9-113">指示 SQL 提供程序由于 SQL 错误正在重试 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="fe8e9-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="fe8e9-114">消息</span><span class="sxs-lookup"><span data-stu-id="fe8e9-114">Message</span></span>  
 <span data-ttu-id="fe8e9-115">因 SQL 错误号 %1，正在重试 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="fe8e9-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="fe8e9-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="fe8e9-116">Details</span></span>  
  
|<span data-ttu-id="fe8e9-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="fe8e9-117">Data Item Name</span></span>|<span data-ttu-id="fe8e9-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="fe8e9-118">Data Item Type</span></span>|<span data-ttu-id="fe8e9-119">描述</span><span class="sxs-lookup"><span data-stu-id="fe8e9-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="fe8e9-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="fe8e9-120">ErrorNumber</span></span>|<span data-ttu-id="fe8e9-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe8e9-121">xs:string</span></span>|<span data-ttu-id="fe8e9-122">SQL 错误号。</span><span class="sxs-lookup"><span data-stu-id="fe8e9-122">The SQL error number.</span></span>|  
|<span data-ttu-id="fe8e9-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="fe8e9-123">AppDomain</span></span>|<span data-ttu-id="fe8e9-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="fe8e9-124">xs:string</span></span>|<span data-ttu-id="fe8e9-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="fe8e9-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
