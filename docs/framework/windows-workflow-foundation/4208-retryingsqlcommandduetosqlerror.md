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
ms.workload: dotnet
ms.openlocfilehash: 51374a25ee11b3344e950670cc7882db42d39779
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="4208---retryingsqlcommandduetosqlerror"></a><span data-ttu-id="24dcb-102">4208 - RetryingSqlCommandDueToSqlError</span><span class="sxs-lookup"><span data-stu-id="24dcb-102">4208 - RetryingSqlCommandDueToSqlError</span></span>
## <a name="properties"></a><span data-ttu-id="24dcb-103">属性</span><span class="sxs-lookup"><span data-stu-id="24dcb-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="24dcb-104">ID</span><span class="sxs-lookup"><span data-stu-id="24dcb-104">ID</span></span>|<span data-ttu-id="24dcb-105">4208</span><span class="sxs-lookup"><span data-stu-id="24dcb-105">4208</span></span>|  
|<span data-ttu-id="24dcb-106">关键字</span><span class="sxs-lookup"><span data-stu-id="24dcb-106">Keywords</span></span>|<span data-ttu-id="24dcb-107">WFInstanceStore</span><span class="sxs-lookup"><span data-stu-id="24dcb-107">WFInstanceStore</span></span>|  
|<span data-ttu-id="24dcb-108">级别</span><span class="sxs-lookup"><span data-stu-id="24dcb-108">Level</span></span>|<span data-ttu-id="24dcb-109">信息</span><span class="sxs-lookup"><span data-stu-id="24dcb-109">Information</span></span>|  
|<span data-ttu-id="24dcb-110">通道</span><span class="sxs-lookup"><span data-stu-id="24dcb-110">Channel</span></span>|<span data-ttu-id="24dcb-111">Microsoft-Windows-应用程序服务器-应用程序/调试</span><span class="sxs-lookup"><span data-stu-id="24dcb-111">Microsoft-Windows-Application Server-Applications/Debug</span></span>|  
  
## <a name="description"></a><span data-ttu-id="24dcb-112">描述</span><span class="sxs-lookup"><span data-stu-id="24dcb-112">Description</span></span>  
 <span data-ttu-id="24dcb-113">指示 SQL 提供程序由于 SQL 错误正在重试 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="24dcb-113">Indicates the SQL provider is retrying a SQL command due to a SQL error.</span></span>  
  
## <a name="message"></a><span data-ttu-id="24dcb-114">消息</span><span class="sxs-lookup"><span data-stu-id="24dcb-114">Message</span></span>  
 <span data-ttu-id="24dcb-115">因 SQL 错误号 %1，正在重试 SQL 命令。</span><span class="sxs-lookup"><span data-stu-id="24dcb-115">Retrying a SQL command due to SQL error number %1.</span></span>  
  
## <a name="details"></a><span data-ttu-id="24dcb-116">详细信息</span><span class="sxs-lookup"><span data-stu-id="24dcb-116">Details</span></span>  
  
|<span data-ttu-id="24dcb-117">数据项名称</span><span class="sxs-lookup"><span data-stu-id="24dcb-117">Data Item Name</span></span>|<span data-ttu-id="24dcb-118">数据项类型</span><span class="sxs-lookup"><span data-stu-id="24dcb-118">Data Item Type</span></span>|<span data-ttu-id="24dcb-119">描述</span><span class="sxs-lookup"><span data-stu-id="24dcb-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="24dcb-120">ErrorNumber</span><span class="sxs-lookup"><span data-stu-id="24dcb-120">ErrorNumber</span></span>|<span data-ttu-id="24dcb-121">xs:string</span><span class="sxs-lookup"><span data-stu-id="24dcb-121">xs:string</span></span>|<span data-ttu-id="24dcb-122">SQL 错误号。</span><span class="sxs-lookup"><span data-stu-id="24dcb-122">The SQL error number.</span></span>|  
|<span data-ttu-id="24dcb-123">AppDomain</span><span class="sxs-lookup"><span data-stu-id="24dcb-123">AppDomain</span></span>|<span data-ttu-id="24dcb-124">xs:string</span><span class="sxs-lookup"><span data-stu-id="24dcb-124">xs:string</span></span>|<span data-ttu-id="24dcb-125">由 AppDomain.CurrentDomain.FriendlyName 返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="24dcb-125">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|
